# Hello-TaroUI3.0

哈啰移动端组件、交互和 token 设计系统 Agent Skill。

这个 skill 用于基于哈啰 TaroUI 3.0 设计系统校准移动端页面、H5 原型、Taro/React 交付代码或设计草图。它不绑定某一个业务产品，适用于哈啰 C 端与 B 端移动端场景。

## 能做什么

- 识别页面中的组件并匹配哈啰 TaroUI 3.0 组件样式
- 按 design token 校准颜色、字号、圆角、阴影、间距和安全区
- 补齐组件交互状态，如 selected、disabled、loading、empty、error、success
- 基于草图、截图、HTML 原型或实现代码输出组件优化建议
- 生成或修改 HTML/CSS/JS 原型，使组件更符合哈啰移动端设计系统

## 安装

核心 skill 目录是：

```text
Hello-TaroUI3.0/
```

Kiro 可从 GitHub 导入该目录：

```text
https://github.com/Allenchujinxing/Hello-TaroUI3.0-skill/tree/main/Hello-TaroUI3.0
```

Claude Code / Codex 可将 `Hello-TaroUI3.0/` 复制到对应 skills 目录。

## 使用示例

```text
使用 Hello-TaroUI3.0 根据这个 HTML 原型优化页面里的组件样式和交互状态。
```

```text
使用 Hello-TaroUI3.0 识别这张移动端草图里涉及的组件，并给出对应组件规范和 token 建议。
```

```text
使用 Hello-TaroUI3.0 检查这个 Taro 页面是否符合哈啰移动端组件、iconfont、安全区和 token 规范。
```

## 仓库结构

```text
Hello-TaroUI3.0-skill/
├── Hello-TaroUI3.0/
│   ├── SKILL.md
│   ├── agents/
│   └── references/
├── README.md
└── LICENSE
```

## License

MIT
