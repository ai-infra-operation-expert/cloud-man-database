# 本机 App 清单（严格核验版）

> 盘点日期：2026-06-25 (Thu)
> 主机：`agmac` · macOS Darwin 25.5.0 (arm64) · Apple Silicon
> 核验方式：从每个 `.app/Contents/Info.plist` 取 `CFBundleDisplayName` / `CFBundleIdentifier` / `CFBundleShortVersionString` / `LSApplicationCategoryType`，避免肉眼分类偏差
> 原始数据：`/tmp/apps-strict.txt`（194 行）

---

## 0. 重大发现（先把错误纠正）

| App 名 | 我之前归类 | 真实身份（按 Bundle ID / Info.plist） |
|---|---|---|
| **Wukong.app** | 游戏 | **钉钉 Real**（`com.dingtalk.real` / 可执行 `DingTalkReal`）。不是黑神话悟空。 |
| **Muse** | 冥想 / AI | 显示名是 **Allume**（`com.musesoftware.museios-appstore`），iOS App Store 版移植 |
| **Shroomy** | 待确认 | 实际 Bundle 名是 **Reset**（`uk.co.resetapp.reset`），Shroomy 只是中文显示名 |
| **VideoFusion-macOS** | 视频编辑（猜） | **剪映专业版 / CapCut**（`com.lemon.lvpro`，ByteDance） |
| **pcsuite** | 待确认 | **vivo 电脑助手**（`com.vivo.pcsuite`） |
| **START** | 待确认 | **腾讯 START**（`com.tencent.start.mac.Start`），云游戏 / 串流 |
| **Marvis** | 音乐播放器（猜） | **腾讯 Marvis**（`com.tencent.mac.marvis`），开发者工具 |
| **ZCode** | 待确认 | **ZCode**（`dev.zcode.app`），开发者工具 |
| **Hacktivate** | 待确认 | **Hudson Hacktivate**（`uk.hudson.Hacktivate`），教育类 |

---

## 1. 统计概览

| 维度 | 数量 |
|---|---|
| `/Applications/*.app` | **192** |
| `/Applications` 中非 `.app` 项 | 2（`Utilities` 系统文件夹、`暗黑破坏神III` Steam 兼容目录） |
| `~/Applications` | 5 |
| **GUI 应用总计** | **197** |
| Homebrew Formulae | 110 |
| Homebrew Casks | 3 |
| Homebrew Services (running) | 2（mysql@8.0、redis） |
| npm 全局包 | 4 |
| pip3 全局包 | ~50 |
| `~/.local/bin` 自建 CLI | ~25 |
| `~/go/bin` Go 工具 | 7 |

---

## 2. 按 `LSApplicationCategoryType` 分类（Apple 官方分类）

> 只有 **120/192** 应用声明了 `LSApplicationCategoryType`；其余 72 个未声明（多为国产 / 老 App / 自研）。
> 未声明的 72 个在最后一节"未声明分类"单独列出。

### 2.1 `developer-tools` — 46 个

**AI 编程 IDE / 助手**

