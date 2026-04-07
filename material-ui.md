# Flutter Material Design 系统学习课程大纲

> 前置条件：已完成《Flutter 常用组件系统学习》课程（catlog.md），掌握各类组件的基本用法。
>
> 课程定位：组件课程教你**怎么用**每个 Widget，本课程教你**怎么按 Material 规范把它们组合成专业、一致的界面**。聚焦 Material Design 3 的设计系统、规范与高级定制能力。

---

## 第01课 Material Design 3 设计体系总览

- Material Design 演进：Material 1 → Material 2 → Material 3（Material You）
- Material 3 三大核心支柱：Color、Typography、Shape
- Design Tokens 概念：从设计规范到代码的映射机制
- Flutter 中的 Material 3 启用方式（useMaterial3: true）
- Material 2 与 Material 3 的视觉差异对比（按钮、卡片、导航栏等）
- MaterialApp 配置全景：theme、darkTheme、themeMode、highContrastTheme
- 实战：创建一个 M2 与 M3 对比展示页面，直观感受差异

## 第02课 颜色系统 - ColorScheme 深入

- Material 3 颜色角色体系：Primary、Secondary、Tertiary、Error、Surface、Outline 等
- 每个颜色角色的使用场景与搭配规范（何时用 primary，何时用 surfaceContainerHighest）
- ColorScheme.fromSeed：从种子颜色自动生成完整配色方案
- ColorScheme.fromImageProvider：从图片提取主题色
- Dynamic Color（动态取色）：读取系统壁纸色（dynamic_color 包）
- 颜色协调（Color Harmonization）：让自定义颜色融入主题
- Surface Tint 与 Elevation Overlay：Material 3 中阴影被色调替代的机制
- 实战：构建一个颜色角色展示面板，显示当前主题的所有颜色角色

## 第03课 排版系统 - TextTheme 与字体

- Material 3 Type Scale：Display、Headline、Title、Body、Label 五大类
- 每个级别（Large / Medium / Small）的设计用途与推荐使用场景
- TextTheme 自定义：覆盖默认 TextStyle
- Google Fonts 集成：google_fonts 包的使用
- 可变字体（Variable Fonts）在 Flutter 中的应用
- 文本无障碍：textScaleFactor、MediaQuery.textScaleFactorOf
- 实战：为应用配置一套完整的品牌字体排版方案

## 第04课 形状系统与 Elevation

- Material 3 Shape 规范：None → Extra Small → Small → Medium → Large → Extra Large → Full
- ShapeBorder 家族：RoundedRectangleBorder、StadiumBorder、BeveledRectangleBorder、ContinuousRectangleBorder
- 不同组件的默认形状规范（FAB 用 Large，Card 用 Medium，Chip 用 Small 等）
- 全局形状定制：通过各组件 Theme 的 shape 属性统一管理
- Material 3 中的 Elevation 新模型：从纯阴影到 Surface Tint
- Elevation 的 6 个层级（0-5）及其对应使用场景
- Material 组件：Material widget 的 type、elevation、shadowColor、surfaceTintColor
- 实战：构建一个展示不同形状和 Elevation 层级的 Showcase 页面

## 第05课 WidgetState 与交互状态管理

- Material 交互状态体系：hovered、focused、pressed、dragged、selected、disabled、error
- WidgetState（原 MaterialState）机制详解
- WidgetStateProperty.resolveWith：根据状态动态返回样式值
- WidgetStateProperty.all / WidgetStateProperty.lerp
- 状态层（State Layer）：Material 规范中的 opacity 叠加规则
- StateLayerOpacity 规范：hover 8%、focus 10%、pressed 10%、dragged 16%
- 在 ButtonStyle、InputDecoration 等中运用状态属性
- WidgetStatesController：监听和控制组件状态
- 实战：自定义一个完全符合 Material 状态规范的自定义按钮

## 第06课 组件主题批量定制

