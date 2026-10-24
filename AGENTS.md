# 项目执行入口

先读取 .ai-coding/project.json、services.json、docs/engineering/workflow.md、docs/progress/current.md。按 manifest 定位本轮需求、完整设计 HTML 和 Spec，已有文件保持原位。已确认材料直接使用，小修复不重新设计。

本地功能按 docs/engineering/local.md 实施；助手维护技术方案、实现、验证和进度。初始化及新增能力使用用户级 ai-coding-project。平台技能在用户级可用，按当前任务调用：GitHub 仓库与静态发布用 ai-coding-github；云端数据、函数、部署与 AI 后端用 ai-coding-cloudbase；安卓交付用 ai-coding-android。未选能力不作为缺项，不使用其他作品的资源绑定。

运行、依赖维护和 Web/APK 编译使用 .ai-coding/local.json 绑定的公共执行包 scripts/Invoke-CourseProject.ps1 与同一准备镜像。引擎/依赖故障按 docs/engineering/project-execution.md 恢复；不在宿主新增项目工具链，不换镜像、身份或重建作品绕过失败。

按“本轮目标 → 已确认需求与设计 → Spec → 实现 → 助手检查 → 本人试用 → 进度”接续。中大型改动使用 docs/specs/_template.md；小修复沿当前 Spec。技术检查由助手承担；本人处理产品取舍、必要身份/费用/位置和实际试用。准备、接入、调用、发布、安装与本人试用分别记录，未验证不得报通过。

涉及异步表单、编译失败或浏览器验收时读取 docs/engineering/web-verification.md；定位首个真实错误，按实际工具能力操作，区分模拟分支、真实请求失败、独立会话和本人试用证据。

平台凭证与管理授权不由技能目录自动隔离。所有远程操作核对当前项目 services.json 的目标、身份与范围。模型 Key 仅由受保护服务端保管，不进入前端、Git、APK、镜像和日志。需要 AI 时才读取用户级 CloudBase 技能 implementation/ai-service-setup.md 与 model-settings.md，不在准备或纯本地初始化要求供应商账号和调用。

仅明确选择案例才加载本项目案例技能，保留原工程、设计、稳定标识、资源绑定与已确认授权。结束更新当前 Spec 与 progress，提供真实入口、缺项和下一步。