| App | Bundle ID | 厂商 |
|---|---|---|
| Antigravity | `com.google.antigravity` | **Google**（AI 编程 IDE） |
| AutoClaw | `com.zhipuai.autoclaw` | 智谱 |
| Chaterm | `ai.chaterm.global.app` | Chaterm |
| Cherry Studio | `com.kangfenmao.CherryStudio` | Cherry Studio |
| Codex | `com.openai.codex` | OpenAI |
| Comate | `com.baidu.comate.x` | 百度 |
| Cursor | `com.todesktop.230313mzl4w4u92` | Cursor（Anysphere） |
| Hermes | `com.nousresearch.hermes.setup` | Nous Research |
| JVS Claw | `com.aliyun.ecd.jvs` | 阿里云 JVS |
| Manus | `im.manus.desktop` | Manus |
| Multica | `ai.multica.desktop` | Multica |
| Qoder | `com.qoder.ide` | Qoder |
| Qoder CN | `com.aliyun.lingma.ide` | 通义灵码 |
| QoderWork | `com.qoder.work` | Qoder |
| Trae | `com.trae.app` | 字节 |
| Trae CN | `cn.trae.app` | 字节国内 |
| TRAE SOLO | `com.trae.solo.app` | 字节 |
| Windsurf | `com.exafunction.windsurf` | Codeium |
| WorkBuddy | `com.workbuddy.workbuddy` | WorkBuddy |
| ZCode | `dev.zcode.app` | ZCode |
| XETClaw | `com.xiaoe-tech.eclaw` | 小鹅通 Claw |
| Alibaba Cloud Client | `com.alibaba-cloud.client` | 阿里云 |
| Claude | `com.anthropic.claudefordesktop` | Anthropic |
| CodeBuddy | `com.tencent.codebuddy` | 腾讯 |
| Factory | `com.electron.factory` | Factory AI |
| pcsuite | `com.vivo.pcsuite` | vivo 电脑助手 |
| Qwen | `com.qwen.chat` | 通义千问 |
| Clash Verge | `io.github.clash-verge-rev.clash-verge-rev` | 开源 |

**终端 / SSH / 网络工具**

| App | Bundle ID |
|---|---|
| Warp | `dev.warp.Warp-Stable` |
| electerm | `org.electerm.electerm` |
| Termius | `com.termius-dmg.mac` |
| Medis (Redis GUI) | `li.zihua.medis2` |

**容器 / 桌面**

| App | Bundle ID |
|---|---|
| Docker | `com.docker.docker` |
| Ollama | `com.electron.ollama` |
| Marvis | `com.tencent.mac.marvis`（**腾讯开发者工具**） |

**IDE / 编辑器**

| App | Bundle ID |
|---|---|
| Visual Studio Code | `com.microsoft.VSCode`（display name = "Code"） |

**国产工具（含 office 周边）**

| App | Bundle ID | 备注 |
|---|---|---|
| QQ | `com.tencent.qq` | 居然被归 developer-tools |
| 抖音 | `com.bytedance.douyin.desktop` | 抖音桌面 |
| 哔哩哔哩 | `com.bilibili.bilibiliPC` | B 站 |
| 阶跃AI | `com.stepfun.desktop` | 阶跃 |
| 小鹅通学员版 | `com.xet.client` | 小鹅通 |
| 有道云笔记 | `ynote-desktop` | 有道 |
| 每日英语听力 | `com.eusoft.ting-mac-en` | Eusoft |
| WeGame | `com.tencent.wegame.mac.WeGame` | 腾讯游戏平台 |
| 汽水音乐 | `com.soda.music` | 字节汽水 |

---

### 2.2 `productivity` — 29 个

**笔记 / 文档 / 知识管理**

| App | Bundle ID |
|---|---|
| Obsidian | `md.obsidian` |
| Notion | `notion.id` |
| Bear | `net.shinyfrog.bear` |
| Typora | `abnerworks.Typora` |
| UlyssesMac | `com.ulyssesapp.mac` |
| Safari | `com.apple.Safari` |
| OneDrive | `com.microsoft.OneDrive-mac` |
| TencentDocs | `com.tencent.txdocs` |
| LibreOffice | `org.libreoffice.script` |
| wpsoffice | `com.kingsoft.wpsoffice.mac` |
| 语雀 | `com.yuque.app` |
| Things3 | `com.culturedcode.ThingsMac` |
| TickTick | `com.TickTick.task.mac` |
| Grammarly for Safari | `com.grammarly.safari.extension` |

**AI 助手**

| App | Bundle ID | 厂商 |
|---|---|---|
| Copilot | `com.microsoft.copilot-mac` | Microsoft |
| Kimi | `com.moonshot.kimichat` | 月之暗面 |
| Monica | `im.monica.desktop.monica` | Monica |
| MiniMax | `com.minimax.agent.cn` | MiniMax |
| Doubao | `com.bot.neotix.doubao` | 字节豆包 |
| ERNIE | `com.baidu.ernie` | 百度文心一言 |
| QClaw | `com.tencent.qclaw` | 腾讯 |
| Qianwen | `com.alibaba.tongyi` | 通义千问 |
| easyclaw | `ai.easyclaw.desktop` | EasyClaw |
| Muse (Allume) | `com.musesoftware.museios-appstore` | App Store 版移植 |
| Apps for Google App | `kj.gapps` | Google Apps 启动器 |

