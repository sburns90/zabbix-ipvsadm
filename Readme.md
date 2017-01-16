Zabbix IPVSADM Module
====

Installation
----
Do the following on the host with zabbix-agent:

* Put *ipvsadm_discover.sh* and *ipvsadm.py* in */etc/zabbix*
* Both files need the following permissions:
 * mode:   *754*
 * user:   *root*
 * group:  *zabbix*
* Put *ipvsadm.conf* in */etc/zabbix/zabbix_agentd.conf.d/*
* Rename *zabbix_ipvsadm_sudoers* to *zabbix_ipvsadm* and put it in */etc/sudoers.d/*
 * DO **NOT** EDIT THE /etc/sudoers FILE AT ALL UNLESS YOU **USE VISUDO** AND KNOW WHAT YOU ARE DOING!
* Restart the zabbix-agent:   <code>sudo service zabbix-agent restart</code>


Zabbix Server
----
* To test the functionality
* On the zabbix server run:  <code>zabbix_get -s $IPADDRESS -k ipvsadm.discovery</code>
 * REPLACE $IPDADDRESS with the IP 
* If you get output that does NOT say "Permissions Denied" then it works!.
* Import the *Template_LVS_connections.xml* template


History & Credit
--------------
* Major credit goes to Yxnt for fixing the JSON formatting issue which prevented the module from working.

* Forked from Yxnt @ https://github.com/Yxnt/zabbix-ipvsadm.
* Original Zabbix module from shinonome @ https://github.com/shinonome/zabbix_ipvsadm **(unmaintained)**
* Original code & concept from shota @ https://www.zabbix.com/forum/showthread.php?t=12086 **(unmaintained)**

Screenshot from the final product on the zabbix server.
![](ipvsadm.png)
Image above is fom Yxnt.
