# 為 macOS 製作可開機安裝程式
在 macOS High Sierra、Sierra、El Capitan、Yosemite 或 Mavericks 中，您可以將 USB 隨身碟或其他儲存媒體做為啟動磁碟，然後從該磁碟安裝 Mac 作業系統。  
  
您並不需要可開機安裝程式來[重新安裝 macOS](https://support.apple.com/zh-tw/HT204904)，不過當您想在多台電腦上安裝 macOS 時，開機安裝程式就很實用。這些是進階步驟，主要為系統管理者及其他熟悉命令列的人員提供。
    
## 從 App Store 下載 macOS 安裝程式
1. 從 Mac App Store 下載 macOS 安裝程式。安裝程式會以名稱開頭為「Install」的單一檔案下載到您的「應用程式」檔案夾。例如：Install macOS High Sierra。
2. 如果安裝程式在下載後自動開啟，請結束安裝程式。
3. 裝載將要放置安裝媒體的 USB 隨身碟、外接硬碟、次要內部分割區或其他儲存媒體。確認它至少具有 12GB 可用儲存空間。

## 在「終端機」中使用 createinstallmedia 指令
1. 下載安裝程式後，開啟「終端機」app（位於「應用程式」檔案夾的「工具程式」檔案夾）。
2. 在「終端機」中使用 createinstallmedia 指令，以建立可開機安裝程式。這是指令的基本語法：
High Sierra 的語法：
```shell
createinstallmedia --volume volumepath
```
Sierra 和之前版本的語法：
```shell
createinstallmedia --volume volumepath --applicationpath installerpath
```
請將 volumepath 換成您 USB 隨身碟或其他卷宗的路徑。將 installerpath 換成安裝程式的路徑。
---------------------------------------
下列範例假設安裝程式位於您的「應用程式」檔案夾，而您的 USB 隨身碟或其他卷宗的名稱為 MyVolume：

High Sierra 的範例：
```shell
sudo /Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume
```

Sierra 的範例：
```shell
sudo /Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ macOS\ Sierra.app
```

El Capitan 的範例：
```shell
sudo /Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ El\ Capitan.app
```

Yosemite 的範例：
```shell
sudo /Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Yosemite.app
```

Mavericks 的範例：
```shell
sudo /Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia --volume /Volumes/MyVolume --applicationpath /Applications/Install\ OS\ X\ Mavericks.app
```

## 更多內容
如需 **createinstallmedia** 指令的更多資訊，請確認 macOS 安裝程式位於您的「應用程式」檔案夾，然後在「終端機」中輸入適當的路徑：

High Sierra 的路徑：
```shell
/Applications/Install\ macOS\ High\ Sierra.app/Contents/Resources/createinstallmedia
```

Sierra 的路徑：
```shell
/Applications/Install\ macOS\ Sierra.app/Contents/Resources/createinstallmedia
```

El Capitan 的路徑：
```shell
/Applications/Install\ OS\ X\ El\ Capitan.app/Contents/Resources/createinstallmedia
```

Yosemite 的路徑：
```shell
/Applications/Install\ OS\ X\ Yosemite.app/Contents/Resources/createinstallmedia
```

Mavericks 的路徑：
```shell
/Applications/Install\ OS\ X\ Mavericks.app/Contents/Resources/createinstallmedia
```

Ref https://support.apple.com/zh-tw/HT201372
