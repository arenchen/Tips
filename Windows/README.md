# Windows Tips
## 變更 Windows 8 Or Windows Server 2012 網路類別
```shell
# 察看欲修改網路的 InterfaceIndex
Get-NetConnectionProfile

Set-NetConnectionProfile  -InterfaceIndex [InterfaceIndex] -NetworkCategory [Public|Private]
```

## 清除事件檢視器所有事件
```shell
wevtutil el | foreach { wevtutil cl $_ }
```

## 如何在 Windows 登入畫面中隱藏其他使用者
```
HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Winlogon\SpecialAccounts\UserList

Add DWORD
Name = Username
Value = 0
```

## Hiberfil.sys
```shell
powercfg –h off
```
