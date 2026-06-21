# 不安装 Android Studio，使用 GitHub Actions 云端生成 APK

## 一、准备

1. 注册并登录 GitHub。
2. 新建一个仓库，例如 `FlowerAgentNative`。
3. 将本项目文件全部上传到仓库根目录。
   - 上传后仓库首页应直接看到 `app`、`build.gradle`、`settings.gradle`、`.github`。
   - 不要再多套一层文件夹。

## 二、开始构建

1. 打开仓库。
2. 点击顶部 `Actions`。
3. 左侧选择 `Build Android APK`。
4. 点击右侧 `Run workflow`。
5. 再点击绿色 `Run workflow`。
6. 等待构建完成。

## 三、下载 APK

1. 点开已经完成、显示绿色对勾的构建记录。
2. 页面底部找到 `Artifacts`。
3. 下载 `FlowerAgentNative-debug-apk`。
4. 解压后得到 `app-debug.apk`。
5. 将APK复制到广告机安装。

## 四、说明

- 这个APK是调试签名版，可直接安装测试。
- 若后续需要正式签名版，需要增加签名文件和GitHub Secrets配置。
- 当前工程最低支持 Android 4.1（minSdk 16）。
