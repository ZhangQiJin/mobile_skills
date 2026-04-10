# mobile-native-reverse-ui-analysis

面向 AI 编程工具的移动原生 UI 逆向分析 skill。它可以将网页分析结果、截图、设计说明、HTML 片段、Storyboard/XML 片段等输入，转换为 iOS 与 Android 原生实现所需的 12 维结构化规格，并输出可直接用于生成 SwiftUI/UIKit 或 Jetpack Compose/XML 代码的一键提示词。

## English Overview

`mobile-native-reverse-ui-analysis` is a mobile native UI reverse-analysis skill for AI coding tools. It converts UI inputs such as web reverse-analysis results, screenshots, design notes, HTML snippets, Storyboard/XML snippets, or layout fragments into structured native mobile specifications for iOS and Android.

The skill produces a 12-dimension analysis covering screen context, view hierarchy, native components, visual elements, theming, typography, interaction, accessibility, dependencies, code quality, state, and reusability. It then outputs ready-to-copy generation prompts for SwiftUI/UIKit and Jetpack Compose/XML.

### When To Use

- Convert a web page or H5 screen into native iOS and Android UI implementation prompts.
- Continue from `html-page-reverse-ui-analysis` and map the web analysis into mobile native components.
- Analyze screenshots, recordings, Figma notes, PRD descriptions, or existing layout snippets.
- Generate production-oriented UI prompts for SwiftUI, UIKit, Jetpack Compose, or Android XML/View.

### Demo

Demo recording:

[mobile-native-reverse-ui-analysis/assets/demo.mov](mobile-native-reverse-ui-analysis/assets/demo.mov)

### Repository Layout

```text
.
├── README.md
└── mobile-native-reverse-ui-analysis/
    ├── SKILL.md
    ├── README.md
    ├── reference.md
    └── assets/
        └── demo.mov
```

### Install For Cursor

```bash
git clone https://github.com/ZhangQiJin/mobile_skills.git /tmp/mobile_skills
mkdir -p ~/.cursor/minimax-skills/skills
cp -R /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.cursor/minimax-skills/skills/
```

Restart Cursor or refresh the agent configuration after installation.

### Install For Codex / Agents

```bash
git clone https://github.com/ZhangQiJin/mobile_skills.git /tmp/mobile_skills
mkdir -p ~/.agents/skills
cp -R /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.agents/skills/
```

You can also use a symlink:

```bash
ln -s /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.agents/skills/mobile-native-reverse-ui-analysis
```

### Usage Examples

```text
Use mobile-native-reverse-ui-analysis to reverse-engineer this screenshot into native iOS and Android UI prompts.
```

```text
Here is a 12-dimension web analysis from html-page-reverse-ui-analysis. Convert it into SwiftUI and Jetpack Compose native implementation prompts.
```

```text
Convert this H5 page into an iOS UIKit screen spec and an Android XML/View screen spec.
```

### Accepted Inputs

Provide at least one of the following:

- Web or HTML reverse-analysis results.
- Screenshots, screen recordings, or design images.
- Figma notes, PRD text, or prototype descriptions.
- Existing XML, Storyboard, SwiftUI, Compose, or HTML layout snippets.

If details are missing, the skill should ask for target platform, minimum OS versions, dark mode requirements, dynamic type, accessibility, landscape support, or tablet adaptation.

### Output

The skill outputs 12 dimensions:

1. Screen metadata
2. View hierarchy
3. Native components
4. Visual elements
5. Color and theming
6. Typography
7. Design style
8. Interaction and motion
9. Layout, safe area, and accessibility
10. Dependencies and engineering constraints
11. Code quality and maintainability
12. State and reusability

It then outputs:

- iOS final generation prompt
- Android final generation prompt

If the user asks for only one platform, output only that platform.

## 演示

录屏文件位于：

[mobile-native-reverse-ui-analysis/assets/demo.mov](mobile-native-reverse-ui-analysis/assets/demo.mov)

