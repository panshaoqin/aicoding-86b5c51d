# ai

固定 Web/APK callFunction → CloudBase 云函数 → 对应语言或多模态配置的模型服务 HTTPS。默认推荐硅基流动，允许不同供应商。新项目采用application-settings，由本人在程序输入模型Key、服务端保管；credentialRef仅明确旧工程兼容，不在初始化要求Key。模型/函数/输出取项目需求，仅实现本轮任务。服务端鉴权、持久限额、超时、结构校验和失败回退必验；基础地址和完整 endpoint 分清。

本轮spec明确复用函数/接口、输入输出、模型配置来源、秘密安全注入方式及错误恢复。先实现服务端验证/限额，再最小授权调用，再接页面；有效Key/模型证据复用，变更或缺项才补测。HTTP200、函数部署成功和模型输出满足业务要求分别判定；结果写库前保持本项目确认策略，不默认自动信任。

首次启用AI才生成config/ai-models.defaults.json；该文件分别提供 textBaseUrl/visionBaseUrl（默认均 https://api.siliconflow.cn/v1）与模型：textModel=deepseek-ai/DeepSeek-V4-Flash、visionModel=Qwen/Qwen3.8-27B，仅作为尚未配置时的初始值。V4 按当前项目 ai-coding-cloudbase/implementation/model-settings.md 实现“设置 → AI 服务”；保存到服务端本项目配置，持久化 revision，由按本项目确认策略授权的配置编辑者修改。网页和 Android 共享有效配置，函数按任务读取，分别从语言或多模态 Card 的同一 revision 读取地址、模型和对应 Key，不接受业务请求任意覆盖 URL/Key/model。“语言模型设置”和“多模态模型设置”两个 Card 各自配置 API URL、API Key、模型、测试/保存/恢复默认，互不覆盖；兼容服务只换配置不需重打 APK；失效配置不能静默回默认。模型 ID 可公开，Key 通过同一页面的独立受保护接口提交，按 ai-service-setup.md 仅存服务端。迁移旧函数环境变量时保留原选择，初始化不提前创建 UI/函数/业务表。


实施方法读通用开发Skill ai-settings-access.md：先验证函数PG访问身份和私有配置，再绑定指定用户、保存回读和接UI；函数service_role不替代应用授权。项目案例中已明确授权的用户可配置，不另建管理员；中性项目按自身策略。具体编辑者UID/资源/授权依据和SDK适配写本轮Spec。
