# 本地网页

沿用本项目 PRD/Canvas，默认 Ionic React + TypeScript + Vite；Tailwind 3/PostCSS 在本地构建，不能用 CDN 掩盖编译问题。保持原型布局与交互，不默认添加导航或案例组件。

在项目已绑定镜像的 Compose 容器中开发；package.json/lockfile 为依赖依据。业务 IndexedDB 通过 Repository 隔离，后续云实现复用接口。仅实现当前需求中的数据与功能。

先复用已有组件和样式，把本轮Canvas布局/交互变化对应到实际文件；在spec记录组件改动、Repository接口与持久化边界，再增量实现。启动先检查绑定引擎与源码挂载；离线恢复原引擎/Compose，依赖缺失在同镜像处理。使用现有命名卷，不能用Windows node_modules或宿主npm绕过。热更新不生效先对URL、端口、挂载和watch配置，禁止盲目重建项目。

检查 Windows 挂载修改实际出现在页面、相同状态/视口对照原型、保存重开、修改删除、失败输入保留和受影响交互。真实浏览器结果、构建结果与本人试用分别记录，HTTP 200 不等于功能通过。


浏览器验证、相关结果复用与中断接续读取 [efficient-execution.md](efficient-execution.md)。Windows/WSL新模板已开启Vite轮询；旧工程核挂载和实际监听，只合并必要配置并重启一次。测试等待真实提交与可见状态，不用toast同名文本或任意延时替代持久化。
