---
name: Hello-TaroUI3.0
description: 使用哈啰 TaroUI 3.0 移动端设计系统进行组件选型、视觉样式、交互模式和 token 校准。适用于哈啰 C 端与 B 端移动端页面、H5 原型、Taro/React 交付、组件样式还原、iconfont、安全区系统控件、反馈状态、表单控件、弹层、筛选、列表、卡片、地图控件和设计系统一致性检查。
---

# 哈啰 TaroUI 3.0

本 skill 是哈啰移动端设计系统的组件与 token 使用指南。它负责把页面方案、原型或实现代码校准到哈啰 TaroUI 3.0 的组件结构、视觉样式、交互模式和设计 token。

本 skill 不负责定义业务场景、用户目标或信息架构。若需求仍停留在“做一个什么业务页面”的阶段，应先用对应的场景/产品设计 skill 明确页面目标，再使用本 skill 做设计系统落地。

## 工作流

1. **明确输入类型。** 判断当前任务是在生成新页面、优化已有原型、修正代码样式、做组件选型，还是做设计系统一致性检查。
2. **保留产品决策。** 沿用已有方案中的用户、场景、信息层级、主操作和状态模型，不用组件库重新发明页面结构。
3. **查找匹配组件。** 先读 `references/component-styles/index.md`，再只读取当前页面需要的组件文件。
4. **分离视觉和行为。** 读取 `references/component-index.md`，判断某个视觉组件是否可以借用 `references/component-library/taroify.md` 中的交互语义。
5. **以组件样式为准。** 组件样式文件决定结构、尺寸、间距、字体、颜色角色、圆角、阴影、边框、图标槽位和视觉状态。
6. **Taroify 只用于行为语义。** 可以借用 picker、sheet、form、tab、toast、dialog、skeleton、loading、list 等移动端交互模式，但不要复制 Taroify 默认视觉主题。
7. **按需读取 design token。** 如果组件样式文件只写了 token 名但没有给出值，或实现代码需要精确 CSS 值，只读取 `references/HelloCN.md` 中对应章节。
8. **做一致性检查。** 检查组件、状态、图标、安全区、token、间距、圆角和交互反馈是否符合设计系统。

## 全局规则

- 全屏移动端 demo 必须包含 `component-styles/basic/system.md` 中的系统状态栏和 Home Indicator。
- 图标必须遵循 `component-styles/basic/icon.md` 的 iconfont 用法。不要使用外部图标库，也不要手写 SVG path。
- 设计基准为 390x844px @1x，并遵循 iOS 安全区行为。
- 所有视觉值必须来自组件样式文件或 `HelloCN.md` token。不要自行发明近似颜色、圆角、间距或阴影。
- 如果无法精确实现，说明：`Not implemented exactly: <component> / <reason>`。

## 内置参考

- `references/component-styles/`：自包含的哈啰 TaroUI 3.0 移动端组件样式库。
- `references/component-styles/index.md`：组件清单、全局规则和文件索引。
- `references/component-index.md`：视觉组件合同与行为族之间的桥接说明。
- `references/component-library/taroify.md`：仅作为移动端交互语义参考，不要复制默认视觉主题。
- `references/HelloCN.md`：Hello-CN token 来源。默认只读取需要的 token 章节，不要整篇加载。

## 组件选择指南

- **页面框架：** 读取 system、nav-bar、tab-bar、tab、tool-bar，处理状态栏、安全区、导航和底部操作。
- **核心操作：** 读取 button、fab、dialog、toast、loading，覆盖点击、禁用、loading、成功、失败和确认反馈。
- **地图页：** 读取 `display/map.md`，再按需读取相邻控件，如 `input/search.md`、`input/filter-bar.md`、`feedback/popup.md`、`feedback/action-sheet.md`、`feedback/toast.md`、`display/empty.md`，以及相关 list/card/tag 文件。
- **表单页：** 读取输入字段、所需的 picker/calendar/cascader、反馈状态、按钮和底部工具栏。
- **详情/操作页：** 读取导航栏、card/list/tag/badge/collapse/timeline、反馈弹层和底部固定操作。
- **搜索/列表页：** 读取 search、filter bar/dropdown、tabs、list/card/tag/badge、empty/skeleton/pull-up-load。
- **数据页：** 读取 card、tag/badge、tabs、list、progress、notice/message；如果存在图表样式源，也按需读取。

## 输出要求

做设计系统细化或评审时，输出：

- 按页面区域分组的组件清单
- 每个动态组件的交互行为
- 状态覆盖：loading、empty、error、disabled、selected、submitting、success
- 绑定到组件文件和 token 来源的样式说明
- 无法精确实现的差异点

生成 HTML/CSS/JS 时，实现当前流程真正需要的交互：打开、选择、确认、取消、清除、校验、提交 loading、toast/dialog 反馈，以及 loading 到内容的状态转换。
