# GeckoLib Legacy

![GeckoLib Legacy](branding/cover.png)

<!-- legacy-overview:start -->
为本工作区 Ars Nouveau 与 Oritech 回迁提供 GeckoLib 4 系几何、动画采样和渲染接口。它是现代 GeckoLib API 的部分适配，不是既有 1.12 GeckoLib 3 的简单改名。

## 当前状态

> **公开仓库目前包含项目介绍、上游差异、图像与 CI 框架。Mod 源码尚未提交，等待对应迁移验收完成。CI 此时只报告 scaffold，没有执行 Mod 编译。**

当前为进行中的迁移或改名后验收阶段。构建通过、接口已导入和历史测试结果均不等于完整移植完成。当前源码提交与产物状态见 [PUBLICATION.md](PUBLICATION.md)；未通过验收的项目暂不提供成品发布。

<!-- legacy-authorship:start -->
## 作者与来源 / Authors and upstream

- 此 Legacy 版本作者与维护者 / Legacy author and maintainer：**yudream**。
- 原作者 / Original author(s)：**GeckoLib contributors / bernie-g**。
- 原仓库 / Original repository：[bernie-g/geckolib](https://github.com/bernie-g/geckolib)。
- 上游基线：`1.21.1`。
- 固定上游提交：[`cce098097cdd`](https://github.com/bernie-g/geckolib/commit/cce098097cdd2084d8383bec593e0db79e0ed5a0)。
- 本版本独立维护；上游版权、许可证及资源来源声明保留于 LICENSE / NOTICE 文件中。
<!-- legacy-authorship:end -->

## 运行环境与身份

| 项目 | 要求 / 标识 |
| --- | --- |
| Minecraft | 1.12.2 |
| 运行基线 | Cleanroom **0.4.0 正式版（不带 `-alpha`）** |
| Java | 25 |
| 加载器 Mod ID | `geckolib-legacy` |
| 资源与原注册命名空间 | `geckolib`（保留） |

Mod 的 alpha 版本号与加载器版本无关。开发 SDK 可以较新，兼容结论必须来自上述正式运行基线。
加载器身份改名后，安装时应替换本项目旧 jar；原资源命名空间的保留不构成跨实现的存档转换承诺。

## 功能与迁移范围

- Geo 模型与骨骼缓存、资源读取和基础动画数据。
- Animatable、动画控制相关接口，以及实体、方块实体和物品的渲染适配。
- 面向 Ars Nouveau / Oritech 已实现模型的兼容代码。

## 与上游的具体差异

| 项目 | 上游基线 | 本 Legacy 版本 |
| --- | --- | --- |
| 参考版本 | GeckoLib 1.21.1 分支 / 4 系 API | 将使用中的 Geo / animation 接口映射到 1.12 渲染与资源生命周期。 |
| API 范围 | 现代上游完整库 | 当前为 78 个 Java 源文件组成的适配范围，不承诺完整 GeckoLib 4 或 3 的 API 覆盖。 |
| 动画行为 | 完整控制器、事件关键帧、过渡与 Molang | 已有几何和基础采样；完整过渡、事件关键帧与查询覆盖仍待对齐。 |
| 依赖关系 | 现代上游独立运行库 | 本库保持独立安装，Ars/Oritech 引用该版本；不把它作为已验收的通用替换品。 |
| 标识 | geckolib | 加载器 ID 为 geckolib-legacy，资源/Java 包保留各自原命名。 |

## 尚未实现与兼容边界

- 需要与实际使用它的 Mod 一起核验资源重载、动画、模型和专服安全。
- 历史可启动或构建通过不代表所有动画行为与上游一致。
- 不支持把任何现代 GeckoLib Mod 直接放入 1.12。

## 依赖

- Java 25 / Cleanroom；具体支持范围由消费方的实际验证决定。

## 使用方式

1. 在依赖本移植的 Mod 明确要求时，安装相同验收版本的 GeckoLib Legacy。
2. 开发者先核查所用类、方法、Molang 查询与关键帧在本实现中的覆盖。

## 构建与 CI

在完整源码项目目录使用 Java 25 执行：

```bash
python3 tools/bootstrap_legacy.py
bash gradlew --no-daemon :build :reobfJar --console=plain
python3 tools/verify_legacy_package.py
```

CI 会准备固定版本的源码依赖，构建完整主源码与测试，并检查发行 jar 的身份、作者和图标。
仅有文档的仓库会明确报告 scaffold，不把跳过编译标为 Mod 构建成功。CI 构建不能替代客户端玩法和专服验收。

## 发布平台

CurseForge / Modrinth 的项目资料、文件、依赖和 CI 凭据配置见 [发布说明](docs/PUBLISHING.md)。平台尚未发布的状态见 PUBLICATION.md。

## 授权与图像

保留 GeckoLib 上游 LICENSE 与固定提交；不修改上游版权归属。

此版本作者为 **yudream**，上游作者与版权保留如上。`branding/icon.png` 和 `branding/cover.png` 为本项目生成的展示图，
以代表物品或概念表现项目；不作为游戏实机截图，也不改变上游游戏资源的授权。生成记录见 `branding/provenance.json`。

<!-- legacy-overview:end -->
