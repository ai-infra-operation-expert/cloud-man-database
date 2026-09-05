# Mac 工具链盘点 · 2026-06-25

> **目的**:沉淀现状 → 砍重复 → 腾出"AI Native 个人工作流"的清晰度
> **方法**:实际系统扫描(不看感觉,看清单)
> **复盘周期**:每月一次 + 装/删任何 app 时回填
> **原则**:**每个 app 必须能回答"为啥要装"** — 否则就删

---

## 0. 摘要

| 维度 | 数字 | 评价 |
|---|---|---|
| `/Applications` 下的 GUI app | **193** | 🔴 严重过载(健康:50-80) |
| Homebrew formulae | 122 | 🟡 多但合理(开发机常态) |
| Homebrew casks | 3 | ✅ 克制 |
| `~/Library/Application Support` 占用 top1 | Google 11G | 🔴 同步盘堆积 |
| 占用 top2 | Qoder 10G | 🔴 装了没怎么用 |
| 占用 top3-5 | pcsuite 2.3G / Steam 2.2G / Trae 1.2G | 🔴 候选删除 |
| **Top 15 总占用** | **~36 GB** | 大头在 Google/Qoder/游戏/AI 客户端 |

**一句话结论**:193 个 GUI app 中,真正每天用的 **20-25 个**,周用的 **30-40 个**,剩下 **100+ 个重叠/闲置**。

---

## 1. 主力栈(🟢 必留,每天用)

按角色分组,每组 3-6 个核心,不加塞。

### 1.1 AI 对话 & 编码
- **Claude** — 主力对话 + 思考
- **Cursor** — 主力 AI IDE
- **Codex** — OpenAI 备份
- **VS Code** — 兜底编辑器(.yaml/.json/md)

### 1.2 终端 & K8s
- **Warp** — 主力终端
- **Docker** — 跑 GPUStack server
- **kubectl** — 已有 ✅
- **gh** — 已有 ✅(GitHub CLI)
- **tmux / fzf / fd / ripgrep / zoxide** — 已有 ✅

### 1.3 工作通信
- **WeChat** — 个人
- **钉钉** — 阿里云工作
- **Lark(飞书)** — 部分团队
- **Slack** — 海外/技术社区
- **腾讯会议** — 客户

### 1.4 知识 & 待办
- **Notion** — 团队文档/PM
- **Obsidian** — 个人知识库(本工作区)
- **Things3** — 待办
- **极客时间** — 技术学习(这 1 个真值得留)

### 1.5 浏览器 & 存储
- **Chrome** — 主力
- **百度网盘** — 国内客户文件
- **OneDrive** — 跨设备同步

---

## 2. 🟡 留着但少用(允许存在,不主动开)

| 类别 | app | 备注 |
|---|---|---|
| 笔记 | Bear / Ulysses / Typora | 跟 Notion/Obsidian 重叠,但 1 个快速记录用 |
| 下载 | qbittorrent / aDrive | 看实际用频 |
| 音乐 | 网易云 / QQ音乐 / 汽水音乐 | 留 1 个最常用的 |
| 阅读 | 微信读书 / Kindle | 通勤/出差用 |
| AI 备份 | Manus / Cherry Studio / Kimi / Doubao / Qwen | 选 2-3 个深度用,其他归档 |
| 监控 | CleanMyMac_5_MAS | 偶尔清一下 |
| 切换 | CC Switch | Claude/Codex 配置切换 |

---

## 3. 🔴 建议删除(回收空间 + 减少干扰)

### 3.1 AI 工具爆炸(15+ 个重叠,这是最该砍的)

**主力 3 件套已经够**:
- ✅ Cursor / Claude / Codex

