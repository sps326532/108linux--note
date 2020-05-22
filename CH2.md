## 2020/03/10
* ifconfig→查詢網路
*************************************************
 1. NAT：hetwork address translation
     - centos 可看到Internet上的機器但Internet上的機器看不到centos
     - 在virtualbox內，centos看不到win，win也看不到centos，但在VWMARET，centos和windows可互相看到
 
 2.Hos only 模式
    - centos和windows可互相看到，但centos不能看到Internet上的機器
 
 3. Bridge 橋切設定
 **************************************************
 *  傳統與現代linux
      傳統 | 現代
      -----|--------
      eth0 | enpos3
      eth1 | enpos8
      eth1 | enpos9
   - 以上是linux網路卡命名方式
***************************************************
* ipconfig /all 及 netstat-rn
      -  查看網路卡資訊
* netstat -an
      -  查看實體機上那些埠被打開
 **************************************************
 * Linux提供的三種標準I/O
  1. standard input(STDIN)代號0：標準輸入，預設為鍵盤
  2. standard output(STDOUT)代號1：標準輸出，預設為終端機視窗
  3. standard error(STDERR)代號2：標準錯誤輸出，預設為終端機視窗
 **************************************************
 * 終端機指令
  - echo：反映指令，打什麼就傳回什麼
  - echo hell (在此省略“’”)>Desktop/1.txt→建立內文為hello的文本
 * Desktop/1.txt
    - 若文字檔存在，清空內容
    - 若文字檔不存在，建立文字檔
 **************************************************
 * 關機方法
  1. reboot 重啟動
  2. halt - p 
  3. power off
 ****************************************************
 * su=切換為系統管理員(在Linux中為root，提示符號為#，若身分為p)
 * yum install=安裝軟體指令
 * systemctrl stop 伺服器名稱(E.g.ssh)d：關閉伺服器
 * systemctrl stop 伺服器名稱(E.g.ssh)d：啟動伺服器
 * systemctrl status 伺服器名稱(E.g.ssh)d ：檢查伺服器狀態
 *******************************************************
 * netstat-tulnp|grep.22
    - t=檢查TCP連線
    - u=檢查UDP連線
    - l=Listen 
    - n=不解析
    - p=process ID
    - grep=過濾器
 ********************************************************
 * 遠端桌面連線方式
  - 開啟方式→開始→搜尋列上輸入“mstsc”
  - 輸入欲連線到的電腦IP後加上冒號+埠號-E.g.192.168.1.150.5566
  ********************************************************
  * 再製
    1.完整再製：浪費磁碟空間但效能好
    2.連結再製：節省磁碟空間但效能差
