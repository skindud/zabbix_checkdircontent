<!-- PROJECT SHIELDS -->
<!--
*** I'm using markdown "reference style" links for readability.
*** Reference links are enclosed in brackets [ ] instead of parentheses ( ).
*** See the bottom of this document for the declaration of the reference variables
*** for contributors-url, forks-url, etc. This is an optional, concise syntax you may use.
*** https://www.markdownguide.org/basic-syntax/#reference-style-links
-->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

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


<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/skindud/repo_name.svg?style=for-the-badge
[contributors-url]: https://github.com/skindud/repo_name/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/skindud/repo_name.svg?style=for-the-badge
[forks-url]: https://github.com/skindud/repo_name/network/members
[stars-shield]: https://img.shields.io/github/stars/skindud/repo_name.svg?style=for-the-badge
[stars-url]: https://github.com/skindud/repo_name/stargazers
[issues-shield]: https://img.shields.io/github/issues/skindud/repo_name.svg?style=for-the-badge
[issues-url]: https://github.com/skindud/repo_name/issues
[license-shield]: https://img.shields.io/github/license/skindud/repo_name.svg?style=for-the-badge
[license-url]: https://github.com/skindud/repo_name/blob/master/LICENSE.txt
[product-screenshot]: images/screenshot.png