**建议批量删**:
- ❌ **字节 Trae 系列**:Trae / Trae CN / TRAE SOLO(3 个,留 1 个试)
- ❌ **腾讯 Qoder 系列**:Qoder / Qoder CN / QoderWork / QoderWake / ZCode(5 个,功能重叠,全删,主力用 Cursor)
- ❌ **腾讯系**:CodeBuddy / Comate
- ❌ **海外系**:Windsurf / Copilot(海外 AI IDE)
- ❌ **AI Agent 系**:Monica / Manus / CoPaw / Bolt / Hermes / Kick / Start / Antigravity / AutoClaw(15+ 个 Agent 工具,留 1-2 个深度用)
- ❌ **国内 AI 客户端**:ima.copilot / ERNIE / Kimi / Doubao / Qwen / 元宝 / 阶跃AI / 秘塔AI搜索 / 秘塔回响 / 纳米AI / 扣子(11 个,选 1 个网页版 + 1 个 app 即可)
- ❌ **"Claw" 系列**:QClaw / PocketClaw / JVS Claw / XETClaw / easyclaw(本地 claw 多是早期试水,云端用 OpenClaw 就够)

> **理由**:15+ 个 AI 工具都装,实际用 3 个,其他 12 个就是**"装了不用,占心智"**。每个 app 都是一个 decision point,装多了反而不知道该用哪个。

### 3.2 终端重复(4 个,1 个就够)

- ✅ **Warp** 留
- ❌ **OrcaTerm** / **Termius** / **electerm** / **Chaterm**(挑 1 个远程用,其他全删)
  - 如果是 SSH 远程管理:Termius 同步最好
  - 如果是云控制台:OrcaTerm 阿里云集成好

### 3.3 浏览器(Chrome 已经够)

- ✅ **Chrome**
- 🟡 **Safari**(macOS 原生,部分 Apple 生态场景保留)
- ❌ **Edge**(Mac 上 Edge 多余,微软系服务用 Chrome 也能跑)
- ❌ **Comet**(Perplexity 浏览器,Chrome 扩展替代)
- ❌ **Tabbit / Tabbit Browser / Tabbit Apps.localized**(没看出不可替代性)

### 3.4 通讯(按需)

- ✅ **WeChat / 钉钉 / Lark / Slack / 腾讯会议** 留
- 🟡 **Telegram / Discord / Signal / LINE / WhatsApp** — 看私域用频,最多留 1-2 个
- ❌ **BOSS直聘** / **脉脉**(找工作才用,不用就删)
- ❌ **MailMaster**(Chrome 邮件客户端就够)

### 3.5 娱乐(空间大头)

- ❌ **Steam**(2.2G) — 不玩就删
- ❌ **Stardew Valley** / **Factorio** / **暗黑破坏神III** / **WeGame** / **TapTap** / **小黑盒**(游戏/手游平台,Mac 体验一般)
- 🟡 **视频**:B 站 / 优酷 / 爱奇艺 / 人人视频 / 抖音 / 快手 / 小红书 — **挑 1-2 个,Mac 视频体验都一般**
- 🟡 **音乐**:网易云 / QQ音乐 / 汽水音乐 / 喜马拉雅 / 小宇宙 — **留 1 个**

### 3.6 知识囤积陷阱(你的"想读"陷阱)

- ❌ **三联中读** / **一席** / **读库** / **盐言故事** / **壹心理** / **每日瑜伽** / **每日英语听力** — 真有时间看吗?
- ❌ **语雀** / **Get笔记** / **有道云笔记** — 跟 Notion/Obsidian 重叠
- ❌ **DuckDuckGo** / **Grammarly for Safari** / **Calm** / **Headspace** / **Endel** / **Singing Bowls** / **Dark Noise** / **潮汐** — 看你的冥想/白噪音用频

### 3.7 系统工具

- ❌ **Applite**(Homebrew GUI,有 cask 命令就行)
- 🟡 **CleanMyMac_5_MAS**(可留可删,半年用 1 次)
- ❌ **Clash Verge**(代理工具,看你实际用哪个节点)

---

## 4. 📦 接下来给 GPUStack / AI Stack 工作该装的清单

> 这次盘点后,补齐真正缺的工具。

### 4.1 K8s 日常(你 Mac 控 N 个集群用)

```bash
brew install k9s krew helm kubectx stern
```

- `k9s` — 终端 K8s dashboard
- `krew` — kubectl 插件管理
- `helm` — K8s 包管理
- `kubectx` — 快速切 context/namespace
- `stern` — 多 Pod 日志聚合

