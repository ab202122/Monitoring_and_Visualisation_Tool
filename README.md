# Monitoring_-_Visualisation_Tool
# Requirements
The visualization tool runs on AWS cloud so the developer needs to register and open an account to use the Elastic stack for Kibana. 
The agent software (Filebeat) is embedded in the Installer for the Intrusion Detection System module and was customized and tested for the following IoT gateway test devices:
* OpenBlocks IoT BX1 Gateway Device 
     Raspberry-Pi  
     Firmware: installed version: 1.0.14-1 / OBSBX1 3.10.17-17
     Hardware: Intel Atom Processor (500MHz, 1024KB) 
     Software: Debian GNU/Linux - version 3.10.17-poky-edison 

# User Guides 
The following manufacturer guides are useful for installing and operating the OpenBlocks IoT gateways:  

* https://openblocks.plathome.co.jp/common/pdf/obsiot_developer_guide.pdf 
* https://openblocks.plathome.co.jp/common/pdf/obsiot_webui_setup_guide.pdf

# Download & Installation  

Download “installer.sh” file onto your Openblocks IoT gateway device and execute as follows:  

IoT-1# 	ls -l
total 52320
-rw-r--r--    1 	root root	    41404017	Mar 25 2021 	installer.sh

IoT-1# 	 ./installer.sh 

This will install all the customized files onto your IoT device. 

IoT-1# 	ls -l 
total 52344
-rwxr-xr-x	 1 	spp  spp	   1103 	Jan  1 2020 hardening.sh
drwxr-xr-x  4 	root root	   4096 	Mar 09 2021 installer
-rw-r--r--  1 	root root 41404017	Mar 25 2021 installer.sh
-rwxr-xr-x	 1 	spp  spp	    149 	Jan  1 2020 start_ids.sh
-rwxr-xr-x	 1 	spp  spp	    169 	Jan  1 2020 start_ips.sh
drwxr-xr-x  2 	root root	   4096 	Jan  1 2020 update 
-rw-r--r--  1 	root root	   1435 	Jan  1 2020 updater.py
-rw-r--r--  1 	root root	    227 	Nov 16 2020 version.yaml 

# Verify Installation & Running 

* Agent for the Visualization Tool: 

IoT-1# 	/etc/init.d/filebeat status
filebeat is running.

If not running or failed, then restart it using below command: 

IoT-1# 	/etc/init.d/filebeat start

* For default running of IDS security feature 

Once everything is configured and tested, then Add following commands in the default boot config file to enable security by default

/etc/init.d/filebeat start

The above commands will enable both Visualization Tool (Filebeat) and IDS/IPS security features to start whenever the IoT device gets booted. 
