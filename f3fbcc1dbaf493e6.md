# URL Compass

URL Compass 是一个面向技术研究者、内容聚合者与信息管理工程师的开源外链资源归集系统。该项目并不生产原始内容，而是提供一套结构化的 URL 索引框架，用于对分散在多个来源中的深度技术文章、案例文档与参考材料进行集中式导航。其核心定位在于解决个人与团队在跨平台信息检索过程中面临的链接失散、上下文缺失与回溯效率低下等问题，通过建立统一的资源清单（Resource Manifest）与分类视图，帮助用户将零散的网页地址转化为可复用、可共享的知识资产。

本项目适用于需要长期维护外部参考链接库的文档工程师、技术布道师、科研助理以及开源社区维护者。URL Compass 不依赖特定数据库或云服务，所有资源记录以纯文本形式存储于项目仓库中，确保可移植性与版本控制友好性。通过本项目提供的示例数据与目录结构，用户可以快速上手构建自己的专属外链集合，并配合自动化脚本实现链接可达性检测与元信息提取。

## 功能概览

**结构化资源清单管理**：提供统一的 URL 登记格式与目录分类规范，支持按来源域名、内容主题或采集批次对链接进行分组存储，便于后续检索与统计。

**链接状态标记系统**：内置建议性的状态标签体系，包括未读、待整理、已归档、失效待更新等，帮助用户追踪每条外链的处理进度。

**多维度分类视图**：资源可按技术领域、文章类型、采集时间或优先级进行多级分类，同一链接可映射至多个分类节点，无需物理复制。

**纯文本可移植性**：所有资源数据以 Markdown 或 YAML 片段形式保存，无需专用客户端即可查看和编辑，兼容主流代码托管平台。

**批量导入与去重检测**：支持从 CSV 或纯文本列表批量导入 URL，并自动识别重复条目，减少人工核对成本。

**链接可达性检查接口**：项目提供可选的脚本工具，利用 HTTP 头部请求验证链接有效性，生成可达性报告供用户参考。

**自定义元信息扩展**：每条资源记录允许附加自定义键值对元数据，例如作者、发布日期、摘要关键词或阅读时长，满足个性化需求。

**版本化变更追踪**：由于所有资源清单纳入 Git 版本控制，每次增删改操作均保留历史记录，支持回滚与变更审计。

## 应用场景

技术文档团队整理外部参考库：文档编写人员经常需要引用第三方技术博客、规范文档或 API 参考。URL Compass 可作为团队共享的链接总表，统一存放所有被引用过的外部资源，避免重复查找，并在外部链接失效时快速定位并更新。

开源项目维护者管理社区资源推荐：开源项目维护者可以在项目仓库中维护一个官方推荐的外部资源列表，包括相关工具、教程和生态项目，帮助社区新成员快速了解项目周边生态，同时以版本化方式记录资源增减过程。

个人研究者构建主题式阅读清单：研究人员针对某一特定技术方向或课题，可以使用 URL Compass 创建个人阅读清单，按主题分类存储大量文章链接，并结合状态标签标记已读、待精读或需引用，提升文献管理效率。

技术内容聚合站点生成链接看板：小型技术内容站点或导航站点的运营者可以利用本项目的目录结构生成链接看板页面，通过自动化脚本将资源清单转换为 HTML 导航页，减少手动维护前端代码的工作量。

## 快速开始

以下命令演示如何将本项目克隆至本地环境，安装基础依赖并运行初始资源检查脚本。

```bash
git clone https://github.com/example/url-compass.git
cd url-compass
pip install -r requirements.txt
python scripts/check_links.py --manifest manifests/current_batch.txt
```

## 安装要求

| 依赖组件 | 必需版本 | 说明 |
|---|---|---|
| Python | 3.8 及以上 | 用于运行链接检查与元信息解析脚本 |
| Git | 2.25 及以上 | 用于版本控制与仓库克隆操作 |
| pip | 20.0 及以上 | 用于安装 Python 依赖包 |
| requests | 2.25.0 及以上 | 发送 HTTP 请求进行链接可达性检测 |
| pyyaml | 5.4.0 及以上 | 用于解析 YAML 格式的元数据配置文件 |
| markdown-cli | 0.1.0 及以上（可选） | 用于将资源清单渲染为 HTML 预览页面 |
| shellcheck | 0.7.0 及以上（可选） | 用于检查辅助 shell 脚本的语法正确性 |

