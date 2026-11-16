---
name: game-design-skill
description: 为 Qiu 的好友房网页游戏家族设计或施工 UI 时使用，包括新游戏接入、首页与房间外壳、设计 token 和双站验收。
---

# 好友房网页游戏设计

**统一骨架和动词，不统一皮肤。** 共享入口、位置、操作和文案；保留各游戏的配色、字体、主视觉、动效性格和招牌展示。

1. 朋友换一个游戏，不必重新学在哪开房、哪进朋友的房。
2. 任意一页截图，别人一眼能认出是哪个游戏。

统一到第一条通过为止，第二条不能破。首页和外壳参照 Qiu 已真机验收的胡闹运动会与卡坦岛范式；巫师牌首页是改造对象，不是原始模板。拿不准某次提交是否已获真机验收，就不把该版本当范式。

## 红线和索引

- 要判断该统一什么、怎样不重演旧回归：[哲学与判例](references/philosophy.md)。
- 要选字号、间距、焦点、颜色或动效：先读[令牌标尺](references/tokens.md)；每游戏一套语义 token，不拿装饰色凑统一。
- 要搭首屏或调整入口：[首页范式](references/homepage.md)；一屏、一处动作坞，不把进房表单铺在首页。
- 要改候场、对局外壳或退场路径：[房间外壳](references/room-chrome.md)；返回大厅不等于退出房间。
- 要改标签、按钮或可访问名称：[文案词表](references/copy-glossary.md)；主动作使用统一动词。
- 要改双站或大厅接入：[平台与版本](references/platforms.md)；不让视觉改动改变版本策略。
- 要施工、交付或自检：[工作流](references/workflow.md)；只动展示层，构建通过不等于真机验收。
- 要接入新游戏：[设计文档模板](templates/DESIGN.template.md)、[接入清单](templates/new-game-checklist.md)和[三个实现的索引](examples/README.md)。