**云存储 / 同步**

| App | Bundle ID |
|---|---|
| BaiduNetdisk | `com.baidu.netdisk` |
| aDrive | `com.alicloud.smartdrive` |

---

### 2.3 `utilities` — 10 个

| App | Bundle ID | 备注 |
|---|---|---|
| Applite | `dev.aerolite.Applite` | Homebrew GUI |
| CleanMyMac_5_MAS | `com.macpaw.CleanMyMac-mas` | MacPaw |
| BOYA Central | `com.boyaCentral.BOYA.Appcn` | 麦克风 |
| LetsVPN | `world.letsgo.booster.mac.store` | VPN |
| MindMac | `app.mindmac.macos` | AI chat client |
| Perplexity | `ai.perplexity.mac` | AI 搜索 |
| PocketClaw | `com.rethinkingstudio.ClawControl` | **真正的 Claw 命名 app** |
| CBReader | `org.cbeta.CBReader` | CBETA 佛经 |
| Thunder | `com.xunlei.Thunder` | 迅雷 |
| 高德地图 | `com.autonavi.amap` | 高德 |

---

### 2.4 `social-networking` — 6 个

| App | Bundle ID |
|---|---|
| WeChat | `com.tencent.xinWeChat` |
| Discord | `com.hnc.Discord` |
| LINE | `jp.naver.line.mac` |
| Signal | `org.whispersystems.signal-desktop` |
| Telegram | `ru.keepcoder.Telegram` |
| WhatsApp | `net.whatsapp.WhatsApp` |

---

### 2.5 `entertainment` — 6 个

| App | Bundle ID |
|---|---|
| Infuse | `com.firecore.infuse`（高清播放器） |
| Prime Video | `com.amazon.aiv.AIVApp` |
| LibriVox | `biz.bookdesign.LibriVox` |
| START | `com.tencent.start.mac.Start`（腾讯云游戏 / 串流） |
| 爱奇艺 | `com.iqiyi.player` |
| QQLive | `com.tencent.tenvideo`（腾讯视频） |

---

### 2.6 `business` — 5 个

| App | Bundle ID |
|---|---|
| DingTalk | `5ZSL2CJU2T.com.dingtalk.mac` |
| Lark | `com.electron.lark` |
| Slack | `com.tinyspeck.slackmacgap` |
| TencentMeeting | `com.tencent.meeting` |
| Windows App | `com.microsoft.rdc.macos`（RDP） |

---

### 2.7 `news` — 3 个

| App | Bundle ID |
|---|---|
| Folo | `is.follow`（RSS） |
| Instapaper | `com.marcoarment.instapaperpro` |
| Ground News | `com.checkitt` |

---

### 2.8 `music` — 3 个

| App | Bundle ID |
|---|---|
| NeteaseMusic | `com.netease.163music` |
| QQMusic | `com.tencent.QQMusicMac` |
| 喜马拉雅 | `com.gemd.iting` |

---

### 2.9 `healthcare-fitness` — 3 个

| App | Bundle ID |
|---|---|
| Dark Noise | `com.charliemchapman.dark-noise` |
| Endel | `com.endel.endel` |
| 潮汐 | `tide.moreless.io`（display name = "Tide"） |

---

### 2.10 `video` — 2 个

| App | Bundle ID |
|---|---|
| VideoFusion-macOS | `com.lemon.lvpro`（**剪映专业版 / ByteDance**） |
| 优酷 | `com.youku.mac` |

---

### 2.11 `reference` — 2 个

| App | Bundle ID |
|---|---|
| Amazon Kindle | `com.amazon.Lassen` |
| 网易有道翻译 | `com.youdao.YoudaoDict` |

---

### 2.12 单一分类

