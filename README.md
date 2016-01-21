Zabbix template Check Dir Content
==================

Description
-----------------
- two way checking: file/dir structure and the same things with additional file size/time
- description
simple installation - based on /proc/mdstat and zabbix regexp item without Low Level Discovery;
- not use any additional files/actions on monitored server(s), only zabbix agent is needed;
- correctly worked on every linux OS even if linux don't have raid.
- any raid numbers are available;
- show the problem with raid without detalization;
- checked status of raids once an hour

TO DO list
------

- try to make universal template with a number of checking folders by adding {$MACRO} variables

Installation
----------------

- add dir_check_files.conf to /etc/zabbix/zabbix_agentd.d/ and restart zabbix;
- install tree utility on observed server (yum install tree) for 1st way of checking;
- import Zabbix template (zbx_template_checkdircontent.xml), add {$CHECK_DIR}/{$MD5SUM} for the 1st way (tree) and {$CHECK_DIR_V2}/{$MD5SUM_V2} for the 2nd way (find) of checking;
- add template to the monitored servers.
