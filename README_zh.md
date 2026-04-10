# mobile-native-reverse-ui-analysis

语言： [English](README.md) | 中文

`mobile-native-reverse-ui-analysis` 是一个面向 AI 编程工具的移动原生 UI 逆向分析 skill。它可以将网页分析结果、截图、录屏、设计说明、HTML 片段、Storyboard/XML 片段等输入，转换为 iOS 与 Android 原生实现所需的 12 维结构化规格，并输出可直接用于生成 SwiftUI/UIKit 或 Jetpack Compose/XML 代码的一键提示词。

## 语言支持

该 skill 支持中文和英文。

- 用户用中文提问时，分析结果和最终提示词默认使用中文。
- 用户用英文提问时，分析结果和最终提示词默认使用英文。
- SwiftUI、UIKit、Jetpack Compose、Material 3、NavigationStack、Scaffold、LazyColumn 等技术名词按惯例保留英文。

## 演示

录屏文件位于：

[mobile-native-reverse-ui-analysis/assets/demo.mov](mobile-native-reverse-ui-analysis/assets/demo.mov)

## 仓库内容

```text
.
├── README.md
├── README_zh.md
└── mobile-native-reverse-ui-analysis/
    ├── SKILL.md
    ├── README.md
    ├── reference.md
    └── assets/
        └── demo.mov
```

## 适用场景

- 将网页或 H5 页面转换为 iOS 与 Android 原生 UI 实现提示词。
- 承接 `html-page-reverse-ui-analysis` 的网页 12 维分析结果，继续映射到移动原生组件。
- 分析截图、录屏、Figma 说明、PRD、产品原型或已有布局片段。
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

安装后重启 Codex 或对应 agent 运行环境。

## 使用示例

截图转双端原生提示词：

```text
请使用 mobile-native-reverse-ui-analysis，把这张截图逆向成 iOS + Android 原生 UI 提示词。
```

承接网页逆向分析：

```text
以下是 html-page-reverse-ui-analysis 的网页 12 维分析结果，请继续生成 SwiftUI 和 Jetpack Compose 的原生实现提示词。
```

单平台输出：

```text
请使用 mobile-native-reverse-ui-analysis，只输出 iOS SwiftUI 实现提示词。最低版本 iOS 16。
```

```text
请使用 mobile-native-reverse-ui-analysis，只输出 Android Jetpack Compose 实现提示词。使用 Material 3，minSdk 26。
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

## 推荐工作流

1. 如果输入来自网页，先使用 `html-page-reverse-ui-analysis` 完成网页分析。
2. 使用 `mobile-native-reverse-ui-analysis` 将网页结构映射为 iOS 与 Android 原生 UI 规格。
3. 将最终生成提示词复制到 AI 编码工具中。
4. 生成 SwiftUI/UIKit 或 Jetpack Compose/XML 代码。
5. 检查平台规范、无障碍与响应式布局表现。

## 输出质量标准

- 不把 Web 结构直接照搬到原生，不使用 `div`、`flex` 等作为最终实现描述。
- 优先使用原生布局语义：`NavigationStack`、`ScrollView`、`LazyVStack`、`List`、`TabView`、`Scaffold`、`TopAppBar`、`LazyColumn`、`Column`、`Row`、`Card` 等。
- 色彩、字体、间距、圆角、阴影、状态、动效和无障碍都要明确说明。
- 对无法确认的信息标注“需设计稿确认”或“推断为...”，避免编造。
- 最终提示词应是一段完整、可复制、可直接用于生成代码的文字。

## 维护说明

- 修改触发条件与工作流程：编辑 `mobile-native-reverse-ui-analysis/SKILL.md`。
- 修改 12 维定义或模板：编辑 `mobile-native-reverse-ui-analysis/reference.md`。
- 修改安装说明与示例：编辑 `README.md` 与 `README_zh.md`。

## License

MIT