| Category | App | Bundle ID |
|---|---|---|
| `travel` | Flighty | `com.flightyapp.flighty` |
| `navigation` | 百度文库 | `com.baidu.wenkupc` |
| `graphics-design` | Canva | `com.canva.canvaeditor` |
| `education` | Hacktivate | `uk.hudson.Hacktivate`（Hudson UK） |

---

## 3. 未声明 `LSApplicationCategoryType` 的应用（72 个，需按用途判断）

> 这些 App 没设官方分类，我按品牌 / 用途归。

### 3.1 实际是开发/IDE（推断归 developer-tools）

| App | Bundle ID | 备注 |
|---|---|---|
| CodeBuddy（注：腾讯版已声明）| — | 见上 |
| HBuilderX | `io.dcloud.HBuilderX` | DCloud IDE |
| Sublime Text | `com.sublimetext.4` | 编辑器 |
| Zed | `dev.zed.Zed` | 编辑器 |
| Google Chrome | `com.google.Chrome` | 浏览器（也归开发者工具） |
| Microsoft Edge | `com.microsoft.edgemac` | 浏览器 |
| DBeaver Community | `org.jkiss.dbeaver.core.product` | DB GUI |
| Termius | — | 已在 utilities |
| GitHub Desktop | `com.github.GitHubClient` | Git GUI |

### 3.2 浏览器

- Google Chrome, Microsoft Edge（见上）
- DuckDuckGo (`com.duckduckgo.mobile.ios`, display name = "DuckDuckGo")
- Tabbit Browser (`com.tab-browser.Tabbit`)
- Tabbit (`com.tabbit-ai.Tabbit`，**Tabbit 主入口？**)
- Quark (`com.quark.desktop`)
- QuarkCloudDrive (`com.quark.clouddrive.desktop`)

### 3.3 媒体 / 影音

**音乐播放器（除声明外）**

- Marvis（已在 developer-tools）

**视频 / 直播**

- Kuaishou (`com.jiangjia.gif`，display name = "Kwai")
- Bilibili（已在 developer-tools）
- rednote / 小红书 (`com.xingin.discover`)
- Shudder (`com.sundancenow.shudder`)
- Kick (`com.kick.mobile`)
- 人人视频 (`com.macvideos.mac`)
- OBS (`com.obsproject.obs-studio`)
- qBittorrent (`org.qbittorrent.qBittorrent`)

### 3.4 笔记 / 阅读

- Daily Canon (`org.thedailycanon.app`)
- Get笔记 (`com.biji.getNotes`，display name = "得到大脑")
- 微信读书 (`com.tencent.weread`)
- 读库 (`cn.duku`)
- 一个 (`com.chii.iOne`，display name = "ONE")
- 一席 (`fm.meow.yixi`)
- 三联中读 (`com.palmtrends.ptlifeweeker`)
- 盐言故事 (`com.zhihu.vip.ios`)
- 豆瓣 (`com.douban.frodo`)
- 极客时间 (`org.geekbang.GeekTime`)
- IMSLP (`com.petrucci.IMSLP`，古典乐谱)
- DeDao / 得到 (`com.luojilab.LuoJiFM-IOS`)
- Everand (`com.scribd.iscribd`)
- 快看漫画 (`com.kuaikan.comic`)

### 3.5 AI / 工具（未声明分类）

| App | Bundle ID | 备注 |
|---|---|---|
| MiniMax | — | 已在 productivity |
| Manus | — | 已在 dev-tools |
| Cherry Studio | — | 已在 dev-tools |
| Comet | `ai.perplexity.comet` | Perplexity 浏览器 |
| Cua Driver | `com.trycua.driver` | CuaDriver（display name 含空格） |
| CoPaw | `com.copaw.desktop` | CoPaw |
| ima.copilot | `com.tencent.imamac` | 腾讯 |
| Multica | — | 已在 dev-tools |
| Muse | — | 已在 productivity |
| MiniMax | — | 已在 productivity |
| 秘塔AI搜索 | `com.metaso` | 秘塔 |
| 秘塔回响 | `com.echo.client` | 秘塔回响 |
| 纳米AI | `com.qihoo.namiso` | 360 纳米 |
| 阶跃AI | — | 已在 dev-tools |
| 扣子 | `com.coze.space.ios` | Coze |
| 元宝 | `com.tencent.yuanbao` | 腾讯元宝 |

