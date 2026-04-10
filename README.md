# mobile-native-reverse-ui-analysis

Languages: English | [中文](README_zh.md)

`mobile-native-reverse-ui-analysis` is a mobile native UI reverse-analysis skill for AI coding tools. It converts UI inputs such as web reverse-analysis results, screenshots, screen recordings, design notes, HTML snippets, Storyboard/XML snippets, or layout fragments into structured native mobile specifications for iOS and Android.

The skill produces a 12-dimension analysis covering screen context, view hierarchy, native components, visual elements, theming, typography, interaction, accessibility, dependencies, code quality, state, and reusability. It then outputs ready-to-copy generation prompts for SwiftUI/UIKit and Jetpack Compose/XML.

## Language Support

This skill supports both English and Chinese.

- If the user writes in English, the analysis and final prompts should be written in English.
- If the user writes in Chinese, the analysis and final prompts should be written in Chinese.
- Technical terms such as SwiftUI, UIKit, Jetpack Compose, Material 3, NavigationStack, Scaffold, and LazyColumn are kept in English where appropriate.

## Demo

Demo recording:

[mobile-native-reverse-ui-analysis/assets/demo.mov](mobile-native-reverse-ui-analysis/assets/demo.mov)

## Repository Layout

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

## When To Use

- Convert a web page or H5 screen into native iOS and Android UI implementation prompts.
- Continue from `html-page-reverse-ui-analysis` and map the web analysis into mobile native components.
- Analyze screenshots, screen recordings, Figma notes, PRD descriptions, or existing layout snippets.
- Generate production-oriented UI prompts for SwiftUI, UIKit, Jetpack Compose, or Android XML/View.
- Produce copy-ready prompts for AI coding tools to generate native mobile UI code.

## Install For Cursor

```bash
git clone https://github.com/ZhangQiJin/mobile_skills.git /tmp/mobile_skills
mkdir -p ~/.cursor/minimax-skills/skills
cp -R /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.cursor/minimax-skills/skills/
```

Restart Cursor or refresh the agent configuration after installation.

## Install For Codex / Agents

```bash
git clone https://github.com/ZhangQiJin/mobile_skills.git /tmp/mobile_skills
mkdir -p ~/.agents/skills
cp -R /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.agents/skills/
```

You can also use a symlink:

```bash
ln -s /tmp/mobile_skills/mobile-native-reverse-ui-analysis ~/.agents/skills/mobile-native-reverse-ui-analysis
```

Restart Codex or your agent runtime after installation.

## Usage Examples

Reverse a screenshot into native prompts:

```text
Use mobile-native-reverse-ui-analysis to reverse-engineer this screenshot into native iOS and Android UI prompts.
```

Continue from a web reverse-analysis result:

```text
Here is a 12-dimension web analysis from html-page-reverse-ui-analysis. Convert it into SwiftUI and Jetpack Compose native implementation prompts.
```

Generate single-platform output:

```text
Use mobile-native-reverse-ui-analysis and output only an iOS SwiftUI implementation prompt. Minimum target: iOS 16.
```

```text
Use mobile-native-reverse-ui-analysis and output only an Android Jetpack Compose implementation prompt. Use Material 3 and minSdk 26.
```

## Accepted Inputs

Provide at least one of the following:

- Web or HTML reverse-analysis results.
- Screenshots, screen recordings, or design images.
- Figma notes, PRD text, or prototype descriptions.
- Existing XML, Storyboard, SwiftUI, Compose, or HTML layout snippets.

If details are missing, the skill should ask for target platform, minimum OS versions, dark mode requirements, dynamic type, accessibility, landscape support, or tablet adaptation.

## Output

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

## Recommended Workflow

1. Use `html-page-reverse-ui-analysis` to analyze a web page when the input is web-based.
2. Use `mobile-native-reverse-ui-analysis` to map the web analysis into iOS and Android native UI specifications.
3. Copy the generated final prompts into your AI coding tool.
4. Generate SwiftUI/UIKit or Jetpack Compose/XML code.
5. Review the result for platform conventions, accessibility, and responsive layout behavior.

## Quality Guidelines

- Do not copy web layout concepts directly into native UI descriptions.
- Prefer native layout terms: `NavigationStack`, `ScrollView`, `LazyVStack`, `List`, `TabView`, `Scaffold`, `TopAppBar`, `LazyColumn`, `Column`, `Row`, and `Card`.
- Describe color, typography, spacing, radius, shadows, states, motion, accessibility, and engineering constraints explicitly.
- Mark unknown information as "needs design confirmation" instead of inventing details.
- Keep final prompts complete, actionable, and ready to paste into an AI coding tool.

## Maintainers

- Update `mobile-native-reverse-ui-analysis/SKILL.md` when changing trigger rules or workflow.
- Update `mobile-native-reverse-ui-analysis/reference.md` when changing the 12-dimension analysis schema or prompt templates.
- Update `README.md` and `README_zh.md` when changing installation, examples, or user-facing documentation.

## License

MIT
