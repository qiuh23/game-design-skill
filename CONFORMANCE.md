# 三款游戏反向符合度报告

核对日期：2026-11-16。依[新游戏清单](templates/new-game-checklist.md)及各 reference 反向检查三个固定主分支快照。这里的「不符合」是相对新规范草案的差距，不等于旧任务做错，也不授权修改游戏。检查方法为读取源码、样式、设计文档、版本配置和可追溯的历史交付记录；这次没有重跑游戏测试、部署、浏览器或真机，不能据此确认所有点击区域、最终级联观感与无滚动首屏。没有修改三个游戏仓库。

## 总览

| 检查项 | 胡闹运动会 | 巫师牌 | 卡坦岛 |
| --- | --- | --- | --- |
| 1. 独立视觉身份 | 嘉年华场景与主题色可证。 | 烛光深青金与专属显示字体可证。 | 海岸桌面与资源色可证。 |
| 2. 同步 DESIGN | 缺现行根文档；旧入口草稿与新标尺冲突。 | 无 DESIGN.md；阶段记录不是同步规范。 | CSS 与 JSON 基础 token 逐值一致；DESIGN 残留旧首页复位/恢复，焦点规范与 CSS 不一致。 |
| 3. Token 与尺度 | 主要自定义变量单文件；字号/字重/药丸圆角仍有组件散值。 | 语义色主要收拢；另有全局布局变量、组件散值与较多断点。 | 有单一数值表，组件仍写语义白色、10px 圆角等；焦点有 3px/3px 等不同声明。 |
| 4. 首页与词表 | 纯图标规则入口但名称不同；加入是内嵌面板，未按目标降级恢复和公开房间。 | 源码已有三格、独立加入窗及次级入口；规则、公开房间空状态仍非逐字一致。 | 舞台、紧凑坞和 #39 的 2D/3D 符合参照；开桌/加入仍合并，昵称和恢复在弹窗，在线房间占主格。 |
| 5. 房间与对局 | 房间码可复制；返回大厅与退出分离，但对局中改到菜单。 | 唯一返回箭头与房内确认已实现；房间码不可点复制，即时邀请、退出未统一到顶栏。 | 房间码不可点复制，存在其他大厅链接，确认文案和实际保留规则需按身份/阶段区分。 |
| 6. 线路与大厅 | 两套线路和策略可追溯；大厅源配置覆盖三款。 | 两站构建与分流代码可追溯。 | 两站构建与分流代码可追溯。 |
| 7. 双站发布 | [#86](https://github.com/qiuh23/magical-athlete-online/pull/86) 回退对齐；此轮只读，不重新部署。 | [#57](https://github.com/qiuh23/wizard-friends/pull/57) 按范式改完并上线；此轮只读。 | [#39](https://github.com/qiuh23/catan-friends/pull/39) 小改上线；此轮只读。 |
| 8. Qiu 真机确认 | 附件指定范式已获认可，不外推每条新目标。 | #56 顶栏等裁决获认可；没有确认 #57 的真机验收，不作原始模板。 | 附件指定简洁范式；不外推为 #39 或其他区域已逐条验收。 |
| 9. 索引回写 | 已记录来源和旧文档。 | 已记录来源与待验范围。 | 已记录来源、规范文档和实现差异。 |

## 裁决与冲突

- **已验收的设计原则不等于现网逐条合规。** 卡坦与运动会是范式来源，仍可能不符合此后提炼的独立进房、词表与顶栏规格；巫师牌 #57 是范式的应用实例。
- **单人入口的玩法可等价，主按钮词表按更严格的逐字条款。** 因而保留「人机练习」等模式，不把现行卡坦按钮文字误记为「单人练习」。
- **弹窗三种关闭是此次目标，不回改强制决策。** 卡坦局内强制决策的遮罩有规则限制，作为例外报告；如需调整，须把展示与规则分别讨论。
- **数字追溯到真实声明。** 旧 160ms 和旧 10px 下限不覆盖卡坦现行 180ms／11px；语义色一义一值，装饰色不计数量。卡坦焦点以规范目标 2px/2px 记载，并将真实 CSS 偏差单独列明。


## 胡闹运动会：细项与证据


2026-11-16；仓库 public，main = `7e542f72d6affae64a7bed39e723dd89d36d5898`。全新浅克隆 + 静态源码逐项读取，未运行游戏/构建、未改游戏代码，git status 干净。仅证明代码声明，不代替真机视觉与交互验收。

固定快照：[源码与文件树](https://github.com/qiuh23/magical-athlete-online/tree/7e542f72d6affae64a7bed39e723dd89d36d5898)；下文文件和行号均以该版本为准。

### 精确标尺与身份

`src/client/ui-theme.css#L26-L73`：字体系统栈 `-apple-system, BlinkMacSystemFont, "PingFang SC", "Microsoft YaHei", system-ui, sans-serif`；展示 `"Arial Black", var(--ui-font)`；印刷 `Georgia, "Times New Roman", serif`；阅读 `"Noto Serif SC", "Songti SC", "STSong", "SimSun", serif`。

文字 `#25464c`，次级 `#5b7268`，纸面 `#fffdf4`，品牌黄 `#ffda27`、红 `#f44735`、蓝 `#254de4`、绿 `#b5d66b`、粉 `#f6a8d0`；surface `rgba(255,253,244,.96)`；control `#f2f1e5`；hover `#fff2bf`；active `#e5edda`；border `#c0cbb7`；control-border `#9caf9f`；accent/focus `#254de4`；gold `#b57422`。

圆角 token 8/12/14px（999px 仍是组件字面量）；space 4px；阴影 1=`0 2px 8px rgba(35,73,65,.10)`，2=`0 8px 24px rgba(35,73,65,.18)`，3=`0 16px 48px rgba(35,73,65,.26)`；另有风格性 hard=`3px 4px 0 #25464c`；z 0/10/20/30/40/50/60；duration 120/180/240ms；touch 44px。reduced-motion 在同一文件 L283 覆盖三时长为 0ms。焦点环 L87-L90 为 2px solid focus，offset 2px。

全 `src/client/**/*.css` 显式 font-size 字面值扫描：0、11/12/13/14/16/18/20/24/32px，另标题 clamp 上限96px；font-weight 400/500/600/700/800。是源码扫描，不是所有渲染字号统计。媒体查询宽度档 650/1000/1280px，高度档 350/480/500/570/571/600px（571 为 min-height）。不要将 max-width/min-height 普通属性误算成断点。

大厅特例 `ui-theme.css#L1-L24` 的 @lobby-baseline 列原大厅值与150ms，供 scripts/build-lobby.mjs 生成 fallback，不能用游戏180ms冒称大厅现值。用户此前明确大厅视觉保持原样。

### 逐项符合度

| 检查项 | 结论 | 证据/差距 |
|---|---|---|
| 独立视觉身份 | 源码支持 | 黄色嘉年华、角色舞台，App.tsx L344 与 token L26-L73；不可声称本轮真机验收 |
| token 单源 | 部分符合 | 自定义变量的 :root 声明集中 ui-theme.css（常态+减动）；styles.css L3 的 :root 只有普通属性，不应误报第二 token 源。字号/字重/999圆角仍散布字面量，不是“全部语义值 token 化” |
| 同步 DESIGN.md | 不符合新结构 | 根目录无 DESIGN.md；仅 docs/qa/entry-design/DESIGN.md，旧文档无 YAML frontmatter，仍写圆角10–12/14–16、正文14–16、标题25–40、返回大厅文字入口、手机可纵向滚动，与新附件冲突，不可冒称现行统一标尺 |
| 首屏顶栏 | 部分符合 | App.tsx L223 有正确 aria-label/title 返回游戏大厅，但按钮在右侧 nav，不在左侧品牌前；规则图标 aria-label/title 是“规则”而非词表“玩法规则” |
| 舞台主导 | 源码支持，视觉待验 | App.tsx L344；ui-theme.css L148起桌面双列舞台，home-entry.css 有角色主视觉 |
| 三个动作格子 | 部分符合 | App.tsx L351-L356 是创建/加入/自己练习/人机对战四个 tab；home-entry.css 四列，ui-theme 桌面1000px以上两列。不是目标三按钮同排+AI随后；创建 primary 有样式 |
| 加入独立弹窗 | 不符合 | App.tsx L356点击 setConfiguring，L357-L368 在页面内 role=tabpanel 显示表单，不是 Modal |
| 恢复入口降级 | 不符合 | App.tsx L343 首先渲染 OwnedRoomReturn，L406 是继续游戏卡片与按钮，不是小字链接 |
| 在线房间折叠一行 | 不符合 | App.tsx L339/L359 在加入面板嵌入 RoomDirectory，L441 显式列表，无默认折叠；空状态“还没有房间，快去创建第一场运动会吧。”不等于“暂无公开房间” |
| 全站弹窗三关闭 | 通用 Modal 源码符合 | App.tsx L679-L692：遮罩、×、Escape都有；提交中会阻止关闭；加入流程本身不是弹窗 |
| 房间码复制/邀请/退出 | 部分符合 | App.tsx L225 有可复制房间码及邀请/退出；还有暂停和结束房间。沉浸比赛不渲染这条顶栏，返回大厅位于菜单 L608，不保持全程相同位置/箭头形态 |
| 返回大厅与退出不同 | 符合语义，位置不符合 | requestLobby/Modal App.tsx L251 说明保留与原链接；退出独立L253；非沉浸入口L223，沉浸L608，互斥显示，不应说同屏重复入口 |
| 结算路径 | 部分符合 | App.tsx L629-L634，原房间再来一局与下一场复用现有外壳；主文案不是严格词表“开始游戏” |
| 统一文案 | 部分符合 | 创建/加入/邀请朋友/复制房间码/退出房间/返回游戏大厅存在；自己练习、规则、开始选秀/分配队伍并选人、列表空文案未逐字符合附件 |
| 版本差异 | 源码符合 | vite.config.ts L5-L8 强制 SITE_EDITION cn/global；src/client/site-edition.ts；App.tsx L244 国内不挂 RoomChat、L347-348昵称分流 |
| 房间码前缀 | 符合 | src/client/backends.ts L14-L18：C=cloudflare，A=aliyun |
| 大厅注册/返回线路 | 符合 | lobby/config.json 包含三游戏两线路；src/client/game-lobby.ts CN https://magical-athlete-online.cn/，global https://magical-athlete.qiuh23.workers.dev/lobby/ |
| 44x44/单屏不滚动/遮挡 | 未证明全覆盖 | 核心按钮 ui-theme 有44px，但需实际盒尺寸/视口验证；当前未跑浏览器，不用静态 token 冒称全组件通过 |
| 双站上线/真机认可 | 本轮未复验 | 只读源码任务未运行部署、浏览器或真机；附件将运动会/卡坦列为已验收范式，是用户给定地位，不代表当前每条新规范已经实现 |

### 冲突处理

附件为新规范候选，现有 main 是实际实现。明确区分“目标要求”“源码事实”“用户已验收范式地位”。例如附件标三格、独立加入弹窗、顶栏左返回，而运动会当前尚未全部符合。只记差距，不据此修改游戏。旧 DESIGN 数值不覆盖附件新标尺；最新真机确认范围未给具体 commit 时不自行虚构。


## 巫师牌：细项与证据


核对日：2026-11-16。仓库 `qiuh23/wizard-friends`，public，main `0295faf27338682ad92b30e2c6586ce0063f9b47`（#57）。方法：GitHub metadata + 当前 main 浅克隆；检索并阅读源文件；未改游戏、未运行构建或重做真机验收。克隆工作树干净。以下是代码级核对，不把历史测试或上线当 Qiu 真机验收。#57 暂无明确真机验收证据，首页只能列为「按范式改造完成的实现，待验收」，不是原始模板。

所有文件链接基址：[固定快照](https://github.com/qiuh23/wizard-friends/tree/0295faf27338682ad92b30e2c6586ce0063f9b47)。

### 真实 token 与身份

权威值位于 [src/ui/theme.css L18–89](https://github.com/qiuh23/wizard-friends/blob/0295faf27338682ad92b30e2c6586ce0063f9b47/src/ui/theme.css#L18-L89)。

- UI 字体：`-apple-system, BlinkMacSystemFont, "PingFang SC", "Microsoft YaHei", "Noto Sans SC", system-ui, sans-serif`；标题：`"Noto Serif SC", "Songti SC", serif`；牌面：`Georgia, "Noto Serif SC", serif`。
- 正文 `#f7f4ec`；次要文字 `#b9c4bb`；表面 `rgba(18, 30, 28, .92)`；控件 `rgba(24, 43, 38, .88)`，hover `#2c4a41`，active `#33544a`；边框 `rgba(255, 255, 255, .16)`；控件边框 `rgba(223, 216, 191, .30)`；金色 `#e6c486`；金底文字 `#221b10`；焦点 `#fff4b8`；正分 `#9acbaf`；负分 `#e39782`。烛光深青金身份，桌毡 `#254d49` / `#183933` 与夜色 `#111c25`。
- 字阶 11/12/13/14/16/18/20/24/32px；圆角 token 8/12/14px（999px 胶囊在组件中直接出现，尚无该 token）；间距 token 4/8/12/16/24/32px；阴影 `0 2px 8px rgba(0,0,0,.18)`、`0 8px 24px rgba(0,0,0,.28)`、`0 18px 54px rgba(0,0,0,.42)`；z 0/10/20/30/40/50/60；动效 120/180/240ms；缓动 `cubic-bezier(.2,.7,.3,1)`；触控 44px。
- 400/500/600/700/800 字重是阶段 4 文档的现行档位，尚非独立 weight tokens。焦点全局规则 2px solid + 2px offset，src/ui/theme.css L371–386 有统一 44px 触控尺寸。
- 当前所有 CSS `@media` 条件中的宽度数值：340,359,380,480,580,599,600,601,700,701,800,801,850,851,1100,1500px；高度：280,520,540,541,550,700,800px。方法只提取 @media 条件，不把普通 min-width 属性算断点。其中新版 home-dock 为 359/700px 与短横屏高度 540px，基础 theme 为 480/850px；不能写成全站已收拢到少数几档。

### 逐项核对

|要求|结论|证据 / 差距|
|---|---|---|
|视觉身份独立|代码有实现；真机未验|上列 token 与牌桌主题；不把装饰色数量当失败|
|恰好一个 token 源 + DESIGN.md 同步|不完全符合|语义颜色主要在 src/ui/theme.css；全仓无 DESIGN.md。docs/qa/ui-overhaul/phase-4.md 是阶段记录，不能冒充 DESIGN.md。home-dock.css L3 另外定义全局布局/标题阴影变量；字重/999 圆角/部分间距仍直接写组件。style.css、cinematic.css 的 :root 只消费变量，不应误报为另建色表|
|语义与装饰两分|主要具备，仍需用途审计|theme L23–40,82–89 的角色、兼容别名明确；阶段 4 原装饰保留记录。例 theme L144–145 的 selected/preview 轮廓仍使用 #8ce1ed/#98e4ed 等字面，需确认是否属同一选择语义而非把效果名当豁免；本轮不改|
|尺寸标尺全部单源|部分符合|主要尺度已建 token，但 home-dock L4/21/51 用 z=12/5/6，L27 gap=6px、L61 gap=1px 等非 4 倍数。home-menu L58 有 .15s 过渡声明；theme 更高优先级会覆盖普通按钮，不将其误称最终生效 150ms。断点并未少数档统一|
|常驻顶栏 + 唯一返回箭头|代码符合|src/ui/root.tsx L16–25；chrome.tsx L69–79。LobbyNavigation 全流程仅挂载一次，aria-label/title 精确为 返回游戏大厅|
|主视觉为主、动作区为辅|代码意图符合；视觉待验|home-dock.css L18–39 的全屏场景和底部坞；竖屏高度与软键盘需真机确认，本轮没截图|
|三格按钮、创建唯一 primary、独立加入窗|代码符合|entry.tsx L20–60；home-menu.css L52–67。创建房间/加入房间/单人练习 精确；昵称一行；国内随机昵称图标|
|恢复链接 + 默认收起在线列表|结构符合，文案不符|entry.tsx L34–43，home-dock L41–52；room-directory.js L33 实际 暂无在线房间，不是 暂无公开房间|
|弹窗遮罩/X/Esc|加入、规则、返回确认均有实现|main.js L452–470 / L489–498 + L639 / L726–741；共用 ui/modal.tsx。不能据此声称所有未来弹窗都已符合|
|候场/对局统一外壳及房间码复制|不符|entry.tsx L64–74 房间码是 span，无复制交互；邀请按钮在 room-heading。chrome.tsx L44–53 对局邀请/离开放在菜单，不是顶栏右侧依次 邀请朋友/退出房间|
|返回大厅与退出分离，房内确认|代码符合|chrome L12 和 L71 独立控件；main L703–753 现有保留期限与原浏览器恢复说明、确认弹窗；首页直接跳，房内确认后跳|
|结算复用外壳|代码符合|root 全局 LobbyNavigation 保留；settlement.tsx L43 再来一局操作，无另造返回大厅入口|
|统一词表|部分不符|chrome.tsx L27 游戏规则（而非 玩法规则）；L12 离开房间（而非 退出房间）；entry L73 / chrome L51 复制邀请链接（而非 邀请朋友）；room-directory L33 暂无在线房间（而非 暂无公开房间）；entry L143 开始游戏 → 带箭头字符；房间码无 复制房间码 标签|
|双站、版本隔离、统一大厅|代码符合；本轮未重新部署探测|backend-entry.js L2–5 及 L46–59：SITE_EDITION，Cloudflare C-/Aliyun A-，大厅分别 https://magical-athlete-online.cn/ 与 https://magical-athlete.qiuh23.workers.dev/lobby/；site-policy.js L1–50 国内固定昵称/禁交流；docs/site-edition.md 记录 cn/global 独立构建/发布|
|阶段 PR + 测试 + Qiu 真机验收|前两者有历史记录；验收待定|本次只读新快照，没有新跑测试。当前附件明确巫师首页非模板；此前 #57 部署后停下，不能把 👍 自动等同于真机正式验收|

### 建议报告摘要

巫师牌首页的四层结构、三格动作按钮、独立进房窗、唯一返回箭头已经在代码中形成。主要差距集中在缺少 DESIGN.md、全尺度 token 单源未完成、断点仍分散、房间码不能点复制、候场/局内邀请与退出的位置不统一，以及几处高频文案不等于新词表。此报告是将新上位规范反向套用现有实现的差距，不自动授权修改，也不把此前按旧范围完成的阶段当失败。


## 卡坦岛：细项与证据

核对日期：2026-11-16。只读固定 main `68694c287189e1984ddeca61e9df9c79e0f43236`（#39）。检查源文件、CSS 声明及策略/导航实现；未运行构建或浏览器/真机检查，不把已部署等同于 Qiu 真机验收。没有修改任何游戏代码。

### 实际来源与标尺
- [DESIGN.md](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/DESIGN.md) 和 [.impeccable/design.json](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/.impeccable/design.json) 均存在；[src/tokens.css](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/tokens.css#L1-L77) 为 65 个基础 token 的数值表。逐项解析与 JSON extensions.tokens 比较：65 对 65，零差异；减少动态单列为 duration 1/2/3 = 0ms。
- 身份：海岸桌面。正文 --font = "Segoe UI","Microsoft YaHei",system-ui,sans-serif；展示 --font-display = "Noto Serif SC","Songti SC",SimSun,serif。
- --ink #173b3d、--muted #65776b、--paper #f7f6f0、--ocean #b8d8d2、--surface-alt #e9ede3、--accent #b65c35、--focus #9a4c26、--line #d6ded3。
- 资源 wood #397456 / brick #ae674a / sheep #66863e / wheat #a28027 / ore #637e8c；反馈 gain/select #c99b3f，robber #493e57。
- 字阶 11/12/13/14/16/18/20/24/32px；字重 400/500/600/700/800；圆角 8/12/14/999px（圆形 50%，control/panel 别名 8/12px）。
- spacing 4/8/12/16/24/32px；阴影 0 3px 14px #173b3b14、0 7px 24px #21483b12、0 16px 44px #173b3b26；z 0/10/20/30/40/50/60；duration 120/180/240ms；ease cubic-bezier(.2,.7,.3,1)；触控 token 44px。
- 文档与全部 src CSS 中的宽度媒体档位：640/950/1190px；短横屏 orientation: landscape + max-height:600px；1200 一类旧档位在此次读取的 CSS 中未出现。
- DESIGN frontmatter 明确 colors / typography / rounded / spacing / components，正文说明较全，适合作模板结构来源，但下列不一致不能当成符合声明。

### 已验证差距（按新附件的目标，不擅改游戏）
1. **首页入口形态不合新规范**：[root.tsx L204–217](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/root.tsx#L204-L217) 的实际三按钮是「开桌 / 加入」「人机练习」「在线房间」，不是「创建房间」「加入房间」「单人练习」。开桌/加入共用 #entry-dialog，独立加入按钮和独立加入弹窗不存在；昵称与恢复入口在该弹窗 HomePanel 内，不在首页动作坞和降级区。注意 HomePanel 名称不代表直接首页露出表单：[root L366–395](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/root.tsx#L366-L395)、[entry L104–188](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/entry.tsx#L104-L188)。
2. **顶栏与单一大厅入口不合**：返回大厅链接在右侧 nav，不在品牌左侧；其 aria-label/title 正确。另有设置、玩家面板复用链接和结算链接，违反“全游戏只有一处”。[root L33–109](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/root.tsx#L33-L109)、[table L770–776](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/table.tsx#L770-L776)、[table L878–882](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/table.tsx#L878-L882)、[entry L697–710](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/entry.tsx#L697-L710)。
3. **外壳与词表不合**：房间码为非交互 span，不能点复制；邀请按钮写「邀请好友」，不是「邀请朋友」；退出/暂离不在顶栏的指定右侧顺序；规则按钮有「玩法指南」可见文字，而不是纯图标及统一“玩法规则”可访问名称；建房弹窗主按钮「创建好友房间」。来源同 root L54–98、entry L168–175。「人机练习」可作为玩法名称，但该主按钮未符合逐字词表；详见上面的裁决。
4. **降级区不合**：在线房间是主要第三按钮而非默认收起、含在线人数的一行；恢复入口是 entry 弹窗中的按钮，不是首页小字链接。空状态「暂无公开房间」准确：[entry L202–235](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/entry.tsx#L202-L235)。
5. **严格“所有语义值仅 token 定义、其余只引用”尚未达到**：例如 home primary 文字直接 `color:white`（不是装饰色），字号 14px/600 直接写在组件 CSS，字号虽在标尺中却未引用 token。[home-family L6–14](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/home-family.css#L6-L14)。ui/theme 的 --ui-* 大多为既有 token 派生别名，不应误报成独立色值源；但严格附件的“其他文件只许引用，不许另立一套”应解释清楚别名是否允许。--feedback-gain 与 --feedback-select 相同值是不同语义，不是仅因值重复即违规。
6. **焦点环文档/代码冲突**：DESIGN 写 2px solid / offset 2px，实际 [ui/theme L41–44](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/theme.css#L41-L44)、home-family L13 为 3px / 3px；[entry.css L13](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/entry.css#L13) 选择卡焦点仍用 accent 而非 focus；chat-preview.css L6 是 3px/2px。不能宣称全站一致。
7. **组件数值仍有标尺外声明**：home-family L12/L19/L24 有 10px 圆角、L33 gap 10px，L14 自定义非三档阴影；src/ui/theme.css L124–127 的 play-dock 16px 圆角、6px padding。这些是源码差距，不据此声称每个声明在每个视口都实际生效。全站触控 ≥44×44 需计算最终命中和热区后才能全部确认，token 存在不等于所有控件达标。
8. **文档残留**：DESIGN Components 仍说首页“可恢复展示或复位”，#39 首页已只留 2D/3D；这些按钮在对局继续存在，不应把首页与局内描述混写。DESIGN frontmatter button-primary 是 primary/ink，而 Stage5 正文与当前首页 dock 用 accent，需注明组件语境，不能抽一个普适按钮色。

### 部分符合/可直接提炼
- 棋盘主舞台、海岸身份、紧凑并排三块入口、国内/海外线路顶栏小字，源码明确；“实际一屏无需滚动”和美感保留为真机验收，不冒充本次已验证。
- #39 首页控制严格仅 2D/3D：[root L132–159](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/ui/root.tsx#L132-L159)。默认演示继续由 main updateAmbient 驱动。
- 常规弹窗原生 dialog + 关闭按钮 + Escape + 遮罩 pointerdown/click 关闭：[dialogs.js](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/dialogs.js#L1-L27)。强制决策 stage-dialog 的遮罩关闭受 canDismiss 限制（main L473）；按“全站三关闭齐全”字面是例外，需要报告而非擅改规则交互。
- 在房间点大厅走 openLeave 确认，首页直接链接；房主/非房主、候场/对局保留规则不同：[main L352–353,432–433](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/main.js#L432-L433)、[room-ui L34–37](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/room-ui.js#L34-L37)。非房主候场返回会退出座位，不能泛写“任何时候返回都保留原身份”。

### 双站与工程证据
- [site-config.js](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/site-config.js) 注入 __SITE_EDITION__，cn 固定大厅 https://magical-athlete-online.cn/，global https://magical-athlete.qiuh23.workers.dev/lobby/；[vite.config.js](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/vite.config.js) 按 SITE_EDITION 构建。
- [shared/site-policy.js](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/shared/site-policy.js#L4-L32) cn 固定昵称与禁交流；[invitation.js](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/invitation.js#L1-L15) aliyun=A、cloudflare=C；[docs/site-editions.md](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/docs/site-editions.md) 描述独立站点与大厅由运动会仓库发布。
- 这次只做源码审计，不重跑部署/测试、不新增 PR，不以历史测试数或 CI 文案代替今日运行。新游戏注册大厅需在大厅所属仓核对，卡坦仓本身不能证明全家族门户清单。
- 附件授予卡坦“已验收范式”的地位，但这不是说当前每项代码已符合新总规范。明确区分：可借鉴的主舞台/简洁度、当前实现偏差、需要 Qiu 真机裁决的结果；不擅自消除任何差距。