### 3.6 游戏 / 游戏平台

| App | Bundle ID | 备注 |
|---|---|---|
| Steam | `com.valvesoftware.steam` | Steam 客户端 |
| Stardew Valley | — | **未签名**，Steam 安装目录 |
| 暗黑破坏神III | — | Steam 兼容目录（不是 .app） |
| Wukong | `com.dingtalk.real` | **钉钉 Real**（重命名/复制） |
| Factorio | — | 在 `~/Applications/` |
| TapTap | `com.easyplay.taptap.now` | 游戏分发 |
| 小黑盒 | `com.max.xiaoheihe` | 游戏社区 |

### 3.7 健康 / 心理 / 灵性

| App | Bundle ID | 备注 |
|---|---|---|
| Calm | `com.calm.calmapp` | 冥想 |
| Headspace | `com.getsomeheadspace.headspace` | 冥想 |
| Keep | `com.gotokeep.keep` | 运动 |
| Lovable | `dev.lovable.build` | AI 应用 builder（**不是健康类**） |
| Now | `com.imoblife.now` | 待确认（疑为资讯 / 效率） |
| Reset (Shroomy) | `uk.co.resetapp.reset` | 习惯 / 戒瘾 / 专注 |
| Singing Bowl | `com.bowl.sleepiq.brain.fm.reveri.bettersleep.bowl` | 颂钵 / 助眠 |
| 每日瑜伽 | `yogadaily` | 瑜伽 |
| 壹心理 | `com.xinli001.xinli001` | 心理 |

### 3.8 求职 / 财经 / 社交

| App | Bundle ID |
|---|---|
| BOSS直聘 | `com.hpbr.bosszhipin` |
| 脉脉 | `com.taou.NeiTui` |
| 微博 | `com.sina.weibo` |
| Polymarket | `com.polymarket.ios-app` |
| QiChaCha (QCC) | `com.ioubo.ienterprise` |
| 小鹅通学员版 | — (已在 dev-tools) |

### 3.9 旅行 / 资讯

| App | Bundle ID | 备注 |
|---|---|---|
| iDaily | `com.chii.iDaily` | 每日新闻图赏 |
| 穷游 | `com.qyer.qyerguide` | 旅行 |
| Flighty | — | 已声明 |

### 3.10 媒体播放器 / 编辑

| App | Bundle ID |
|---|---|
| VideoFusion-macOS | — (已在 video) |
| OBS | — (见 3.3) |

### 3.11 其他（待确认）

| App | Bundle ID | 备注 |
|---|---|---|
| Now | `com.imoblife.now` | 无法仅凭 Bundle ID 判断用途 |
| OrcaTerm | `com.orcaterm.app` | 终端 / SSH（待确认） |
| pcsuite | — | 已确认 vivo |
| Muse | — | 已确认 Allume |
| Shroomy | — | 已确认 Reset |
| 小宇宙 | `app.podcast.cosmos` | 播客 |
| wechatwebdevtools | `com.tencent.webplusdevtools` | 微信开发者工具 |
| WorkBuddy | — | 已声明 |
| Wukong | `com.dingtalk.real` | **钉钉 Real，不是游戏** |

---

## 4. 用户级应用（~/Applications，5）

| App | Bundle ID | 备注 |
|---|---|---|
| Chrome Apps.localized | — | Chrome 应用容器 |
| Claude Code URL Handler | — | URL 协议处理器 |
| Factorio | — | 游戏 |
| Quark Apps.localized | — | 夸克应用容器 |
| Tabbit Apps.localized | — | Tabbit 应用容器 |

---

## 5. Homebrew Formulae（含版本，按"日常用 vs 编译依赖"分组）

### 5.1 日常用 CLI（~30）