## 文档导航

| 层面 | 目录 | 回答的问题 |
|---|---|---|
| 用户手册 | docs/user-guide.md | 如何添加新链接、如何分类、如何使用状态标签 |
| 管理员指南 | docs/admin-guide.md | 如何备份清单、如何合并分支、如何处理失效链接 |
| 开发者参考 | docs/developer-api.md | 脚本接口说明、配置文件格式、扩展开发方式 |
| 设计文档 | docs/design-overview.md | 项目设计目标、分类模型设计、元数据方案对比 |
| 常见任务 | docs/recipes.md | 批量导入、导出为 CSV、生成静态导航页等操作示例 |
| 版本记录 | docs/changelog.md | 各版本功能变更、脚本更新与兼容性说明 |

## 资源列表

本项目第 36/56 批次共收录 180 条外链资源，全部来自 wap.mobile.occzl.cn 域下的技术文章详情页。该批次资源集中覆盖移动端开发、前端工程化、网络协议分析及数据处理等主题。以下按链接标识符的数值特征进行分组展示，所有 URL 均保留原始格式，未做任何协议转换、域名规范化或路径改写。

### 第 36 批次资源（标识符 0001 - 0999 区间）

http://wap.mobile.occzl.cn/Article/details/0110.sHtML
http://wap.mobile.occzl.cn/Article/details/0067.sHtML
http://wap.mobile.occzl.cn/Article/details/0552.sHtML
http://wap.mobile.occzl.cn/Article/details/0573.sHtML
http://wap.mobile.occzl.cn/Article/details/06193.sHtML
http://wap.mobile.occzl.cn/Article/details/0673.sHtML
http://wap.mobile.occzl.cn/Article/details/0671726.sHtML
http://wap.mobile.occzl.cn/Article/details/0922.sHtML
http://wap.mobile.occzl.cn/Article/details/099472.sHtML
http://wap.mobile.occzl.cn/Article/details/09959.sHtML

### 第 36 批次资源（标识符 1000 - 3999 区间）

