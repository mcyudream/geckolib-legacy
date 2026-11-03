# GeckoLib Legacy 与上游差异

为本工作区 Ars Nouveau 与 Oritech 回迁提供 GeckoLib 4 系几何、动画采样和渲染接口。它是现代 GeckoLib API 的部分适配，不是既有 1.12 GeckoLib 3 的简单改名。

| 项目 | 上游基线 | 本 Legacy 版本 |
| --- | --- | --- |
| 参考版本 | GeckoLib 1.21.1 分支 / 4 系 API | 将使用中的 Geo / animation 接口映射到 1.12 渲染与资源生命周期。 |
| API 范围 | 现代上游完整库 | 当前为 78 个 Java 源文件组成的适配范围，不承诺完整 GeckoLib 4 或 3 的 API 覆盖。 |
| 动画行为 | 完整控制器、事件关键帧、过渡与 Molang | 已有几何和基础采样；完整过渡、事件关键帧与查询覆盖仍待对齐。 |
| 依赖关系 | 现代上游独立运行库 | 本库保持独立安装，Ars/Oritech 引用该版本；不把它作为已验收的通用替换品。 |
| 标识 | geckolib | 加载器 ID 为 geckolib-legacy，资源/Java 包保留各自原命名。 |

## 当前限制

- 需要与实际使用它的 Mod 一起核验资源重载、动画、模型和专服安全。
- 历史可启动或构建通过不代表所有动画行为与上游一致。
- 不支持把任何现代 GeckoLib Mod 直接放入 1.12。

以 [PUBLICATION.md](../PUBLICATION.md) 中的验收范围为准。
