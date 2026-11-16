# 新游戏从零到上线

| 步骤 | 自检事项 |
| --- | --- |
| 视觉身份 | [哲学与判例](../references/philosophy.md)：确认本游戏自己的品牌色、表面、字体、招牌展示与动效性格；能用两条验收测试解释统一边界。 |
| DESIGN 文档 | 填 [DESIGN 模板](DESIGN.template.md)：frontmatter 的颜色、字体、圆角、间距、组件齐备；正文与源码同值。 |
| token 单源 | [令牌标尺](../references/tokens.md)：逐项核对语义色、字阶/字重/最小字号、圆角与间距、阴影、层级、时长与 reduced motion、焦点环、触控区和断点。 |
| 首页 | [首页](../references/homepage.md) 与[词表](../references/copy-glossary.md)：顶栏与图标名称、主舞台、昵称与三个动作、独立加入弹窗三种关闭方式、可恢复/公开房间降级；检查竖屏一屏可操作。 |
| 房间与对局 | [外壳](../references/room-chrome.md) 与[词表](../references/copy-glossary.md)：房间码可复制、邀请/退出位置、唯一返回大厅、房内确认、结算路径。 |
| 线路与大厅 | [平台](../references/platforms.md)：构建标记、聊天/昵称/房间码等策略，统一大厅双向路由，不交叉串站。 |
| 双站发布 | [工作流](../references/workflow.md)：单阶段 PR、测试、双站构建部署和版本核对，改前/改后清单；只测展示改造不改游戏规则。 |
| 真机确认 | Qiu 在真实设备打开线上版本并确认布局与操作；未确认标为待验，被否决整 PR 回退。 |
| 回写索引 | [参考实现](../examples/README.md)：链接、文档及 token 路径、视觉身份、首页形态、验收范围。 |
