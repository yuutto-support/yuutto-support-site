# Yuutto Help 维护基线

最后整理：2026-09-15

## 当前已核验事实

- Apple App Store 应用名：Yuutto
- App Store Seller：CAMELS IT
- Apple 端版本：6.0.6（2026-09-15 核验；后续必须重新检查）
- iPhone：iOS 13 或更高版本
- iPad：iPadOS 13 或更高版本
- Mac：macOS 10.13 或更高版本
- App Store 还列出 Apple Vision：visionOS 1.0 或更高版本；当前站点不是主要搜索意图，正文不主动扩写该平台
- 品牌主站：https://youtujsq9.net/
- 2026-09-15 核验时，品牌主站可见 Android 入口，并列有 Windows 支持信息

## 每次更新前必须检查

1. Apple App Store：版本号、Seller、系统兼容要求是否变化。
2. 品牌主站：域名是否仍有效，Android / Windows 入口或支持信息是否变化。
3. 站内凡是写死版本号、系统要求、开发者/Seller、域名的页面是否同步更新。
4. sitemap 的 lastmod 只在页面有实质修改时更新，不要每天自动改日期。
5. 绑定独立域名后，统一替换 canonical、Open Graph URL、sitemap、robots、llms.txt 中的 GitHub Pages 地址。

## 内容写作规则

- 每页先解决一个真实问题，不为了关键词单独复制近似页面。
- 避免“本文将介绍”“本页用于整理”“为了 SEO/关键词密度”等编辑后台口吻。
- Android、iPhone、Windows、Mac 必须按各自系统实际差异写，不能只替换平台名。
- 不规定统一字数；有信息就写，没有新信息不凑篇幅。
- 容易变化的数字必须有公开来源和核验日期。没有可靠来源就明确说暂未写死。
- 产品方宣传（速度、隐私、安全等）不能直接改写成本站独立事实。
- App Store 页面中的开发者宣传、营销文案和隐私承诺也不自动视为本站事实；应用名、Seller、版本号、兼容要求等可直接核对的字段，与宣传性描述分开处理。
- 不写政治人物、政治事件、地缘冲突，也不围绕规避监管等敏感场景扩展内容。
- 避免绝对化承诺，例如“100%安全”“绝对无日志”“永久免费”“永不掉线”。
- 文章优先写判断方法、真实故障现象和用户下一步，而不是堆同义品牌词。
- 重要事实页保留“核验来源”和日期。

## 页面职责

- 首页：任务导航 + 最关键的当前事实，不写成百科长文。
- /brand/yuutto/：品牌实体与名称关系。
- /brand/yuutto-vpn/：解释为什么用户会搜 VPN 相关名称，避免复制品牌页。
- /brand/official-website/：入口识别与真假判断。
- /download/*：只处理对应平台的下载、兼容和安装注意事项。
- /faq/*：按故障现象解决问题。
- /update-log/：只记录会影响用户判断的实质更新。

## V4 固定规则（GitHub Pages 阶段）

- 当前发布地址继续使用 `https://yuutto-support.github.io/yuutto-support-site/`，暂不绑定独立域名。
- `404.html` 的站内资源与导航使用 `/yuutto-support-site/` 开头的仓库根路径，避免深层 404 地址导致 CSS、JS 和链接错位。
- Schema 按页面真实用途选择：下载/更新聚合页用 CollectionPage；FAQ 聚合页用 FAQPage；关于页用 AboutPage；联系页用 ContactPage；操作与排障文章才使用 TechArticle。
- Yuutto Help 由 Yuutto / 优途加速器品牌团队维护。Schema 中使用“Yuutto 品牌团队”作为维护方描述，不把它写成未经确认的注册公司名称。
- 不为了“去 AI”机械替换同义词；重复的是写法和页面职责时才改。导航、产品名、系统名等必要重复保留。
- “核验时间”和“内容更新时间”分开理解：仅检查事实但正文无实质变化时，不应刷新 sitemap lastmod。


## V5 语义与内容细修

- FAQ 聚合页只保留一个完整 FAQPage Schema，避免重复声明同一页面类型。
- `/brand/yuutto-vpn/` 与 `/brand/official-website/` 作为解释/识别页面，不再额外声明 TechArticle。
- `SoftwareApplication` 中 CAMELS IT 使用 `provider` 表达已核对的产品提供方关系，不使用含义更强的 `author`。
- `Organization` 不再把 App Store 产品页放入 `sameAs`；App Store 链接归入 Yuutto 的 `SoftwareApplication` 实体。
- 面向用户的页面尽量用“信息核对、相关入口”等自然表达，减少连续出现“当前、核验、本页来源”等审计式口吻。
- 这些调整不改变已核验事实；事实发生变化时才更新对应内容与维护记录。
## V6 固定规则（实体与反馈入口）

- 搜索需求不等于实体事实。“Yuutto VPN”“优途VPN”“优途加速”“优途梯子”“Yuutto梯子”等可以作为用户搜索称呼自然解释，但除非品牌或可靠公开来源明确这样命名，否则不要全部写入 `SoftwareApplication.alternateName`。
- 当前 `SoftwareApplication.alternateName` 只保留更稳定的中文常用名称“优途加速器”；其他词放在正文中说明其搜索语境。
- 真正的教程与排障 `TechArticle` 加入 `publisher`，指向维护本站的 Yuutto 品牌团队；不要给普通 WebPage、FAQPage、CollectionPage 为了完整感硬塞 publisher。
- Contact 页给出可点击的 GitHub 项目仓库入口，不再出现“可以去 GitHub 提交”但没有入口的悬空提示。
- GitHub Issues 是否开放属于仓库设置，不在正文里把它写成永久客服承诺；账号、订单和服务状态仍引导至品牌主站当前客服渠道。
- Open Graph 分享图只有在有正式、长期可用的品牌图片后再添加 `og:image`，不要为了补标签使用临时占位图。