### 4.2 现代 CLI 替换(补齐你已有的)

```bash
brew install eza bat jq yq btop glances bandwhich
```

| 命令 | 替换 | 用途 |
|---|---|---|
| `eza` | `ls` | 更好看的列表 |
| `bat` | `cat` | 带语法高亮 |
| `jq` / `yq` | 手撸解析 | JSON/YAML 解析 |
| `btop` | `top` | 系统监控 |
| `glances` | `htop` | 跨平台监控 |
| `bandwhich` | — | 看流量被谁吃了 |

### 4.3 LLM 部署相关

- ✅ **Ollama** 已有(brew 也有,但 app 也装了 — 重复)
- 🔧 **Python 3.12 venv**(为 gpustack server 用)
- 🔧 **llama.cpp**(用 brew 或自己编译)

### 4.4 AI Coding 配套

- ✅ **opencode** 已有
- ✅ **cline** 已有
- 🟡 **aider**(可选,CLI AI pair 备份)

---

## 5. 🛠 落地计划

| 时点 | 行动 | 预期回收 |
|---|---|---|
| **今天** | 删 Steam + 暗黑 3 + 几个明显不用的游戏 | ~3G |
| **本周** | 批量删 AI 工具重复的 30+(Trae/Qoder/Agent 系/Claw 系) | ~15G(主要是 Qoder) |
| **本月** | 终端/浏览器/知识囤积 20+ 个 | ~5G |
| **每月** | `brew autoremove` + 看 `~/Library/Application Support` top 5 | 持续 |

**总预期回收:25-30 GB 磁盘 + 显著降低工具选择焦虑**

---

## 6. 复盘节奏 & 维护建议

1. **每月 1 号**:跑一遍扫描命令,看新装了啥/没用的有啥
2. **每装一个新 app**:在 `~/Documents/claw/memory/YYYY-MM-DD.md` 写一行"为啥装"
3. **每季度**:把工具栈跟工作流匹配,问"这个 app 帮我省了多少时间?"

---

## 7. 复现这份报告的命令(供下次直接跑)

```bash
# GUI apps
ls -1 /Applications 2>/dev/null

# Homebrew
brew list --formula
brew list --cask

# 存储占用 top 15
du -sh ~/Library/Application\ Support/* 2>/dev/null | sort -rh | head -15

# 启动项
osascript -e 'tell application "System Events" to get the name of every login item'

# 关键 CLI
for cmd in docker kubectl helm k9s colima podman orbstack lazygit tig \
  btop htop ripgrep fd bat eza zoxide fzf tldr tmux gh glab \
  aider cline opencode cursor; do
  command -v "$cmd" >/dev/null 2>&1 && echo "✅ $cmd"
done
```

---

## 附:本次扫描的存储 top 15(快照)

| 占用 | 应用 | 类型 | 处理建议 |
|---|---|---|---|
| 11G | Google | 同步盘 | 检查 Drive 同步设置 |
| 10G | Qoder | AI IDE | 🔴 删(用 Cursor) |
| 2.3G | pcsuite | 华为手机套件 | 🟡 看用频 |
| 2.2G | Steam | 游戏平台 | 🔴 删 |
| 1.4G | Microsoft | Edge/Office 缓存 | 🟡 清缓存 |
| 1.2G | Trae | AI IDE | 🔴 删(字节系) |
| 1.2G | Code | VS Code | ✅ 留 |
| 1.0G | kimi-desktop | AI 客户端 | 🟡 归档 |
| 972M | Quark | 办公 | 🟡 看用频 |
| 968M | CodeBuddyExtension | AI 扩展 | 🔴 删 |
| 819M | QoderCN | AI IDE | 🔴 删 |
| 810M | autoclaw | AI 工具 | 🔴 删 |
| 743M | CodeBuddy | AI IDE | 🔴 删 |
| 725M | Lingma | 通义灵码 | 🟡 留 1 个国产 IDE 备 |
| 538M | com.tencent.imamac | 微信 | ✅ 留 |

---

*最后更新:2026-06-25 23:50*
*下次复盘:2026-07-01*
*创建者:Allen + OpenClaw(MiniMax-M3)协作*
