# Installation Tips
## 安裝 Windows 7 時，將預設的使用者資料夾，移至其他位置
在安裝新的 Windows 7 或 Windows 8 時，當安裝步驟到了要你輸入 使用者名稱 & 電腦名稱 時：  
按下「Shift」+「F10」鍵，開啟命令提示字元視窗，依序輸入下列指令：
```shell
robocopy "C:\Users" "D:\Users" /E /COPYALL /XJ 
rmdir "C:\Users" /S /Q 
mklink /J "C:\Users" "D:\Users
```

若安裝 Windows Update 失敗時，可能是安裝的 Package 無法識別 Link 資料夾，此時可以修改下列機碼：
```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\ProfileList 

Default、ProfilesDirectory、Public 字串值  

將 %SystemDrive% 修改成實體路徑，例如：D: 
```