http://wap.mobile.occzl.cn/Article/details/105686.sHtML
http://wap.mobile.occzl.cn/Article/details/116220.sHtML
http://wap.mobile.occzl.cn/Article/details/120329.sHtML
http://wap.mobile.occzl.cn/Article/details/12109.sHtML
http://wap.mobile.occzl.cn/Article/details/12229.sHtML
http://wap.mobile.occzl.cn/Article/details/1240.sHtML
http://wap.mobile.occzl.cn/Article/details/1374762.sHtML
http://wap.mobile.occzl.cn/Article/details/147766.sHtML
http://wap.mobile.occzl.cn/Article/details/165950.sHtML
http://wap.mobile.occzl.cn/Article/details/1745892.sHtML
http://wap.mobile.occzl.cn/Article/details/17497.sHtML
http://wap.mobile.occzl.cn/Article/details/1802309.sHtML
http://wap.mobile.occzl.cn/Article/details/181708.sHtML
http://wap.mobile.occzl.cn/Article/details/1921.sHtML
http://wap.mobile.occzl.cn/Article/details/1934.sHtML
http://wap.mobile.occzl.cn/Article/details/197054.sHtML
http://wap.mobile.occzl.cn/Article/details/1980.sHtML
http://wap.mobile.occzl.cn/Article/details/2188.sHtML
http://wap.mobile.occzl.cn/Article/details/23065.sHtML
http://wap.mobile.occzl.cn/Article/details/23159.sHtML
http://wap.mobile.occzl.cn/Article/details/2320557.sHtML
http://wap.mobile.occzl.cn/Article/details/235882.sHtML
http://wap.mobile.occzl.cn/Article/details/24081.sHtML
http://wap.mobile.occzl.cn/Article/details/24342.sHtML
http://wap.mobile.occzl.cn/Article/details/24878.sHtML
http://wap.mobile.occzl.cn/Article/details/25616.sHtML
http://wap.mobile.occzl.cn/Article/details/25898.sHtML
http://wap.mobile.occzl.cn/Article/details/2673.sHtML
http://wap.mobile.occzl.cn/Article/details/274796.sHtML
http://wap.mobile.occzl.cn/Article/details/2784918.sHtML
http://wap.mobile.occzl.cn/Article/details/2877270.sHtML
http://wap.mobile.occzl.cn/Article/details/2888582.sHtML
http://wap.mobile.occzl.cn/Article/details/2984919.sHtML
http://wap.mobile.occzl.cn/Article/details/316390.sHtML
http://wap.mobile.occzl.cn/Article/details/32741.sHtML
http://wap.mobile.occzl.cn/Article/details/32967.sHtML
http://wap.mobile.occzl.cn/Article/details/3299.sHtML
http://wap.mobile.occzl.cn/Article/details/3394741.sHtML
http://wap.mobile.occzl.cn/Article/details/34342.sHtML
http://wap.mobile.occzl.cn/Article/details/3474685.sHtML
http://wap.mobile.occzl.cn/Article/details/35211.sHtML
http://wap.mobile.occzl.cn/Article/details/355504.sHtML
http://wap.mobile.occzl.cn/Article/details/356571.sHtML
http://wap.mobile.occzl.cn/Article/details/3646.sHtML
http://wap.mobile.occzl.cn/Article/details/37351.sHtML
http://wap.mobile.occzl.cn/Article/details/3753684.sHtML
http://wap.mobile.occzl.cn/Article/details/37622.sHtML
http://wap.mobile.occzl.cn/Article/details/37633.sHtML
http://wap.mobile.occzl.cn/Article/details/380551.sHtML
http://wap.mobile.occzl.cn/Article/details/383814.sHtML
http://wap.mobile.occzl.cn/Article/details/38428.sHtML
http://wap.mobile.occzl.cn/Article/details/3897459.sHtML
http://wap.mobile.occzl.cn/Article/details/394562.sHtML

### 第 36 批次资源（标识符 4000 - 7999 区间）

