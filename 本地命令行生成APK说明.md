# 不打开 Android Studio，使用命令行生成 APK

本地仍需要安装三个组件：

1. JDK 17
2. Android SDK Command-line Tools
3. Gradle 8.7

安装完成并配置好 `JAVA_HOME`、`ANDROID_HOME` 和 `PATH` 后，在项目根目录执行：

```bat
gradle :app:assembleDebug --no-daemon
```

生成位置：

```text
app\build\outputs\apk\debug\app-debug.apk
```

本项目原始压缩包中的 `gradlew.bat` 只有启动脚本，没有附带 `gradle-wrapper.jar`，因此不能直接双击或执行 `gradlew.bat`。云端构建版通过 GitHub Actions安装Gradle 8.7，不依赖该缺失文件。
