# Linux-Tips
## netstat
>-a 或 –all 顯示所有連線中的 Socket。  
-A<網路類型> 或 –<網路類型> 列出該網路類型連線中的相關位址。  
-c 或 –continuous 持續列出網路狀態。  
-C 或 –cache 顯示路由器配置的快取資訊。  
-e 或 –extend 顯示網路其他相關資訊。  
-F 或 –fib 顯示 FIB。  
-g 或 –groups 顯示多重廣播功能群組組員名單。  
-h 或 –help 線上幫助。  
-i 或 –interfaces 顯示網路介面資訊表單。  
-l 或 –listening 顯示監控中的伺服器的 Socket。  
-M 或 –masquerade 顯示偽裝的網路連線。  
-n 或 –numeric 直接使用 IP 地址，而不通過功能變數名稱伺服器。  
-N 或 –netlink 或 –symbolic 顯示網路硬體週邊設備的符號連接名稱。  
-o 或 –timers 顯示計時器。  
-p 或 –programs 顯示正在使用 Socket 的程式識別碼和程式名稱。  
-r 或 –route 顯示 Routing Table。  
-s 或 –statistice 顯示網路工作資訊統計表。  
-t 或 –tcp 顯示 TCP 傳輸協定的連線狀況。  
-u 或 –udp 顯示 UDP 傳輸協定的連線狀況。  
-v 或 –verbose 顯示指令執行過程。  
-V 或 –version 顯示版本資訊。  
-w 或 –raw 顯示 RAW 傳輸協議的連線狀況。  
-x 或 –unix 此參數的效果和指定 "-A unix" 參數相同。  
–ip 或 –inet 此參數的效果和指定 "-A inet" 參數相同。  

```shell
sudo netstat -lptu
sudo netstat -tulpn
```

## 調整 ext4 預設 5% 保留空間
```shell
# 把 5％ 改成 1％
sudo tune2fs -m 1 /dev/sdb1
```