http://wap.mobile.occzl.cn/Article/details/404686.sHtML
http://wap.mobile.occzl.cn/Article/details/406148.sHtML
http://wap.mobile.occzl.cn/Article/details/4153.sHtML
http://wap.mobile.occzl.cn/Article/details/419442.sHtML
http://wap.mobile.occzl.cn/Article/details/421200.sHtML
http://wap.mobile.occzl.cn/Article/details/4244078.sHtML
http://wap.mobile.occzl.cn/Article/details/4375457.sHtML
http://wap.mobile.occzl.cn/Article/details/437806.sHtML
http://wap.mobile.occzl.cn/Article/details/44228.sHtML
http://wap.mobile.occzl.cn/Article/details/448119.sHtML
http://wap.mobile.occzl.cn/Article/details/4596.sHtML
http://wap.mobile.occzl.cn/Article/details/4664.sHtML
http://wap.mobile.occzl.cn/Article/details/4730386.sHtML
http://wap.mobile.occzl.cn/Article/details/477078.sHtML
http://wap.mobile.occzl.cn/Article/details/48076.sHtML
http://wap.mobile.occzl.cn/Article/details/4945.sHtML
http://wap.mobile.occzl.cn/Article/details/5002.sHtML
http://wap.mobile.occzl.cn/Article/details/501010.sHtML
http://wap.mobile.occzl.cn/Article/details/510916.sHtML
http://wap.mobile.occzl.cn/Article/details/5126243.sHtML
http://wap.mobile.occzl.cn/Article/details/51311.sHtML
http://wap.mobile.occzl.cn/Article/details/5144837.sHtML
http://wap.mobile.occzl.cn/Article/details/5154038.sHtML
http://wap.mobile.occzl.cn/Article/details/51546.sHtML
http://wap.mobile.occzl.cn/Article/details/525739.sHtML
http://wap.mobile.occzl.cn/Article/details/53698.sHtML
http://wap.mobile.occzl.cn/Article/details/542773.sHtML
http://wap.mobile.occzl.cn/Article/details/561768.sHtML
http://wap.mobile.occzl.cn/Article/details/5638565.sHtML
http://wap.mobile.occzl.cn/Article/details/57120.sHtML
http://wap.mobile.occzl.cn/Article/details/573636.sHtML
http://wap.mobile.occzl.cn/Article/details/58789.sHtML
http://wap.mobile.occzl.cn/Article/details/5891.sHtML
http://wap.mobile.occzl.cn/Article/details/592250.sHtML
http://wap.mobile.occzl.cn/Article/details/5939.sHtML
http://wap.mobile.occzl.cn/Article/details/5947000.sHtML
http://wap.mobile.occzl.cn/Article/details/59809.sHtML
http://wap.mobile.occzl.cn/Article/details/60588.sHtML
http://wap.mobile.occzl.cn/Article/details/60717.sHtML
http://wap.mobile.occzl.cn/Article/details/614631.sHtML
http://wap.mobile.occzl.cn/Article/details/63738.sHtML
http://wap.mobile.occzl.cn/Article/details/643267.sHtML
http://wap.mobile.occzl.cn/Article/details/643442.sHtML
http://wap.mobile.occzl.cn/Article/details/643846.sHtML
http://wap.mobile.occzl.cn/Article/details/6438.sHtML
http://wap.mobile.occzl.cn/Article/details/64784.sHtML
http://wap.mobile.occzl.cn/Article/details/6487.sHtML
http://wap.mobile.occzl.cn/Article/details/6673.sHtML
http://wap.mobile.occzl.cn/Article/details/668878.sHtML
http://wap.mobile.occzl.cn/Article/details/6895.sHtML
http://wap.mobile.occzl.cn/Article/details/68988.sHtML
http://wap.mobile.occzl.cn/Article/details/691118.sHtML
http://wap.mobile.occzl.cn/Article/details/6924044.sHtML
http://wap.mobile.occzl.cn/Article/details/6930336.sHtML
http://wap.mobile.occzl.cn/Article/details/695723.sHtML
http://wap.mobile.occzl.cn/Article/details/6992.sHtML
http://wap.mobile.occzl.cn/Article/details/7055.sHtML
http://wap.mobile.occzl.cn/Article/details/71180.sHtML
http://wap.mobile.occzl.cn/Article/details/7193008.sHtML
http://wap.mobile.occzl.cn/Article/details/7246757.sHtML
http://wap.mobile.occzl.cn/Article/details/728133.sHtML
http://wap.mobile.occzl.cn/Article/details/74105.sHtML
http://wap.mobile.occzl.cn/Article/details/7412.sHtML
http://wap.mobile.occzl.cn/Article/details/7474.sHtML
http://wap.mobile.occzl.cn/Article/details/7541.sHtML
http://wap.mobile.occzl.cn/Article/details/7634850.sHtML
http://wap.mobile.occzl.cn/Article/details/765599.sHtML
http://wap.mobile.occzl.cn/Article/details/76735.sHtML
http://wap.mobile.occzl.cn/Article/details/7679.sHtML
http://wap.mobile.occzl.cn/Article/details/7763427.sHtML
http://wap.mobile.occzl.cn/Article/details/77668.sHtML
http://wap.mobile.occzl.cn/Article/details/7775619.sHtML
http://wap.mobile.occzl.cn/Article/details/7879.sHtML
http://wap.mobile.occzl.cn/Article/details/7894.sHtML
http://wap.mobile.occzl.cn/Article/details/790292.sHtML
http://wap.mobile.occzl.cn/Article/details/79755.sHtML

### 第 36 批次资源（标识符 8000 及以上区间）

