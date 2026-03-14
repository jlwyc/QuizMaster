# Flutter错题App 快速开始

## 环境要求

- Flutter 3.x
- Dart 3.x
- Android SDK / Xcode (iOS开发)

## 运行步骤

### 1. 安装Flutter

```bash
# macOS / Linux
git clone https://github.com/flutter/flutter.git
export PATH="$PATH:`pwd`/flutter/bin"

# Windows
# 下载Flutter SDK: https://flutter.dev/docs/get-started/install
```

### 2. 克隆项目

```bash
git clone https://github.com/jlwyc/cuoti-app.git
cd cuoti-app/cuoti_app
```

### 3. 安装依赖

```bash
flutter pub get
```

### 4. 运行

```bash
# 调试模式
flutter run

# 指定设备
flutter run -d <device_id>

# 查看可用设备
flutter devices
```

### 5. 构建发布

```bash
# Android APK
flutter build apk --release

# iOS (需要macOS + Xcode)
flutter build ios --release

# Web
flutter build web
```

## 项目结构

```
lib/
├── main.dart              # 入口文件
├── app.dart              # App配置
├── core/
│   ├── theme/            # 主题配置（暗黑霓虹风）
│   ├── constants/        # 常量
│   └── utils/           # 工具函数
├── models/               # 数据模型
├── providers/            # Riverpod状态管理
├── widgets/             # 通用组件
│   └── common/          # 基础组件
└── features/            # 功能模块
    ├── home/           # 首页
    ├── camera/         # 拍照
    ├── questions/     # 错题库
    ├── exam/           # 组卷
    └── profile/       # 我的
```

## 主题配色

| 颜色 | 色值 | 用途 |
|------|------|------|
| 背景 | #0A0A0F | 墨黑背景 |
| 卡片 | #1A1A24 | 卡片背景 |
| 主色 | #00FF9D | 霓虹青高亮 |
| 错误 | #FF6B35 | 警示橙 |
| 文字 | #E8E8EC | 主文字 |

## 对接后端

修改 `lib/core/constants/app_constants.dart` 中的API地址：

```dart
class AppConstants {
  static const String apiBaseUrl = 'http://你的服务器IP:8000/api/v1';
}
```

## 常见问题

### Flutter安装失败
```bash
# 清除缓存后重试
flutter clean
flutter pub get
```

### Android SDK未配置
```bash
# 设置Android SDK路径
export ANDROID_HOME=/path/to/android/sdk
```

### iOS模拟器无法运行
```bash
# 打开iOS模拟器
open -a Simulator

# 或者安装
xcodebuild -installComponents
```
