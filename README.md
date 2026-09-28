# 钢铁前线：卡牌对决

原创军事题材卡牌对战原型：单机 AI 对战、自定义整张卡牌贴图、卡牌效果编辑、本机自动保存、JSON 卡组导入/导出。

## 出战卡组和战斗队列

在「卡牌工坊」选择 8 张出战卡，卡牌可以重复选择，加入顺序就是战斗顺序。战斗时手牌区域一次展示队列里的 4 张；打出一张后，下一张立即补位。新一局使用当前选定的 8 张。

卡牌工坊要求新建卡牌上传贴图。图片会压缩后用作整张卡面，手牌和战场上的单位都以完整卡牌显示；卡面不使用 emoji 图标。默认卡牌带有可编辑的抽象战场纹理。

## GitHub Actions 云端构建 APK

1. 把本目录内的全部内容上传到 GitHub 仓库根目录（不要只上传 `app/`）。
2. 推送到 `main` 或 `master` 分支，或在仓库 **Actions → Build Android APK → Run workflow** 手动启动。
3. 构建完成后，在运行详情页下载 `steel-front-apk` artifact，解压即可得到 `app-debug.apk`。

工作流会安装 Temurin JDK 17、Gradle 8.9、Android SDK 35，创建 Gradle Wrapper 并执行 `./gradlew --no-daemon assembleDebug`。APK artifact 保留 30 天。

## 本地构建

需要 Android Studio、JDK 17 和 Android SDK 35。用 Android Studio 打开本目录，等待 Gradle 同步后选择 **Build → Build Bundle(s) / APK(s) → Build APK(s)**。
