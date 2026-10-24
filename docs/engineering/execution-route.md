# 从目标到实施

新会话读取项目根 AGENTS、manifest/services、工程基线与当前进度；按 manifest 找真实源码、PRD/Canvas、当前spec，不假定旧app/路径。先识别用户目标，再只读相关指南；不用使用者准确命名技能。

| 用户目标 | 默认路线 | 先复用什么 |
| --- | --- | --- |
| 更新资料/技能 | ai-coding-env/references/course-updates.md | 原 A、资料版本、共享技能摘要与原环境绑定 |
| 创建/恢复工程 | ai-coding-project | 准备登记、已有工程与资源绑定 |
| 本地网页功能 | local.md | 原Canvas、组件、Repository与本地模式 |
| 远程代码备份/协作 | ai-coding-github代码仓库模式 | 本项目源码remote与授权；不自动开Pages |
| github.io展示原型 | ai-coding-github 的 references/pages-cli.md + publishing.md | 确认HTML、专用静态仓库与公开资源 |
| 云端保存/正式发布 | cloudbase.md | 本项目环境、身份、实际表/桶及当前工具授权 |
| 安卓安装文件 | ai-coding-android | 原Web/Capacitor工程、appId和绑定镜像 |
| AI功能/更换模型 | ai.md + model-settings.md | 当前任务、凭证引用、工程默认、服务端有效模型/revision与既有设置入口 |

新增能力先按项目Skill implementation/capability-activation.md调用Enable-ProjectCapability，沿其nextSkills在同一任务继续；仅读取/修复已启用能力时复用原绑定。初始化不调用全部服务，未来计划不等于本轮接入。

中大型/跨端改动先用本项目spec模板写“目标/材料→现状复用→具体链路和改动点→有依赖的步骤→不可变项→失败分支→验收/接续”。已确认路线直接执行；小修复在原spec/进度记录，不要求本人填写技术文档、重发长提示或重复批准。

技术实施采用工程基线的默认方案；读取实际依赖版本与所需API再接入，不临时选全新框架。通用技能可处理不同业务；错题字段/演示用户/函数名/模型ID来自本项目或明确案例。案例与工程规范各有职责，发现冲突保留原工程、定位差异并更新记录。

引擎未开→启动已有引擎/原连接并恢复Compose；依赖错误→查独立卷、锁文件和Linux平台模块，同镜像修复；授权失效→对应服务技能恢复；权限错误→核登录、GRANT/RLS和归属；发布超时→查终态；APK旧内容→沿build/sync/包资源定位。不能宿主构建、换镜像/主版本、重建工程、放宽权限/TLS或交旧产物。

同原因有界恢复；技术限制需要改变路线时说明影响，先核用户已有决定，不自动重问普通修复。必要身份/费用由本人决定，未完成如实记录。结束给可打开入口/本轮文件位置和一个当前本人动作，更新实际结果与下一步，不把检查项当使用者作业。


阶段记录、一次诊断、稳定浏览器验证和相关结果复用按 [efficient-execution.md](efficient-execution.md)。新增AI设置按 当前项目 CloudBase 技能 implementation/ai-settings-access.md 先后端身份/存储/指定编辑者，再接UI和最小模型请求。

## 精简操作页面面后的执行责任（2.2.4）

页面省略技术清单不减少助手验收：先读 implementation/agent-step-checks.json 与当前目标指南，选定案例才合并其检查。需求材料优先按 manifest 的真实路径找；新文档推荐“需求说明文档.md”，兼容 PRD.md / 需求说明.md。多份存在先比版本和已确认记录，保留旧稿，不因文件名不同重复设计或自动重命名。

接收完整需求正文和 HTML 后由助手核材料、备份和设计一致性；本地实现维持原 Canvas；Pages 按 publishing.md 核公开资源/远程入口；云端实际验证持久化与双端同步；Android 用标准构建入口核新包来源/资源，再分别记录安装、启动、本人操作；AI 按已选任务核结构、鉴权、限额、失败路径和服务端共享设置。自动检查不能代替本人试用。技术异常由助手定位、修复并复验，只向本人给当前必要动作。此分工适用于各类业务，案例规则由案例维护。
