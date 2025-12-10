# GodzillaNodeJsPayload

本仓库为 Godzilla提供了NodeJs的有效载荷、加密器、插件等支持

## 项目简介

GodzillaNodeJsPayload 是一个为 Godzilla 平台提供的插件项目（基于 Java + Maven 构建）。本仓库以 Maven 为构建工具，生成的 jar 可作为 Godzilla 客户端的插件使用。

重要提醒：请在合规、合法并取得目标系统授权的前提下使用本仓库提供的任何代码或插件。

## 先决条件

- Java JDK（建议 8 或更高）
- Maven（命令行工具）
- Git（用于克隆仓库）
- Godzilla 客户端（用于加载插件）

## 构建（生成插件 Jar）

在仓库根目录下执行以下命令以生成可供 Godzilla 客户端加载的 jar：

```bash
# 克隆仓库（如尚未克隆）
git clone https://github.com/BeichenDream/GodzillaNodeJsPayload.git
cd GodzillaNodeJsPayload

# 使用 Maven 生成 jar（根据你的说明使用 mvn jar:jar）
mvn jar:jar
```

构建完成后，产物通常位于 `target/` 目录下，名称类似于：
```
target/<artifactId>-<version>.jar
```
如果你使用了不同的 Maven 配置或插件，jar 名称可能会有所不同。也可以使用 `ls target/*.jar` 来确认输出文件。

备注：
- 若项目使用了额外资源或依赖需要打包成可执行/包含依赖的单 jar，请根据需要改用 `mvn package` 并配合相应的打包插件（例如 maven-assembly-plugin 或 maven-shade-plugin）。
- 若你的 pom.xml 已设置为 `packaging` 为 `jar`，则 `mvn jar:jar` 会生成 jar 文件。

## 在 Godzilla 客户端中添加插件

1. 打开 Godzilla 客户端。
2. 进入 配置（或 设置）→ 插件配置（或 Plugin Configuration）。
3. 点击 添加/上传 插件（Add Plugin / Upload）。
4. 选择上一步构建得到的 jar 文件（例如 `target/your-artifact-1.0.jar`）。
5. 保存配置并根据 Godzilla 客户端的说明重启或刷新插件加载（如有必要）。

完成后，客户端应能在插件列表中看到并启用该插件。


## 常见命令（示例）

```bash
# 清理并生成 jar（更常用）
mvn clean package

# 仅生成 jar（按你的说明）
mvn jar:jar

# 查看 target 目录下的 jar
ls -lh target/*.jar
```

## 安全与合规

- 本仓库可能包含供测试或研究用途的功能。请务必仅在得到授权的环境中使用插件。
- 作者与维护者对任何未授权或非法使用本仓库内容导致的问题不承担责任。

## 贡献

欢迎提交 issue 或 PR。如需对 README 或插件功能进行改进，请：
1. Fork 本仓库
2. 新建分支并提交改动
3. 发起 Pull Request，描述改动内容与目的
