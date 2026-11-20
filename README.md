# Runke Fan's academic homepage

Live site: https://eric6frank.github.io/

This Jekyll homepage adapts the local `academicpages.github.io-master` template's
sidebar/content structure and reuses its Academicons assets, base-path include,
and MIT license. The layout and styles are customized to match the supplied
white-background academic homepage reference. No sample publications, sample
personal information, or unrelated template pages are published.

## 发布和本地目录

- GitHub 仓库：`Eric6Frank/Eric6Frank.github.io`
- GitHub Pages：Deploy from a branch → `main` → `/ (root)`。
- 在 `main` 提交修改后，GitHub Pages 自动构建 Jekyll 并发布。
- 原始 Academic Pages 文件夹保持不变。

## 日常更新位置

| 内容 | 文件 |
| --- | --- |
| 姓名、学校、邮箱、头像、微信图片、访客地图 ID | `_config.yml` |
| 英文个人介绍、News、Education、Experience、Awards、Contact | `index.html` |
| 论文标题、作者、发表状态、配图、论文链接 | `_data/publications.json` |
| 顶部导航 | `_data/navigation.yml` |
| 页面间距、字号、颜色和手机端布局 | `assets/css/homepage.css` |
| 左侧个人信息结构 | `_includes/author-profile.html` |

### 替换头像和微信二维码

1. 将真实头像保存为 `images/avatar.jpg`，二维码保存为 `images/wechat.png`。
2. 在 `_config.yml` 将 `author.avatar` 改为 `/images/avatar.jpg`，
   将 `author.wechat` 改为 `/images/wechat.png`。
3. 在 `_includes/author-profile.html` 将两张图片的 `alt` 分别改为
   `Portrait of Runke Fan` 和 `Runke Fan's WeChat QR code`。
4. 提交并推送。头像会裁切为圆形，二维码保持完整比例。

### 更新论文

编辑 `_data/publications.json`。`authors` 数组必须使用论文正式作者顺序；
`Runke Fan` 会自动加粗。将配图放在 `images/`，把 `image` 改为对应路径，
例如 `/images/dual-fa-uav.png`。留空时显示配图占位。

新增或替换链接时使用 `{"label": "Paper", "url": "https://doi.org/..."}`。
没有公开链接的论文不伪造链接；补齐信息后可删除 `note` 字段。

### 接入 Visitors 访客地图

当前只显示明确标注的占位，没有虚构访问次数或访问地点，也不会加载访客跟踪脚本。
开通自己的 ClustrMaps 地图后，复制嵌入脚本 URL 中 `d=` 后的 ID，
填入 `_config.yml` 的 `clustrmaps_id`（只填 ID，不填整段 HTML）。
再次发布后，真实地图自动替换占位。如采用其他服务，请替换 `index.html`
底部 Visitors 部分；那里也有中文注释说明。

### 内容待补充

- 头像、微信二维码和五篇论文的配图。
- WCL 投稿与 GLOBECOM 论文的完整作者顺序和公开论文链接。
- About Me 按提供的信息保留“三次一等奖学金”；Awards 仅列出已提供的
  2024、2025 年记录，第三次获奖年份待确认后添加。
- Google Scholar 在本次核对时返回 HTTP 429；目前论文列表结合用户提供的信息、
  arXiv、IEEE、Crossref 和合作者主页整理，不声称已完整导入 Scholar。

## 本地运行（可选）

安装 Ruby 和 Bundler 后：

```sh
bundle install
bundle exec jekyll serve
```

打开 http://127.0.0.1:4000/ 。仅通过 GitHub Pages 更新不需要本机安装 Ruby。

## 来源与许可

核对依据见 `docs/content-sources.md`。Academic Pages / Minimal Mistakes 的
MIT 许可保留在 `LICENSE`；Academicons 的许可说明保留在其 CSS 文件头中。
