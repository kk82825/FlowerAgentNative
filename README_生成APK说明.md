# 竹影蝶韵·智循生芳——纯原生 Android 工程

## 一、工程特点

- 纯 Java + Android 原生控件，不使用 WebView、uni-app、Vue、HTML。
- `minSdk 16`，理论安装范围从 Android 4.1 开始。
- `targetSdk 28`，适合旧广告机离线运行。
- 全部图片、植物资料和112条问答均放在安装包内。
- 首页、作品导览、智能养护、AI小课堂、花艺知识库、美育互动、互动问答均为原生页面。
- 页面固定竖屏并保持屏幕常亮。

## 二、使用 Android Studio 生成测试 APK

1. 安装 Android Studio。
2. 解压本工程，打开 `FlowerAgentNative` 文件夹，不要只打开 `app` 文件夹。
3. 等待右下角 Gradle Sync 完成。第一次同步需要联网下载 Gradle、Android Gradle Plugin 和 Android SDK 35。
4. 如果提示缺少 Android SDK 35，点击提示中的 `Install missing SDK package`。
5. 菜单选择：`Build` → `Build Bundle(s) / APK(s)` → `Build APK(s)`。
6. 构建完成后，测试 APK 位于：

   `app/build/outputs/apk/debug/app-debug.apk`

调试 APK 已由 Android Studio 自动使用调试证书签名，可直接复制到广告机安装。

## 三、生成正式签名 APK

1. 菜单选择：`Build` → `Generate Signed Bundle / APK`。
2. 选择 `APK`，点击 `Next`。
3. 第一次使用时点击 `Create new` 创建密钥库 `.jks`。
4. 填写密钥库路径、密码、别名、有效期和证书信息，并妥善保存密码。
5. Build Variant 选择 `release`。
6. 勾选签名版本 V1 和 V2；面向 Android 4.x 老设备时必须保留 V1。
7. 点击 `Create`。
8. 正式 APK 位于：

   `app/build/outputs/apk/release/app-release.apk`

## 四、命令行生成 APK

项目包含 Gradle Wrapper 配置。若 `gradle-wrapper.jar` 已由 Android Studio 生成或补齐，可在项目根目录执行：

Windows：

`gradlew.bat assembleDebug`

macOS / Linux：

`./gradlew assembleDebug`

正式版执行：

`./gradlew assembleRelease`

## 五、广告机安装建议

1. 先卸载之前的 uni-app APK，避免包名和缓存混淆。
2. 开启广告机“允许安装未知来源应用”。
3. 将 `app-debug.apk` 或签名后的 `app-release.apk` 复制到U盘。
4. 在广告机文件管理器中点击安装。
5. 第一次测试先安装 debug APK；确认功能稳定后再换正式签名 APK。

## 六、低版本兼容说明

本工程设置为 `minSdk 16`，但应至少在以下设备上分别测试：

- Android 4.1 / API 16 模拟器；
- Android 4.4 / API 19 模拟器；
- 当前 RK3368 Android 5.1.1 广告机；
- 一台较新的 Android 设备。

由于完全不使用 WebView，系统 WebView 版本不会影响页面显示。
