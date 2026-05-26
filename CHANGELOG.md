# 更新记录

## 2026-05-26

这次更新主要是把规范用起来更顺手——同一个东西不会再看到两套说法，token 名字也对得上号。具体：

### 算错的、写岔的，都对齐了

- 全屏页面"可用内容区"那行算式之前是 `845 - 88 - 106 = 651px`，按 390×844 设计稿应该是 `844 - 88 - 106 = 650px`，已修正。
- 底部操作栏的总高度，之前 token 文档写 98px、组件文档写 106px，现在统一成 106px（内容区 72px + 安全区 34px）。
- "模块纵向间距"之前 token 表写 12px、关键尺寸表写 8px，现在统一成 12px。
- Picker 选择器顶部/底部的渐隐蒙层高度有处写错成 40px，已改回设计稿的 48px。
- Picker 工具栏按钮圆角直接写了裸 `10px`，现在用 token `radius-2xl` 表达。

### 颜色 token 的语义清晰了

之前有些组件的"白色背景"和"白色文字"混着用 `text-inverse` 和 `surface-primary`，看起来都是白色但语义不一样。现在统一成：

- 容器、面板、卡片的**背景**用 `surface-primary`
- 彩色背景上的**反色文字/图标**用 `text-inverse`

涉及 NavBar、Card、Stepper、Range Slider、Dialog、FAB、Image Upload、Tag、Badge、Empty、Dropdown Panel、Input、Picker。

### 圆角不再有"裸数值"

地图悬浮控件、索引导航的圆形提示等几处直接写了像素值（`8px`、`40px`），现在都改成对应的 token（`radius-xl`、`radius-full`）。Dialog 文档里把 `radius-xl` 标成"模块内圆角"也不准确，改成"模块级圆角"了。

### 卡片内边距和文档对得上号了

卡片内边距 token 之前定义是 16px，但 Card 组件实际所有地方都用 12px。现在 token 定义改成 12px，Card 组件文档也直接引用 `space-card-padding` 而不是写裸 `12px`。

### 一些零散的清理

- token 文档里"基础"表的"外边距 / 水渠"和下面"页面级间距 Token"重复了，删掉裸值表，让 token 表成为唯一入口。
- HelloCN.md 把"12px 文字 → 14px 图标"的搭配建议删了，因为 14px 不在 iconfont 库的标准尺寸里，做方案时按需指令即可。
- 组件清单里有个 `Drawer 抽屉` 的占位条目，但实际几乎用不到，删了，README 里的目录树也跟着对齐。
- Range Slider 滑块的阴影 token 之前写的是 `Shadow/Shadow-1`，按 token 体系滑块场景应该用 `shadow-thumb`，已修正。

### token 文档新增一句说明

明确说"组件内部尺寸、padding、gap 跟随 Figma 设计稿保持固定 px，不属于 token 化范围"，避免下次读到"禁止硬编码视觉值"时把组件内部 px 也算进去。
