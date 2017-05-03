# Mac-Tips
## Index
- [為 macOS 製作可開機安裝程式](Create-Install-Media.md)

## 快速鍵
- 螢幕截圖
  - Command-Shift-3：擷取整個桌面
  - Command-Shift-4：圈選特定區域畫面
  - Command-Shift-4，按一下空白鍵，再點擊視窗：擷取該視窗畫面並自動去背
  - Command-Shift-4，先拖曳，再按住空白鍵移動：可以移動選取區域
  - Command-Shift-4，按住 Shift 拖曳：可以鎖定寬度或高度
  - Command-Shift-4，按住 Option 拖曳：可以以中心位置做面積縮放
  
> 以上熱鍵加按 Control，可以將圖片直接存到剪接簿中，而不是存成獨立檔案，要用時再按 Command-V 貼出來。

## 開啟「允許任何來源」 App 限制
- 開啟
```shell
sudo spctl --master-disable
```
- 關閉
```shell
sudo spctl --master-enable
```

## 顯示/隱藏系統檔案
- 顯示：
```shell
defaults write com.apple.finder AppleShowAllFiles TRUE;\killall Finder
```
- 隱藏：
```shell
defaults write com.apple.finder AppleShowAllFiles FALSE;\killall Finder
```

## 防止 .DS\_Store 檔案生成
- 禁止 .DS\_Store 生成：
```shell
defaults write com.apple.desktopservices DSDontWriteNetworkStores true
```
- 恢復 .DS\_Store 生成：
```shell
defaults delete com.apple.desktopservices DSDontWriteNetworkStores
```

## 修改主要語言
```shell
sudo "/System/Library/CoreServices/Language Chooser.app/Contents/MacOS/Language Choose
```

## 安裝 Homebrew
```shell
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

## 更改螢幕快照預設儲存路徑
```shell
defaults write com.apple.screencapture location ~/Documents
```

## 找出特定檔案並刪除
```shell
find ./ -type f | grep 關鍵字 | xargs rm
find ./ ( -iname "關鍵字" -o -iname "關鍵字" ) -print0 | xargs -0 rm -rf
```
- 刪除 Mac OS X 快取檔案
```shell
find /media -type f -size -4096b ! -ipath "*/.recycle/*" -a \( -iname ".DS_Store" -o -iname "._*" \) -print0 | xargs -0 rm -v -rf
```
- 刪除 Windows 縮圖檔案
```shell
find /media -type f -a ! -ipath "*/.recycle/*" -iname "thumbs.db" -print0 | xargs -0 rm -v -rf
```
