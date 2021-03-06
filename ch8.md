# ch8 系統行程管理

* process 行程
* context switching 切換
* processcs 多工
* thread 線程
************************************************
## 行程狀態指令 -ps
* ps指令(Process status)
 
* ![](https://github.com/sps326532/108linux--note/blob/master/1.PNG)
 
 1. PID (Process ID，行程識別碼)：當行程被啟動，會被賦予一個 ID 為識別碼，每個行程都有自己所屬的 ID，管理者可 PID 來傳送信號給這些行程。
 2. TTY 控制終端機：在何種終端機上面運作，若與終端機無關，則顯示 ?。
 tty1-tty6 是本機上面的登入者程序 (Ctrl + Alt + Fn)，若為 pts/0 等等的，則表示為由網路連接進主機的程序，若為 ? 則代表背景執行程式。
 3. TIME：目前為止所占用 CPU 的時間，使用者於命令列觸發的行程 (如 ls)，他們的「生命期」多半相當短暫。但是對於提供公共服務的行程 (如 Apache web server)，他們的生命期就相當長，甚至是在系統啟動之後就開始，直到關機或管理者給予結束才終止。
4. CMD：命令名稱
*************************************************************************************************************************
* ![](https://github.com/sps326532/108linux--note/blob/master/2.PNG)

1. UID：誰執行後面程式
2. 第一行是bash行程，為登入成功後執行的程式
3. 第二行是執行 ps指令的行程資訊
4. ps 加上 -f會變成更加詳細
5. PPID(Parent Process ID)，是父行程的編號，代表該行程的父行程編號ㄕ
6. 在第二行的資訊是 ps-f行程，這行程是由bash行程衍生出來的子行程(bash是ps-f的父行程)

**********************************************************************************
## 8-1-1活用行程列表 -ps
* ![](https://github.com/sps326532/108linux--note/blob/master/3.PNG)

1. 在centos7中：pid=1,systemd=第一次
2. 圖旁邊的root為是誰執行
3. USER=該行程的擁有者
4. PID=該行程的PID
5. %CPU=CPU使用率
6. %MEM=記憶體使用率
7. VSZ=虛擬記憶體的使用量，以KB為單位
8. RSS=固定占用的記憶體，以KB為單位
9. TTY=該行程是由哪一個終端機編號所產生的，因為上圖都是系統服務，因此TTY顯示為問號?
10. STAT=行程目前狀態。S代表正處於睡眠中，R代表在執行當中
11. START=紀錄行程被啟動時的日期
12. TIME=實際使用CPU的時間
13. COMMAND=該行程的指令

* grep，只列出符合服務名稱的該行即可：ex crond
* ![](https://github.com/sps326532/108linux--note/blob/master/4.PNG)
1. 第一行指令是crond，為系統的crond服務
2. 第二行則是致令中管線後面的第二個指令grep crond
***************************************************************************************