| 工具 | 版本 | 用途 |
|---|---|---|
| ffmpeg | 8.1 | 音视频 |
| ffmpeg@8 | (alias) | — |
| fzf | 0.73.0 | 模糊查找 |
| gh | 2.92.0 | GitHub CLI |
| git | 2.54.0 | Git |
| go | 1.26.1 | Go |
| go@1.25 / go@1.26 | — | 多版本 |
| kind | 0.31.0 | 本地 K8s |
| kubectl / kubernetes-cli | 1.35.3 | K8s |
| llvm@21 | 21 | LLVM 工具链 |
| maven | latest | Java 构建 |
| mdbook | latest | 写书 |
| multica | 0.66.0 | Multica CLI（**注意：这是 crush 的别名**） |
| crush | 0.66.0 | Crush AI agent? |
| mysql@8.0 | 8.0 | DB (running) |
| node / node@25 | 25 | Node.js |
| ollama | latest | 本地 LLM |
| opencode | latest | AI 编程（终端版） |
| openjdk / openjdk@25 | 25 | JDK |
| pandoc | latest | 文档转换 |
| python@3.14 | 3.14 | Python |
| rbenv | latest | Ruby 版本管理 |
| ruby@3.2 | 3.2 | Ruby |
| redis / redis@8.6 | 8.6 | KV (running) |
| ripgrep / rg | latest | grep 替代 |
| rust | latest | Rust |
| tmux | latest | 终端复用 |
| unbound | latest | DNS (stopped) |
| uv | latest | Python 包管理 |
| xcodegen | latest | Xcode 项目生成 |
| zoxide | latest | cd 替代 |
| zsh-syntax-highlighting | latest | zsh |

### 5.2 编译期依赖（~80，被动安装）

abseil / ada-url / autoconf / brotli / c-ares / ca-certificates / cairo / dav1d / fmt / fontconfig / freetype / fribidi / gettext / giflib / glib / gmp / gnupg / gnutls / gpgme / gpgmepp / graphite2 / harfbuzz / hdrhistogram_c / icu4c@78 / jpeg-turbo / lame / libassuan / libcbor / libdatrie / libevent / libfido2 / libgcrypt / libgit2 / libgpg-error / libidn2 / libksba / libnghttp2 / libnghttp3 / libngtcp2 / libpng / libssh2 / libtasn1 / libthai / libtiff / libunistring / libusb / libuv / libvpx / libx11 / libxau / libxcb / libxdmcp / libxext / libxrender / libyaml / little-cms2 / llhttp / lz4 / lzo / m4 / mpdecimal / ncurses / nettle / npth / nspr / nss / openjpeg / openssl@3 / opus / p11-kit / pcre2 / pinentry / pixman / pkgconf / poppler / protobuf / sdl2 / simdjson / sqlite / svt-av1 / utf8proc / uvwasi / x264 / x265 / xorgproto / xz / zlib-ng-compat / zstd

### 5.3 可清理候选

- `unbound` —— 未运行，按需卸载
- `temurin@8`（cask）—— JDK 8 老版本，按需
- `crush` —— 与 `multica` 同源（0.66.0），疑为同一工具不同名

---

## 6. Homebrew Services

```
Name        Status  User         File
mysql@8.0   started allengaller  ~/Library/LaunchAgents/homebrew.mxcl.mysql@8.0.plist
redis       started allengaller  ~/Library/LaunchAgents/homebrew.mxcl.redis.plist
ollama      none                 —
unbound     none                 —
```

---

## 7. Homebrew Casks（3）

| Cask | 备注 |
|---|---|
| cc-switch | AI 模型切换 |
| libreoffice | GUI 已有 `LibreOffice.app`（重复） |
| temurin@8 | JDK 8 |

---

## 8. Node.js 全局包

| 包 | 版本 |
|---|---|
| `@qwen-code/qwen-code` | 0.18.3 |
| `@tencent-ai/codebuddy-code` | 2.109.1 |
| `mmx-cli` | 1.0.16 |
| `corepack` | 0.34.6 |

---