## 仓库内容

```text
.
├── README.md
└── mobile-native-reverse-ui-analysis/
    ├── SKILL.md
    ├── README.md
    ├── reference.md
    └── assets/
        └── demo.mov
```

## 适用场景

- 将网页 12 维逆向分析结果映射为 iOS 与 Android 原生实现方案。
- 根据移动端截图、设计稿说明或产品原型，生成双端原生 UI 拆解。
- 输出 SwiftUI/UIKit 与 Jetpack Compose/XML 的组件选型、视图层级、主题 token、交互状态、无障碍与工程约束。
- 生成可复制的一键提示词，交给 AI 编码工具继续产出原生代码。

## 安装到 Cursor

```bash
git clone https://github.com/ZhangQiJin/mobile_skills.git /tmp/mobile_skills
mkdir -p ~/.cursor/minimax-skills/skills
cp -R /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.cursor/minimax-skills/skills/
```

重启 Cursor 或刷新 agent 配置后即可使用。

## 安装到 Codex / Agents

```bash
git clone https://github.com/ZhangQiJin/mobile_skills.git /tmp/mobile_skills
mkdir -p ~/.agents/skills
cp -R /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.agents/skills/
```

也可以使用符号链接：

```bash
ln -s /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.agents/skills/mobile-native-reverse-ui-analysis
```

## 使用方式

在对话中直接提到 skill 名称，或描述移动端 UI 逆向需求：

```text
请使用 mobile-native-reverse-ui-analysis，把这张截图逆向成 iOS + Android 原生 UI 提示词。
```

```text
以下是 html-page-reverse-ui-analysis 的网页 12 维分析结果，请继续生成 SwiftUI 和 Jetpack Compose 的原生实现提示词。
```

```text
帮我把这个 H5 页面转换成 iOS UIKit 和 Android XML 原生页面说明。
```

## 输入要求

至少提供以下任意一种输入：

- HTML/网页逆向分析结果。
- 页面截图、录屏或设计图。
- Figma、PRD、原型说明。
- 现有 XML、Storyboard、SwiftUI、Compose 或 HTML 布局片段。

如果信息不足，skill 会补问目标平台、最低系统版本、是否需要深色模式、动态字体、无障碍、横屏或平板适配。

## 输出内容

skill 会按 12 个维度输出：

1. 屏幕与产品上下文
2. 视图层级结构
3. 关键 UI 组件列表
4. 视觉元素
5. 色彩系统
6. 字体与排版
7. 视觉风格总结
8. 动效与交互
9. 适配与无障碍
10. 依赖与工程约束
11. 架构与可维护性
12. 数据、状态与复用

最后输出：

- iOS 最终生成提示词
- Android 最终生成提示词

如果用户指定单平台，则只输出对应平台。

## 示例

### 截图转双端原生提示词

```text
请使用 mobile-native-reverse-ui-analysis 分析附件截图。
目标：双端原生还原。
iOS：SwiftUI，最低 iOS 16。
Android：Jetpack Compose + Material 3，minSdk 26。
要求：输出 12 维分析，并在最后给出 iOS 和 Android 最终生成提示词。
```

### 网页分析结果转原生提示词

```text
请基于下面的网页逆向分析结果，继续使用 mobile-native-reverse-ui-analysis 输出移动端原生方案。
要求：
1. 不重复冗长网页分析。
2. 每个维度都写出 iOS 与 Android 的原生组件映射。
3. 最后生成 SwiftUI 和 Jetpack Compose 可直接使用的一键提示词。

【粘贴网页 12 维分析结果】
```

## 维护说明

- 修改触发条件与工作流程：编辑 `mobile-native-reverse-ui-analysis/SKILL.md`。
- 修改 12 维定义或模板：编辑 `mobile-native-reverse-ui-analysis/reference.md`。
- 修改安装说明与示例：编辑本 `README.md` 或 skill 目录内的 `README.md`。

## License

MIT
