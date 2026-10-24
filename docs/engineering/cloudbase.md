# cloudbase

使用项目明确绑定的 CloudBase PostgreSQL、Storage 和静态托管。公开连接值可进客户端配置，管理令牌不可进入。账号策略和数据规则由项目决定。调用用户级 ai-coding-cloudbase，先读其 references/official-routing.md，再按 implementation/cloudbase.md 的七步流程接续；SDK 范例在 references/web-pg-example.md，阶段计时与恢复在 implementation/efficient-execution.md。不依赖案例技能才取得通用方法。

助手先记录实际SDK版本/API或既有REST适配、应用登录方式、用户归属、表/桶与迁移。按管理资源→应用会话→最小受权限读写/图片→Repository接线→发布实施；管理员SQL不替代客户端结果。权限失败查登录/GRANT/RLS，不放宽匿名写；NoSQL总览不替代PG探测。数据同步默认按确认需求实现，不假称实时；演示seed和图片存储策略由本项目决定。

先读已有表、桶、登录方式和额度，再保存差异迁移；不为验证账号删除旧用户。CloudBase 静态托管承载网页，数据库与存储实现共享数据，两者分别验收。纯静态展示到 GitHub.io 调用 ai-coding-github，保留项目已确认的发布目标。
