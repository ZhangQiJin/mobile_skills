# mobile-native-reverse-ui-analysis

面向 AI 编程工具的移动原生 UI 逆向分析 skill。它可以将网页分析结果、截图、设计说明、HTML 片段、Storyboard/XML 片段等输入，转换为 iOS 与 Android 原生实现所需的 12 维结构化规格，并输出可直接用于生成 SwiftUI/UIKit 或 Jetpack Compose/XML 代码的一键提示词。

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
git clone https://github.com/ZhangQiJin/mobile-native-reverse-ui-analysis.git /tmp/mobile-native-reverse-ui-analysis
mkdir -p ~/.cursor/minimax-skills/skills
cp -R /tmp/mobile-native-reverse-ui-analysis/mobile-native-reverse-ui-analysis ~/.cursor/minimax-skills/skills/
```

重启 Cursor 或刷新 agent 配置后即可使用。

## 安装到 Codex / Agents

```bash
git clone https://github.com/ZhangQiJin/mobile-native-reverse-ui-analysis.git /tmp/mobile-native-reverse-ui-analysis
mkdir -p ~/.agents/skills
cp -R /tmp/mobile-native-reverse-ui-analysis/mobile-native-reverse-ui-analysis ~/.agents/skills/
```

也可以使用符号链接：

```bash
ln -s /tmp/mobile-native-reverse-ui-analysis/mobile-native-reverse-ui-analysis ~/.agents/skills/mobile-native-reverse-ui-analysis
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