http://wap.mobile.occzl.cn/Article/details/806468.sHtML
http://wap.mobile.occzl.cn/Article/details/8182.sHtML
http://wap.mobile.occzl.cn/Article/details/8211.sHtML
http://wap.mobile.occzl.cn/Article/details/83609.sHtML
http://wap.mobile.occzl.cn/Article/details/838269.sHtML
http://wap.mobile.occzl.cn/Article/details/8443.sHtML
http://wap.mobile.occzl.cn/Article/details/8467077.sHtML
http://wap.mobile.occzl.cn/Article/details/864111.sHtML
http://wap.mobile.occzl.cn/Article/details/86488.sHtML
http://wap.mobile.occzl.cn/Article/details/8686.sHtML
http://wap.mobile.occzl.cn/Article/details/869028.sHtML
http://wap.mobile.occzl.cn/Article/details/8766.sHtML
http://wap.mobile.occzl.cn/Article/details/879814.sHtML
http://wap.mobile.occzl.cn/Article/details/8807.sHtML
http://wap.mobile.occzl.cn/Article/details/888457.sHtML
http://wap.mobile.occzl.cn/Article/details/8900.sHtML
http://wap.mobile.occzl.cn/Article/details/89226.sHtML
http://wap.mobile.occzl.cn/Article/details/8974.sHtML
http://wap.mobile.occzl.cn/Article/details/8990060.sHtML
http://wap.mobile.occzl.cn/Article/details/9058.sHtML
http://wap.mobile.occzl.cn/Article/details/914834.sHtML
http://wap.mobile.occzl.cn/Article/details/9169.sHtML
http://wap.mobile.occzl.cn/Article/details/9193965.sHtML
http://wap.mobile.occzl.cn/Article/details/9323082.sHtML
http://wap.mobile.occzl.cn/Article/details/93409.sHtML
http://wap.mobile.occzl.cn/Article/details/94964.sHtML
http://wap.mobile.occzl.cn/Article/details/950739.sHtML
http://wap.mobile.occzl.cn/Article/details/958137.sHtML
http://wap.mobile.occzl.cn/Article/details/9638653.sHtML
http://wap.mobile.occzl.cn/Article/details/965693.sHtML
http://wap.mobile.occzl.cn/Article/details/9966134.sHtML
http://wap.mobile.occzl.cn/Article/details/99722.sHtML
http://wap.mobile.occzl.cn/Article/details/9995475.sHtML
http://wap.mobile.occzl.cn/Article/details/99961.sHtML
http://wap.mobile.occzl.cn/Article/details/017548.sHtML
http://wap.mobile.occzl.cn/Article/details/020259.sHtML
http://wap.mobile.occzl.cn/Article/details/025229.sHtML
http://wap.mobile.occzl.cn/Article/details/02619.sHtML
http://wap.mobile.occzl.cn/Article/details/0263943.sHtML
http://wap.mobile.occzl.cn/Article/details/036401.sHtML
http://wap.mobile.occzl.cn/Article/details/05508.sHtML

## 项目结构

项目采用分层式目录结构，将资源清单、脚本工具、文档和配置文件分开存放，便于维护和扩展。