## 9. Python 全局包（pip3，~50）

### 数据 / 文档
beautifulsoup4, lxml, cssselect2, soupsieve, python-docx, python-pptx, xlsxwriter, markdownify, markitdown, markdown, weasyprint, pydyf, reportlab, tinyhtml5, tinycss2, PyYAML

### 图像 / 视觉
pillow, matplotlib, contourpy, kiwisolver, cycler, fonttools, pyparsing, magika

### ML / 数据科学
numpy, onnxruntime, mlx, jq

### 网络 / 协议
requests, urllib3, certifi, idna, charset-normalizer, cffi, pycparser

### 其他
protobuf, flatbuffers, brotli, zopfli, python-dateutil, python-dotenv, click, defusedxml, packaging, typing_extensions, six, webencodings

---

## 10. `~/.local/bin` 自建 CLI（25）

`claude` · `grok` · `kimi-cli` · `kimi-legacy` · `kimiim-cli` · `hermes` · `cursor` · `cursor-agent` · `droid` · `cua-driver` · `agent` · `news4coder` · `nn` · `oc-skills` · `skillhub` · `qodercli` · `uv` · `uvx` · `python3.11` · `node` · `npm` · `npx` · `env` · `env.fish`

---

## 11. `~/go/bin` Go 工具

`dlv` · `gopls` · `golangci-lint` · `buf` · `controller-gen` · `protoc-gen-go` · `news4coder`（与 `~/.local/bin` 重复）

---

## 12. 严格核验后的结论

1. **Wukong.app 是钉钉 Real**，不是黑神话悟空。建议重命名为 `DingTalkReal.app`，避免误启动。
2. **"Claw" 系 6 个应用，分属 4 个不同厂商**：智谱（AutoClaw）、阿里云（JVS Claw）、腾讯（QClaw）、小鹅通（XETClaw）、EasyClaw（独立）、PocketClaw（独立）—— **不是一个产品系列**，做选型矩阵时要分别评估。
3. **国产 App 不爱声明 LSApplicationCategoryType**：72/192 未声明，占 37.5%。我手动按用途归到对应类目，但不要做权威依赖。
4. **IDE/编辑器实际数量 14 个**（不是 18）：Antigravity, Chaterm, Cherry Studio, CodeBuddy, Codex, Cursor, HBuilderX, Qoder, Qoder CN, Sublime Text, Trae, Trae CN, TRAE SOLO, Visual Studio Code, Windsurf, WorkBuddy, ZCode, Zed（外加终端 Warp/electerm/OrcaTerm/Termius）。其中 Antigravity 是 Google 的 AI 编程 IDE（2025 年发布）。
5. **Marvis 不是音乐播放器**，是腾讯的开发者工具（com.tencent.mac.marvis，category=developer-tools）。我之前归错。
6. **VideoFusion-macOS = 剪映专业版 / CapCut**（ByteDance）。归类应在"视频"。
7. **Muse 显示名是 Allume**，可能是 App Store 版移植（museios-appstore）。
8. **Shroomy 显示名是 Shroomy，但 Bundle Name 是 Reset**，是 uk.co.resetapp.reset 的产品。
9. **crush 与 multica 同源**（都是 0.66.0），怀疑是 `multica` 这个 brew formula 内部 alias。

---

## 13. 后续行动

- [ ] 把 `Wukong.app` 重命名为 `DingTalkReal.app`（避免误启动）
- [ ] 把 6 个 "Claw" 应用做厂商-功能矩阵（4 厂商 vs 6 产品）
- [ ] 把 14 个 IDE / 编辑器做收敛评估，保留 2-3 个
- [ ] 卸载 `unbound`（未运行）+ 评估 `crush` 与 `multica` 是否合并
- [ ] `~/Applications` 的 5 个里，3 个是"应用容器"（Chrome Apps / Quark Apps / Tabbit Apps），Claude Code URL Handler 是协议处理器，Factorio 是游戏
- [ ] `~/Documents/claw/local-apps-2026-06-25.md` 关联到 `proposals/` 下"AI Native Team"选型章节
