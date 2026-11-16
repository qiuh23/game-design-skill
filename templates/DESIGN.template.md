---
name: "游戏名 · 视觉身份"
description: "用一句话说明展现的场景和玩家正在做什么"
colors:
  primary: "<主操作色 token>"
  text: "<正文 token>"
  muted: "<次级文字 token>"
  paper: "<表面 token>"
  line: "<边框 token>"
  accent: "<强调 token>"
  focus: "<焦点 token>"
typography:
  body:
    fontFamily: "<正文字体栈>"
    fontSize: "<从字阶选>"
    lineHeight: "<本游戏实测>"
  title:
    fontFamily: "<标题字体栈>"
    fontSize: "<从字阶选>"
    fontWeight: "<从字重标尺选>"
rounded:
  control: "<从圆角档位选>"
  panel: "<从圆角档位选>"
spacing:
  sm: "<从间距表选>"
  md: "<从间距表选>"
  lg: "<从间距表选>"
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "<对应文字 token>"
    rounded: "{rounded.control}"
    padding: "<从间距表选>"
---

# 游戏名 · 视觉身份

## Overview
定义牌桌／棋盘／赛道的视觉主次，说明什么一眼看出是本游戏。

## Colors
列出语义角色、唯一 token、品牌和反馈用法，区分美术、材质、场景灯光。注明已验证的可读性；不从别款复用品牌取值。

## Typography
列正文、标题与游戏专用字体、字阶和适用场景。

## Layout
写首页四层、房间外壳、竖屏／短横屏／桌面、断点及各自用法。

## Elevation & Depth
写三级阴影的值和归属；单列招牌动效阴影。

## Shapes
列圆角和例外的场景几何。

## Tokens
写明唯一源码路径，把 frontmatter 与正文映射到对应 token，机器可读副本如有也要与源码同步。各类值按[统一标尺](../references/tokens.md)选择；本模板不替游戏决定身份值。

## Components
写首页入口、房间与对局外壳、交互反馈、触控、焦点、动效及减弱动态效果。跨站规则另记，不纳入样式。

## Do's and Don'ts
记录本游戏的品味决定、不动的招牌、设计与代码差异以及真机验收状态。
