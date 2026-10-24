# 项目运行与依赖恢复

A保存原始准备，用户索引用于发现，B保存运行环境和公共执行包绑定。B已绑定时按原绑定恢复，不能用用户的新默认环境覆盖。A移走后可从明确索引摘要继续；实际引擎、镜像、源码挂载与依赖仍须核验。

## 公共执行入口

助手在PowerShell先解析本项目的公共执行包，再使用它的脚本。此包不位于技能发现目录，不依赖全局env技能：

```powershell
. "$env:USERPROFILE/.trae-cn/skills/ai-coding-project/scripts/Course-Execution.ps1"
$executionRoot = Resolve-CourseExecutionRoot '<B的绝对路径>'
& (Join-Path $executionRoot 'scripts/Invoke-CourseProject.ps1') -ProjectDirectory '<B的绝对路径>' -Action Start
& (Join-Path $executionRoot 'scripts/Invoke-CourseProject.ps1') -ProjectDirectory '<B的绝对路径>' -Action RunScript -Script build
```

同入口支持RunScript（实际package.json脚本）、Install、Add、Remove和Repair。依赖维护在同一准备镜像和原独立卷执行，先备份package/锁文件并只停止本项目app，失败保留记录。不挂宿主node_modules、不换镜像或宿主编译绕过故障。构建可-ReuseBuild按真实输入/产物摘要复用，不替代线上或手机验收。

根目录解析沿已有manifest，不在源码子目录另建工程。缺公共执行包或引擎时，回明确准备目录的env恢复原工具；不扫描用户目录或创建替代环境。发布和Android使用当前项目技能的标准入口，均复用绑定镜像。

已确认Spec中的本轮依赖可直接维护，主要版本或架构改变先说明影响并核已有授权。按docs/engineering/efficient-execution.md记录实际阶段、等待、结果与下一步，自动检查不替代本人试用。

外层报错未包含具体源码错误时，先读本轮 `.ai-coding/command.json` 与其日志，按 [首个错误定位](web-verification.md) 处理；不要猜另一个组件的类型、重新触发写操作来取输出，或只报告最后一次成功构建的耗时。
