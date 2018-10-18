## 自動化安裝LibreNMS
LibreNMS是一套開源的網路裝置管理軟體，其分支於Observium，並且加入了社群版沒有的Alert功能。

本專案為自動化安裝LibreNMS Shell Script。


## 安裝步驟：

### Step 1:
    git clone https://github.com/BensonRUEI/Librenms-Install-Shell.git
  
### Step 2:
根據系統不同執行不同的Shell Script，並且建議使用root來進行安裝。
  
  
#### CentOS 7 以上
  
    sh Librenms-Install-Shell/Centos7_install.sh
  
#### Ubuntu 16.04 以上
  
    sh Librenms-Install-Shell/ubuntu_install.sh

### Step 3:
開啟瀏覽器連至：http://YourIP/install.php ,根據內容進行相關設定(如DB Password、DB Name)。

### Step 4:
新增config.php文件至/opt/librenms

### Step 5:
    chown librenms:librenms /opt/librenms/config.php
   
### Switch SNMP 設定教學
請自行修改IP與CommunityString

    #CISCO
    conf t
    snmp-server community CommunityString
    snmp-server enable trap 
    snmp-server host IP version 2c CommunityString
    end
    write memory 


    #Aruba
    configure t
    snmp-server community CommunityString
    snmp-server enable trap 
    snmp-server host IP version 2c CommunityString
    exit
    write memory
