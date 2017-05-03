# 為 macOS 製作可開機安裝程式
在 macOS Sierra、El Capitan、Yosemite 或 Mavericks 中，您可以將 USB 隨身碟或其他卸除式媒體做為啟動磁碟，然後從該磁碟安裝 Mac 作業系統。
** 這些進階步驟主要是為系統管理者及其他熟悉命令列的人員提供。**

## 在「終端機」中使用 createinstallmedia 指令
1. 從 Mac App Store 下載 macOS 安裝程式。下載完畢後，如果安裝程式自動開啟，請將它結束。安裝程式會位於「應用程式」檔案夾。
2. 裝載您的 USB 隨身碟或其他卷宗。您也可以使用次要內部分割區。
3. 開啟「終端機」app（位於「應用程式」檔案夾的「工具程式」檔案夾中）。
4. 在「終端機」中使用 **createinstallmedia** 指令，以建立可開機安裝程式。如需詳細的使用說明，請確定「應用程式」檔案夾中有適當的 macOS 安裝程式，接著在「終端機」中輸入下列其中一種路徑：
  - Sierra 的路徑：  
  ```shell
  /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia
  ```
  - El Capitan 的路徑：  
  ```shell
  /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia
  ```
  - Yosemite 的路徑：  
  ```shell
  /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia
  ```
  - Mavericks 的路徑：  
  ```shell
  /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia
  ```

## 範例
這是指令的基本語法。  
請將 **volumepath** 換成您 USB 隨身碟或其他卷宗的路徑，並將 **installerpath** 換成「安裝 OS X」app 的路徑。  
```shell
createinstallmedia --volume volumepath --applicationpath installerpath
```

下列範例假設 OS X 安裝程式位於您的「應用程式」檔案夾，而您的 USB 隨身碟或其他卷宗的名稱為 MyVolume：
- Sierra 的範例：
```shell
sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ macOS\ Sierra.app
```
- El Capitan 的範例：
```shell
sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app
```
- Yosemite 的範例：
```shell
sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Yosemite.app
```
- Mavericks 的範例：
```shell
sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Mavericks.app
```
