# Network Automation automation with OpenDayLight

- The ODL Controller used in this repo is the commercial distribution from Brocade: Brocade SDN Controller (BSC) version 4.2 (today [Lumina Networks](https://www.luminanetworks.com/))
- Content of this repo:
	- [What is OpenDayLight (Brief introduction)]()
	- [How to Start/Stop the ODL conntroller]()
	- [ODL northbound API: RESTCONF]()
		- [Display the YANG modules defined in the controller]()

## What is OpenDayLight (Brief introduction):
- Vendor-driven consortium for developing open-source SDN controller platform.
- It is developed in Java and the latest Release: Carbon (April 2017)
- It employs a model-driven approach to describe the network, the functions to be performed on it and the resulting state. This model-driven approach is fundamental to ODL project, YANG is a data modeling language used to model configuration and state data manipulated. This modeling engine acts as a middleware between the southbound plugins (OpenFlow, NETCONF, OVSDB etc ...) and the northbound plugin: RESTCONF API.
- The content of this pack acts as a so called “SDN app” in the ODL nomenclature, in the sense where it consumes the ODL Northbound API (RESTCONF) to manipulate configuration and obtain states from the network. And because ODL is by nature multivendor, this can allow for multivendor network automation.
- For more information check the following links:


## How to Start/Stop the ODL conntroller:

```
mab@mab-infra:~$ sudo service brcd-bsc status 
● brcd-bsc.service
   Loaded: loaded (/etc/init.d/brcd-bsc; bad; vendor preset: enabled)
   Active: active (running) since lun. 2017-11-20 16:58:08 CET; 22s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 28358 ExecStart=/etc/init.d/brcd-bsc start (code=exited, status=0/SUCCESS)
   CGroup: /system.slice/brcd-bsc.service
           └─28593 /usr/bin/java -Djava.security.properties=/opt/brocade/bsc/controller/etc/odl.java.security -server -Xms128M -Xmx2048m -XX:+UnlockDiagnosticVMOptions -XX:+UnsyncloadClass -XX:+HeapDumpOn

nov. 20 16:58:06 mab-infra systemd[1]: Starting brcd-bsc.service...
nov. 20 16:58:06 mab-infra sudo[28361]:     root : TTY=unknown ; PWD=/ ; USER=brocade ; COMMAND=/opt/brocade/bsc/services/start
nov. 20 16:58:06 mab-infra sudo[28361]: pam_unix(sudo:session): session opened for user brocade by (uid=0)
nov. 20 16:58:08 mab-infra brcd-bsc[28358]: Starting Configuration Merge ...
nov. 20 16:58:08 mab-infra brcd-bsc[28358]: Done with Configuration Merge ...
nov. 20 16:58:08 mab-infra brcd-bsc[28358]: Checking if clean requested...
nov. 20 16:58:08 mab-infra brcd-bsc[28358]: No clean requested.
nov. 20 16:58:08 mab-infra brcd-bsc[28358]: Starting controller ...
nov. 20 16:58:08 mab-infra systemd[1]: Started brcd-bsc.service.
mab@mab-infra:~$ 
mab@mab-infra:~$ sudo service brcd-ui status 
● brcd-ui.service
   Loaded: loaded (/etc/init.d/brcd-ui; bad; vendor preset: enabled)
   Active: inactive (dead)
     Docs: man:systemd-sysv-generator(8)
mab@mab-infra:~$ 
mab@mab-infra:~$ sudo service brcd-ui start 
mab@mab-infra:~$  
mab@mab-infra:~$  sudo service brcd-ui status 
● brcd-ui.service
   Loaded: loaded (/etc/init.d/brcd-ui; bad; vendor preset: enabled)
   Active: active (running) since lun. 2017-11-20 16:58:53 CET; 2s ago
     Docs: man:systemd-sysv-generator(8)
  Process: 29015 ExecStart=/etc/init.d/brcd-ui start (code=exited, status=0/SUCCESS)
   CGroup: /system.slice/brcd-ui.service
           └─29058 /usr/bin/node /opt/brocade/ui/web/bin/../app/index.js

nov. 20 16:58:53 mab-infra sudo[29049]:     root : TTY=unknown ; PWD=/ ; USER=brocade ; COMMAND=/usr/bin/python /opt/brocade/configuration/.lib/configuration_manager.py -l /opt/brocade/ui/services/ui-conf
nov. 20 16:58:53 mab-infra sudo[29049]: pam_unix(sudo:session): session opened for user brocade by (uid=0)
nov. 20 16:58:53 mab-infra sudo[29049]: pam_unix(sudo:session): session closed for user brocade
nov. 20 16:58:53 mab-infra brcd-ui[29015]: Switching to brocade user...
nov. 20 16:58:53 mab-infra sudo[29052]:     root : TTY=unknown ; PWD=/ ; USER=brocade ; COMMAND=/opt/brocade/ui/web/bin/start
nov. 20 16:58:53 mab-infra sudo[29052]: pam_unix(sudo:session): session opened for user brocade by (uid=0)
nov. 20 16:58:53 mab-infra brcd-ui[29015]: /opt/brocade/ui/web/bin/brcd-ui.pid found but pid 20532 was not running
nov. 20 16:58:53 mab-infra brcd-ui[29015]: brcd-ui started
nov. 20 16:58:53 mab-infra sudo[29052]: pam_unix(sudo:session): session closed for user brocade
nov. 20 16:58:53 mab-infra systemd[1]: Started brcd-ui.service.
mab@mab-infra:~$
```

## ODL Northbound API: RESTCONF

- OpenDayLight exposes a northbound API based on RESTCONF.
- RESTCONF is based on [IETF RFC 8040](https://tools.ietf.org/html/rfc8040)
- RESTCONF extends the idea of NETCONF, by relying on a REST API type of access.
- Model definition in YANG
- JSON or XML are used for data representation

- RESTCONF defines how a YANG model is mapped to a RESTful interface, specifically:
  - how to modify the data by using REST verbs (GET / PUT / PATCH / …)
  - how to construct URIs to access the model / data
