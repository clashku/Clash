<div align="center">
  <a href="https://github.com/clashku/Clash" title="从旧 Clash 迁到维护中客户端">
<img width="150" height="150" alt="Clash" src="https://github.com/user-attachments/assets/22b7cf80-912f-4a19-96fb-521f72c88d8a" />

  </a>
  <h1>从旧 Clash 迁到维护中客户端 (2026年11月更新)</h1>
  <p>
    <b>迁移动因、步骤与新旧对照；安装包仍走官方 Releases</b>
  </p>
  <p>
    <img src="https://img.shields.io/badge/Update-2026.11-brightgreen.svg" alt="Update">
    <img src="https://img.shields.io/badge/Platform-Win%20%7C%20Mac%20%7C%20iOS%20%7C%20Android%20%7C%20Linux-blue.svg" alt="Platform">
    <img src="https://img.shields.io/badge/Ecosystem-Clash%20%7C%20Mihomo%20%7C%20Sing--box%20%7C%20Xray-orange.svg" alt="Ecosystem">
  </p>
</div>

如果你觉得这个项目对你有帮助，欢迎点右上角的**Star**⭐ 支持一下！

[代理雷达](https://github.com/guiforcores/dailileida)：每日追踪 mihomo、sing-box、Xray、V2Ray、Clash 及自研内核的代理客户端：开源项目看 GitHub Star，商店应用看美区 App Store / Google Play 评分数。

本页按 **从旧 Clash 迁到维护中客户端** 来写：先讲为什么要迁、迁什么、怎么迁，再给出维护中下载与节点入口。教程域名以 [clashku.com](https://clashku.com/) 为准；安装包以各项目 GitHub Releases（或本页标明的备份仓）为准。标题里的 `YYYY年M月更新` 与徽章 `Update-YYYY.MM` 请保持原格式，由例行任务改日期。

---

## 为什么还要「迁移」

早年大家说的 Clash，多数是指 **Clash for Windows / ClashX / Clash for Android** 这一代图形客户端。上游核心与若干经典 GUI 已停更或不再公开维护，继续用旧安装包会遇到：

- 新协议、新订阅字段对不上，导入失败或节点测速全红  
- 缺少安全修复与系统适配（新版 Windows / macOS / Android）  
- 网上流传的「破解包 / 整合包」来源混乱，风险高于官方 Releases  

迁的目标不是换一个「更花哨的名字」，而是换到 **仍有公开 Releases、仍在修 bug** 的 Meta / Mihomo 系前端（以及少数多内核客户端）。本仓备份旧客户端，只为对照与应急，不建议当作日常主用。

---

## 三分钟 TL;DR

1. **先备份**：导出旧客户端里的订阅 URL、自定义规则、系统代理/TUN 开关习惯。  
2. **按旧客户端对号入座**（见下一节迁移对照），只装 **一个** 维护中客户端。  
3. **从官方 Releases 下载**，打开 clashku.com 对应教程完成首次导入。  
4. **验证**：订阅能刷新 → 至少一个节点可用 → 浏览器走代理正常。  
5. **再卸载旧版**，避免两个工具抢系统代理。

还没装过任何 Clash、只是来找下载？直接跳到 [维护中客户端索引](#维护中客户端索引)，按平台选一个即可。

---

## 旧版 → 新版迁移对照

按你现在用的旧软件选一条线即可，不必每个都试。

### 你在用 Clash for Windows（CFW）

- **常见去向**：[Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev/releases)、[Clash Party](https://github.com/mihomo-party-org/clash-party/releases)、[FlClash](https://github.com/chen08209/FlClash/releases)、[Clash Nyanpasu](https://github.com/LibNyanpasu/clash-nyanpasu/releases)  
- **迁什么**：Profiles 里的订阅链接；本地改过的 `config.yaml` / 规则片段；开机自启与系统代理习惯  
- **注意**：CFW 的部分主题、托盘插件、第三方「去广告包」不能原样带到新客户端；规则以订阅或新客户端的覆写（override）为准  
- **旧备份 / 教程**：[备份仓](https://github.com/clashku/Clash-for-Windows) · [教程](https://clashku.com/clash-for-windows/)  
- **新教程入口**：[clash-verge](https://clashku.com/clash-verge/) · [clash-party](https://clashku.com/clash-party/) · [flclash](https://clashku.com/flclash/) · [clash-nyanpasu](https://clashku.com/clash-nyanpasu/)

### 你在用 ClashX（原版）

- **常见去向**：[ClashX Meta](https://github.com/MetaCubeX/ClashX.Meta/releases)（菜单栏体验量）；需要完整桌面 UI 时改用 Verge Rev / Party / FlClash  
- **迁什么**：订阅 URL、选中的策略组、是否开启增强模式 / 系统代理  
- **注意**：原版 ClashX 与 Meta 版配置并不保证 100% 互通；导入失败时改「用订阅链接重建」通常比硬拷配置目录更省事  
- **旧备份 / 教程**：[备份仓](https://github.com/clashku/ClashX) · [教程](https://clashku.com/clashx/)  
- **新教程**：[clashx-meta](https://clashku.com/clashx-meta/)

### 你在用 Clash for Android

- **常见去向**：[Clash Meta for Android](https://github.com/MetaCubeX/ClashMetaForAndroid/releases)、[FlClash](https://github.com/chen08209/FlClash/releases)、[Clash Mi](https://github.com/KaringX/clashmi/releases)  
- **迁什么**：订阅链接、绕过列表 / 分应用代理名单、是否始终开启 VPN  
- **注意**：旧版 APK 与 Meta 版数据目录不同；建议新装后重新添加订阅，再按需重做分应用规则  
- **旧备份 / 教程**：[备份仓](https://github.com/clashku/Clash-for-Android) · [教程](https://clashku.com/clash-for-android/)  
- **新教程**：[meta-for-android](https://clashku.com/clash-meta-for-android/) · [flclash](https://clashku.com/flclash/) · [clash-mi](https://clashku.com/clash-mi/)

### 你在用原版 Clash Verge / ClashN

- **Clash Verge（原版）** → 优先迁到社区继续维护的 [Clash Verge Rev](https://github.com/clash-verge-rev/clash-verge-rev/releases)；旧发布页仅作对照：[zzzgydi/clash-verge](https://github.com/zzzgydi/clash-verge/releases) · [clashverge.org](https://clashverge.org/)  
- **ClashN** → Windows 上改选 Verge Rev / Party / FlClash / Nyanpasu；旧页：[2dust/clashN](https://github.com/2dust/clashN/releases) · [getclashn.org](https://getclashn.org/)

### 你要多端统一（电脑 + 手机）

优先同一产品线，减少「每台设备一种界面」的学习成本：

- [Clash Mi](https://github.com/KaringX/clashmi/releases) · [教程](https://clashku.com/clash-mi/)  
- [Hiddify](https://github.com/hiddify/hiddify-app/releases) · [教程](https://clashku.com/hiddify/)

---

## 迁移操作清单（建议按序）

把下面当成迁仓检查单；完成一项勾一项即可。

1. **在旧客户端里复制订阅**  
   打开 Profiles / 配置页，把订阅 URL 存到密码管理器或备忘录。若只有本地 YAML、没有 URL，导出整份配置文件。

2. **记下非默认行为**  
   系统代理还是 TUN / 增强模式；是否开机启动；是否有自定义 DNS、绕过大陆、分应用列表。这些在新客户端里通常要手动再开一次。

3. **只装一个新客户端**  
   从下方「维护中客户端索引」点进 **GitHub Releases**，按系统与架构取安装包。不要并行安装多个会抢代理的 GUI。

4. **首次导入**  
   用订阅 URL 添加配置并更新；失败再试「下载 YAML 后本地导入」。教程按客户端打开 clashku.com 对应页。

5. **连通性验收**  
   更新订阅 → 延迟测试至少一个节点 → 浏览器访问需代理的站点。异常时先换节点，再换网络，最后才怀疑客户端。

6. **确认无冲突后卸旧版**  
   退出并卸载 CFW / 旧 ClashX / 旧 Android 客户端，避免残留系统代理或 VPN 配置抢流量。

7. **（可选）规则覆写**  
   旧客户端里手改的规则，迁到新客户端的 override / 覆写功能中维护，避免下次订阅一更新就被盖掉。

---

## 维护中客户端索引

下列均有公开维护动态；**下载以 Releases 为准**，教程指向 clashku.com。

| 客户端 | 平台 | 下载 | 教程 |
|:-------|:-----|:-----|:-----|
| Clash Verge Rev | Windows / macOS / Linux | [Releases](https://github.com/clash-verge-rev/clash-verge-rev/releases) | [教程](https://clashku.com/clash-verge/) |
| Clash Party | Windows / macOS / Linux | [Releases](https://github.com/mihomo-party-org/clash-party/releases) | [教程](https://clashku.com/clash-party/) |
| Clash Mi | Windows / macOS / Linux / iOS / Android | [Releases](https://github.com/KaringX/clashmi/releases) | [教程](https://clashku.com/clash-mi/) |
| ClashX Meta | macOS | [Releases](https://github.com/MetaCubeX/ClashX.Meta/releases) | [教程](https://clashku.com/clashx-meta/) |
| Clash Meta for Android | Android | [Releases](https://github.com/MetaCubeX/ClashMetaForAndroid/releases) | [教程](https://clashku.com/clash-meta-for-android/) |
| FlClash | Windows / macOS / Linux / Android | [Releases](https://github.com/chen08209/FlClash/releases) | [教程](https://clashku.com/flclash/) |
| Hiddify | Windows / macOS / Linux / iOS / Android | [Releases](https://github.com/hiddify/hiddify-app/releases) | [教程](https://clashku.com/hiddify/) |
| Clash Nyanpasu | Windows / macOS / Linux | [Releases](https://github.com/LibNyanpasu/clash-nyanpasu/releases) | [教程](https://clashku.com/clash-nyanpasu/) |

补充（同样请走官方 Releases）：

- [Bettbox](https://github.com/appshubcc/Bettbox/releases) · [getbettbox.org](https://getbettbox.org/)  
- [ClashBox](https://github.com/xiaobaigroup/ClashBox/releases) · [clashbox.org](https://clashbox.org/)  
- [Sparkle](https://github.com/xishang0128/sparkle/releases) · [getsparkle.org](https://getsparkle.org/)

站内汇总：[Clash Releases](https://clashku.com/clashreleases/)

---

## 停更客户端（仅备份对照）

新环境请用上一节。下列链接方便你对照旧界面或应急翻配置，**不要当作默认安装来源**。

| 客户端 | 平台 | 备份 / 旧发布 | 教程 |
|:-------|:-----|:--------------|:-----|
| Clash for Windows | Windows / macOS / Linux | [备份](https://github.com/clashku/Clash-for-Windows) | [教程](https://clashku.com/clash-for-windows/) |
| ClashX | macOS | [备份](https://github.com/clashku/ClashX) | [教程](https://clashku.com/clashx/) |
| Clash for Android | Android | [备份](https://github.com/clashku/Clash-for-Android) | [教程](https://clashku.com/clash-for-android/) |
| Clash Verge（原版） | Windows / macOS / Linux | [Releases](https://github.com/zzzgydi/clash-verge/releases) | [clashverge.org](https://clashverge.org/) |
| ClashN | Windows | [Releases](https://github.com/2dust/clashN/releases) | [getclashn.org](https://getclashn.org/) |

---

## 节点与订阅（客户端装好之后）

客户端解决「怎么连」；节点来自你自己的订阅。下列入口请自行甄别稳定性、退订与合规条款：

| 名称 | 一句话 | 链接 |
|:-----|:-------|:-----|
| 扬帆云 | IPLC 专线向，流媒体 / AI 向 | [优惠入口](https://clashku-github.affout.com/yangfanyun/) |
| 疾风云 | 性价比 IPLC，晚高峰向 | [优惠入口](https://clashku-github.affout.com/jfcloud/) |
| 大哥云 | 老牌中转隧道 | [优惠入口](https://clashku-github.affout.com/dageyun/) |
| 龙猫云 | 高品质 IPLC 加密隧道 | [优惠入口](https://clashku-github.affout.com/totorocloud/) |
| 肥猫云 | 专线中转，设备数较宽 | [优惠入口](https://clashku-github.affout.com/fatcatcloud/) |

更多整理：

- [Clash订阅节点推荐](https://github.com/clashku/ClashNode)  
- [Clash机场推荐](https://clashku.com/node/)

迁仓时建议：**先在新客户端用原订阅验证**，再考虑换服务商；不要把「换机场」和「换客户端」两件事同一天搅在一起，出问题难排查。

---

## 迁移时常见卡点

**订阅在旧软件能用，新软件更新失败**  
检查链接是否被复制截断、是否需要客户端内代理拉取、机场是否限制 User-Agent。可改为浏览器下载 YAML 再本地导入。

**有节点但浏览器仍直连**  
确认新客户端已开启系统代理或 TUN，且旧客户端已完全退出。macOS / Windows 可在系统网络设置里看是否残留旧 VPN / 代理。

**延迟全超时**  
先换同订阅下其它地区节点；仍全红则多半是订阅或上游问题，与「刚换的 GUI」无关。

**标题写着 2026年11月更新，是不是软件也是这个月发的？**  
不是。那是本 README 的整理月份；客户端版本以各自 Releases 的 Tag 为准。

**OpenWRT / 软路由要跟着桌面一起迁吗？**  
路由器插件与桌面 GUI 通常分开维护。桌面迁完后，路由侧按固件文档更新 mihomo / 同类核心，配置单独备份。

---

## 本仓怎么用

1. 仍在用 CFW / 旧 ClashX / 旧 Android → 从 [旧版 → 新版迁移对照](#旧版--新版迁移对照) 选一条线，再走 [迁移操作清单](#迁移操作清单建议按序)。  
2. 已经决定目标客户端 → 在 [维护中客户端索引](#维护中客户端索引) 进 Releases，再开对应教程。  
3. 需要订阅 → [节点与订阅](#节点与订阅客户端装好之后)；不要把机场页当成客户端官网。  
4. 改文案时保留日期格式 `YYYY年M月更新` 与 `Update-YYYY.MM`，方便例行任务自动更新。

---

## 免责声明

本仓库仅汇总公开客户端、备份对照与教程链接，不提供翻墙服务，不保证第三方节点可用性或合法性。请遵守当地法律法规与各应用商店、仓库的许可条款。下载请以官方 Releases / 商店页面为准；本页维护月份不代表任何客户端的发版承诺。因下载、安装、配置或使用第三方软件产生的风险由使用者自行承担。

---

如果本页对你完成迁移有帮助，欢迎点右上角 **Star** ⭐ 支持一下。
