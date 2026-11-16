# 参考实现索引

查已获真机认可的交互结构，不照抄皮肤。表中的固定快照用于核对这次报告，引用到当前代码不等于给每个新改动颁发验收。

| 游戏仓库 | 视觉身份 | Token 源 | DESIGN 文档 | 首页形态与参考地位 |
| --- | --- | --- | --- | --- |
| [胡闹运动会](https://github.com/qiuh23/magical-athlete-online) | 蓝、黄、草绿与硬阴影的嘉年华赛场。 | [src/client/ui-theme.css](https://github.com/qiuh23/magical-athlete-online/blob/7e542f72d6affae64a7bed39e723dd89d36d5898/src/client/ui-theme.css) | 无现行根目录 DESIGN；[旧入口设计稿](https://github.com/qiuh23/magical-athlete-online/blob/7e542f72d6affae64a7bed39e723dd89d36d5898/docs/qa/entry-design/DESIGN.md)仅历史。 | 主视觉和入口集中、顶栏图标化。已认可的是范式，不代表现行 tab、表单及对局导航都符合新文档。 |
| [巫师牌](https://github.com/qiuh23/wizard-friends) | 烛光、深青毡面、金色、衬线牌桌。 | [src/ui/theme.css](https://github.com/qiuh23/wizard-friends/blob/0295faf27338682ad92b30e2c6586ce0063f9b47/src/ui/theme.css) | 未找到 DESIGN.md；[阶段 4 文档](https://github.com/qiuh23/wizard-friends/blob/0295faf27338682ad92b30e2c6586ce0063f9b47/docs/qa/ui-overhaul/phase-4.md)不是替代件。 | [#57](https://github.com/qiuh23/wizard-friends/pull/57)按范式改造完成的实现：满幅舞台、三格入口、独立加入窗；新版真机确认未核实，不是原始模板。 |
| [卡坦岛](https://github.com/qiuh23/catan-friends) | 暖白、海水、实体低多边形的海岸桌面。 | [src/tokens.css](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/src/tokens.css) | [DESIGN.md](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/DESIGN.md)、[.impeccable/design.json](https://github.com/qiuh23/catan-friends/blob/68694c287189e1984ddeca61e9df9c79e0f43236/.impeccable/design.json) | 以满屏地图、一个紧凑动作坞作为简洁度参照；[#39](https://github.com/qiuh23/catan-friends/pull/39)只改首页 2D／3D 控制条，新提交不等于独立真机确认。 |