- 组件主题架构：MaterialApp → ThemeData → 各 ComponentTheme
- 全部可定制的组件主题清单：AppBarTheme、CardTheme、DialogTheme、ElevatedButtonTheme、FilledButtonTheme、IconButtonTheme、InputDecorationTheme、ListTileTheme、NavigationBarTheme、NavigationDrawerTheme、NavigationRailTheme、SearchBarTheme、SegmentedButtonTheme、SwitchTheme、TabBarTheme 等
- 组件主题的优先级：Widget 参数 > 组件 Theme > 全局 ThemeData
- ThemeExtension\<T\>：自定义主题扩展（添加品牌色、自定义间距等）
- copyWith 模式：基于现有主题局部修改
- Theme 继承与局部覆盖：在子树中用 Theme widget 覆盖局部主题
- 实战：为一个完整 App 配置统一的组件主题方案（覆盖 10+ 组件主题）

## 第07课 Material 动效规范

- Material Motion 四大转场模式：
  - Container Transform：容器变形（列表项展开为详情页）
  - Shared Axis：共享轴过渡（前进/后退导航）
  - Fade Through：淡入穿透（无关联页面切换）
  - Fade：淡入淡出（出现/消失）
- animations 包（flutter/packages）：OpenContainer、SharedAxisTransition、FadeThroughTransition、FadeScaleTransition
- Material 3 Easing 曲线：emphasized、emphasizedDecelerate、emphasizedAccelerate、standard、standardDecelerate、standardAccelerate
- Material 3 Duration Tokens：短(< 100ms)、中(200-300ms)、长(> 400ms) 动画时长规范
- 页面路由转场定制：PageTransitionsTheme 与 PageTransitionsBuilder
- 实战：为 App 实现符合 Material 规范的页面转场动画

## 第08课 自适应布局与跨平台 Material

- Material Design 响应式布局指南：Compact、Medium、Expanded、Large 四种窗口尺寸类
- 断点规范：< 600dp（Compact）、600-840dp（Medium）、840-1200dp（Expanded）、> 1200dp（Large）
- 导航模式随窗口自适应：BottomNavigationBar → NavigationRail → NavigationDrawer
- Canonical Layouts：列表-详情（List-Detail）、Feed、Supporting Panel
- 自适应组件：showDialog 在大屏上的行为、BottomSheet 在宽屏上的适配
- Platform Adaptive：Material vs Cupertino 差异化处理（.adaptive 构造函数）
- Switch.adaptive、Slider.adaptive 等自适应组件
- 实战：构建一个响应式主页，在手机/平板/桌面上自动切换导航与布局模式

---

## 附录

### 与组件课程的关系

| 维度 | 组件课程（catlog.md） | 本课程（material-ui.md） |
|------|----------------------|------------------------|
| 关注点 | 单个 Widget 的 API 和用法 | Design System 整体规范与定制 |
| 颜色 | 基本的 ColorScheme 使用 | 颜色角色、种子色、动态取色、协调 |
| 排版 | Text / TextStyle 使用 | Type Scale 规范、品牌字体方案 |
| 形状 | 个别组件的圆角设置 | 形状 Token 体系、全局形状管理 |
| 主题 | ThemeData 基础配置 | 组件主题批量定制、ThemeExtension |
| 动画 | 隐式/显式动画 Widget | Material Motion 转场规范 |
| 布局 | 布局 Widget 用法 | Material 响应式布局规范、自适应导航 |

### 学习建议

1. **先完成组件课程**：本课程建立在组件用法基础之上，务必先掌握各组件的 API
2. **对照 Material 3 官方规范**：学习时同步参阅 [m3.material.io](https://m3.material.io) 的设计文档
3. **使用 Material Theme Builder**：[Material Theme Builder](https://m3.material.io/theme-builder) 可视化配置主题并导出 Flutter 代码
4. **关注 Flutter 更新**：Material 3 组件仍在持续完善，留意 Flutter 版本更新日志

### 参考资源

- [Material Design 3 官方规范](https://m3.material.io)
- [Flutter Material 3 迁移指南](https://docs.flutter.dev/ui/design/material)
- [animations 包](https://pub.dev/packages/animations)
- [dynamic_color 包](https://pub.dev/packages/dynamic_color)
- [google_fonts 包](https://pub.dev/packages/google_fonts)
- [Material Theme Builder](https://m3.material.io/theme-builder)