```
url-compass/
├── manifests/                         # 资源清单主目录
│   ├── current_batch.txt              # 当前活跃批次链接列表，每行一条 URL
│   ├── batch_36_of_56.txt             # 第 36 批次原始导入数据，含 180 条链接
│   ├── archived/                      # 历史归档批次存储区
│   │   ├── batch_35_of_56.txt         # 上一批次资源快照
│   │   └── batch_34_of_56.txt         # 更早批次资源快照
│   └── metadata/                      # 每条链接的扩展元信息目录
│       ├── 35211.yaml                 # 对应 Article ID 的元数据文件
│       └── 4153.yaml                  # 示例元数据，含作者、标签、状态等
├── scripts/                           # 辅助脚本目录
│   ├── check_links.py                 # 主脚本：批量检测 URL 可达性，输出报告
│   ├── import_csv.py                  # 从 CSV 导入链接并去重
│   ├── export_html.py                 # 将清单渲染为静态导航 HTML 页面
│   └── utils/                         # 脚本公用函数模块
│       ├── http_client.py             # 封装 requests 的统一超时与重试逻辑
│       └── parser.py                  # 解析 URL 与提取域名、路径参数
├── docs/                              # 项目文档目录
│   ├── user-guide.md                  # 用户手册，详细说明各项功能操作
│   ├── admin-guide.md                 # 管理员指南，涉及分支策略与冲突处理
│   ├── developer-api.md               # 开发者参考，脚本接口与配置格式
│   ├── design-overview.md             # 设计文档，分类模型与元数据方案
│   ├── recipes.md                     # 常见任务操作集，含批量导入与导出
│   └── changelog.md                   # 版本变更日志，记录每次功能增减
├── tests/                             # 单元测试与集成测试目录
│   ├── test_checker.py                # 链接检查模块的单元测试用例
│   ├── test_importer.py               # 导入功能的测试脚本
│   └── fixtures/                      # 测试用数据夹具
│       ├── sample_urls.txt            # 模拟输入数据
│       └── expected_output.json       # 预期输出参考
├── config/                            # 项目配置文件目录
│   ├── settings.yaml                  # 主配置文件，包含超时、重试、分类映射
│   └── taxonomy.yaml                  # 分类体系定义，描述所有可用类别及层级
├── output/                            # 脚本输出目录（自动生成，不纳入版本库）
│   ├── link_report.txt                # 链接可达性检查报告
│   └── navigation.html                # 导出的静态导航页面
├── requirements.txt                   # Python 依赖包列表
├── .gitignore                         # Git 忽略规则，排除 output 与临时文件
├── LICENSE                            # MIT 许可证全文
└── README.md                          # 本文件，项目总体介绍与入口文档
```

## 贡献指南

我们欢迎并鼓励社区成员以多种方式参与本项目，包括但不限于新增资源链接、完善元数据、优化脚本逻辑以及改进文档内容。请遵循以下步骤进行贡献：

第一，在 GitHub 上 Fork 本仓库至个人账号，并克隆到本地开发环境。创建新分支时，分支名称应体现本次变更主题，例如 add-batch-37-links 或 fix-checker-timeout。

第二，若为新增资源链接，请将 URL 逐行追加至 manifests/ 目录下对应的批次文件中，并遵循当前文件内的格式规范（每行一条 URL，不使用额外分隔符）。若需添加元数据，请在 metadata/ 子目录中新建或更新相应的 YAML 文件。

第三，运行本地测试脚本以确保变更不会破坏现有功能。执行 python -m pytest tests/ 命令，确认所有测试用例通过。若新增了脚本或修改了核心逻辑，请同步更新对应的单元测试。

第四，提交变更并推送至个人 Fork 仓库，随后向主仓库发起 Pull Request。请在 PR 描述中清晰说明变更目的、涉及的文件范围以及任何可能影响现有用户行为的改动。PR 至少需要一名项目维护者审核通过后方可合并。

第五，若您希望报告问题或提出功能建议，请直接在 GitHub Issues 中创建新议题，并使用项目提供的议题模板填写必要信息，包括运行环境、预期行为与实际行为对比等，以便快速定位与响应。

## 常见问题

Q: 项目中的 URL 链接如果失效了怎么办？

A: 用户可通过运行 scripts/check_links.py 脚本定期检查所有已登记链接的状态。脚本会生成一份报告，标记出所有返回 4xx 或 5xx 状态码的链接。用户可根据报告结果手动更新或移除失效链接。推荐每月运行一次检查，以保持资源清单的健康度。

Q: 我可以将本项目用于商业产品或闭源项目中吗？

A: 可以。本项目采用 MIT 许可证，允许自由使用、修改、分发和再授权，包括用于商业目的。唯一的条件是保留原始版权声明和许可证文本。详情请参阅项目根目录下的 LICENSE 文件。

Q: 如何将已有的大量书签或收藏夹导入到 URL Compass 中？

A: 您可以先将书签导出为 HTML 或 CSV 格式，然后使用项目提供的 scripts/import_csv.py 脚本进行批量导入。该脚本支持自定义列映射，可将书签标题、标签、添加时间等信息映射到元数据字段中。具体使用方法请参考 docs/recipes.md 中的导入操作示例。

## 许可证

MIT License

Copyright (c) 2026 URL Compass Contributors

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

> 外链数量: 180 | 生成时间: 2026-07-02 23:04:16
