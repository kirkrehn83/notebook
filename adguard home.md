---
share: true
---
> [!NOTE] synopsis
> network-wide dns ad-blocker

## faq
---
| **item** | **description** |
| --- | --- |
| url | kirklabz.nohost.me/adguard |
| root user | kirkrehn |
| root password | kirkster |
| root e-mail | kirk@kirkrehn.online |

## logs
---

### install logs

```sh
args:
  app: adguardhome
  force: false
  label: AdGuard Home
  no_remove_on_failure: false
ended_at: 2023-03-29 05:10:17.160920
env:
  YNH_APP_ACTION: install
  YNH_APP_ARG_ADMIN: kirkrehn
  YNH_APP_ARG_DNS_OVER_HTTPS: '1'
  YNH_APP_ARG_DOMAIN: domain2.tld
  YNH_APP_ARG_PATH: /adguard
  YNH_APP_BASEDIR: /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y
  YNH_APP_ID: adguardhome
  YNH_APP_INSTANCE_NAME: adguardhome
  YNH_APP_INSTANCE_NUMBER: '1'
  YNH_APP_MANIFEST_VERSION: 0.107.26~ynh1
  YNH_APP_PACKAGING_FORMAT: '1.0'
  YNH_ARCH: arm64
  YNH_DEBIAN_VERSION: bullseye
error: null
interface: api
operation: app_install
parent: null
related_to:
- - app
  - adguardhome
started_at: 2023-03-29 05:08:37.104859
success: true
yunohost_version: 11.1.15

============

2023-03-28 22:08:37,123: INFO - Installing adguardhome...
2023-03-28 22:08:37,879: DEBUG - Nothing to update in LDAP
2023-03-28 22:08:37,880: DEBUG - Permission 'adguardhome.main' updated
2023-03-28 22:08:38,292: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230329-050837-permission_url-adguardhome" style="text-decoration:underline">Update URL related to permission 'adguardhome'</a>'
2023-03-28 22:08:39,068: DEBUG - The permission database has been resynchronized
2023-03-28 22:08:39,669: DEBUG - SSOwat configuration regenerated
2023-03-28 22:08:40,053: DEBUG - Permission 'adguardhome.main' created
2023-03-28 22:08:40,054: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230329-050837-permission_create-adguardhome" style="text-decoration:underline">Create permission 'adguardhome'</a>'
2023-03-28 22:08:40,104: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./install"  7>&1']'
2023-03-28 22:08:40,126: DEBUG - + source _common.sh
2023-03-28 22:08:40,127: DEBUG - ++ pkg_dependencies='python3-bcrypt python3-yaml'
2023-03-28 22:08:40,128: DEBUG - + source /usr/share/yunohost/helpers
2023-03-28 22:08:40,128: DEBUG - +++ set +o
2023-03-28 22:08:40,128: DEBUG - +++ grep xtrace
2023-03-28 22:08:40,131: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-28 22:08:40,132: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-28 22:08:40,169: DEBUG - + ynh_abort_if_errors
2023-03-28 22:08:40,171: DEBUG - + trap ynh_exit_properly EXIT
2023-03-28 22:08:40,171: DEBUG - + domain=domain2.tld
2023-03-28 22:08:40,171: DEBUG - + path_url=/adguard
2023-03-28 22:08:40,171: DEBUG - + admin=kirkrehn
2023-03-28 22:08:40,172: DEBUG - + password=**********
2023-03-28 22:08:40,172: DEBUG - + dns_over_https=1
2023-03-28 22:08:40,173: DEBUG - + app=adguardhome
2023-03-28 22:08:40,364: INFO - [....................] > Validating installation parameters...
2023-03-28 22:08:40,367: DEBUG - + final_path=/var/www/adguardhome
2023-03-28 22:08:40,367: DEBUG - + test '!' -e /var/www/adguardhome
2023-03-28 22:08:40,368: DEBUG - + ynh_webpath_register --app=adguardhome --domain=domain2.tld --path_url=/adguard
2023-03-28 22:08:40,522: DEBUG - + yunohost app register-url adguardhome domain2.tld /adguard
2023-03-28 22:08:45,541: INFO - [++..................] > Storing installation settings...
2023-03-28 22:08:45,543: DEBUG - + ynh_app_setting_set --app=adguardhome --key=domain --value=domain2.tld
2023-03-28 22:08:45,543: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:45,696: DEBUG - + app=adguardhome
2023-03-28 22:08:45,696: DEBUG - + [[ domain =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:45,697: DEBUG - + ynh_app_setting set adguardhome domain domain2.tld
2023-03-28 22:08:45,835: DEBUG - + ynh_app_setting_set --app=adguardhome --key=path --value=/adguard
2023-03-28 22:08:45,835: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:45,989: DEBUG - + app=adguardhome
2023-03-28 22:08:45,990: DEBUG - + [[ path =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:45,991: DEBUG - + ynh_app_setting set adguardhome path /adguard
2023-03-28 22:08:46,124: DEBUG - + ynh_app_setting_set --app=adguardhome --key=admin --value=kirkrehn
2023-03-28 22:08:46,125: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:46,285: DEBUG - + app=adguardhome
2023-03-28 22:08:46,286: DEBUG - + [[ admin =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:46,286: DEBUG - + ynh_app_setting set adguardhome admin kirkrehn
2023-03-28 22:08:46,419: DEBUG - + '[' 1 == 1 ']'
2023-03-28 22:08:46,420: DEBUG - + dns_over_https=true
2023-03-28 22:08:46,420: DEBUG - + adguard_DoT_port=853
2023-03-28 22:08:46,421: DEBUG - + ynh_app_setting_set --app=adguardhome --key=adguard_DoT_port --value=853
2023-03-28 22:08:46,421: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:46,572: DEBUG - + app=adguardhome
2023-03-28 22:08:46,573: DEBUG - + [[ adguard_DoT_port =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:46,574: DEBUG - + ynh_app_setting set adguardhome adguard_DoT_port 853
2023-03-28 22:08:46,705: DEBUG - + ynh_exec_warn_less yunohost firewall allow --no-upnp UDP 853
2023-03-28 22:08:46,706: DEBUG - + [[ 6 -eq 1 ]]
2023-03-28 22:08:46,706: DEBUG - + yunohost firewall allow --no-upnp UDP 853
2023-03-28 22:08:47,151: DEBUG - Port 853 is already opened for IPv4 connections
2023-03-28 22:08:47,151: DEBUG - Port 853 is already opened for IPv6 connections
2023-03-28 22:08:48,858: DEBUG - Firewall reloaded
2023-03-28 22:08:48,872: DEBUG - opened_ports:
2023-03-28 22:08:48,873: DEBUG -   - 22
2023-03-28 22:08:48,873: DEBUG -   - 25
2023-03-28 22:08:48,874: DEBUG -   - 53
2023-03-28 22:08:48,874: DEBUG -   - 80
2023-03-28 22:08:48,875: DEBUG -   - 443
2023-03-28 22:08:48,875: DEBUG -   - 547
2023-03-28 22:08:48,875: DEBUG -   - 587
2023-03-28 22:08:48,876: DEBUG -   - 784
2023-03-28 22:08:48,876: DEBUG -   - 853
2023-03-28 22:08:48,876: DEBUG -   - 993
2023-03-28 22:08:48,876: DEBUG -   - 1883
2023-03-28 22:08:48,877: DEBUG -   - 1900
2023-03-28 22:08:48,877: DEBUG -   - 5222
2023-03-28 22:08:48,877: DEBUG -   - 5269
2023-03-28 22:08:48,879: DEBUG -   - 5353
2023-03-28 22:08:48,879: DEBUG -   - 7359
2023-03-28 22:08:48,972: DEBUG - + ynh_exec_warn_less yunohost firewall allow --no-upnp TCP 853
2023-03-28 22:08:48,973: DEBUG - + [[ 6 -eq 1 ]]
2023-03-28 22:08:48,974: DEBUG - + yunohost firewall allow --no-upnp TCP 853
2023-03-28 22:08:49,407: DEBUG - Port 853 is already opened for IPv4 connections
2023-03-28 22:08:49,408: DEBUG - Port 853 is already opened for IPv6 connections
2023-03-28 22:08:50,591: DEBUG - Firewall reloaded
2023-03-28 22:08:50,604: DEBUG - opened_ports:
2023-03-28 22:08:50,605: DEBUG -   - 22
2023-03-28 22:08:50,606: DEBUG -   - 25
2023-03-28 22:08:50,606: DEBUG -   - 53
2023-03-28 22:08:50,607: DEBUG -   - 80
2023-03-28 22:08:50,607: DEBUG -   - 443
2023-03-28 22:08:50,607: DEBUG -   - 547
2023-03-28 22:08:50,608: DEBUG -   - 587
2023-03-28 22:08:50,608: DEBUG -   - 784
2023-03-28 22:08:50,609: DEBUG -   - 853
2023-03-28 22:08:50,609: DEBUG -   - 993
2023-03-28 22:08:50,610: DEBUG -   - 1883
2023-03-28 22:08:50,610: DEBUG -   - 1900
2023-03-28 22:08:50,610: DEBUG -   - 5222
2023-03-28 22:08:50,611: DEBUG -   - 5269
2023-03-28 22:08:50,612: DEBUG -   - 5353
2023-03-28 22:08:50,613: DEBUG -   - 7359
2023-03-28 22:08:50,705: DEBUG - + adguard_DoQ_port=784
2023-03-28 22:08:50,705: DEBUG - + ynh_app_setting_set --app=adguardhome --key=adguard_DoQ_port --value=784
2023-03-28 22:08:50,706: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:50,865: DEBUG - + app=adguardhome
2023-03-28 22:08:50,865: DEBUG - + [[ adguard_DoQ_port =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:50,866: DEBUG - + ynh_app_setting set adguardhome adguard_DoQ_port 784
2023-03-28 22:08:50,999: DEBUG - + ynh_exec_warn_less yunohost firewall allow --no-upnp UDP 784
2023-03-28 22:08:51,000: DEBUG - + [[ 6 -eq 1 ]]
2023-03-28 22:08:51,000: DEBUG - + yunohost firewall allow --no-upnp UDP 784
2023-03-28 22:08:51,428: DEBUG - Port 784 is already opened for IPv4 connections
2023-03-28 22:08:51,429: DEBUG - Port 784 is already opened for IPv6 connections
2023-03-28 22:08:52,647: DEBUG - Firewall reloaded
2023-03-28 22:08:52,660: DEBUG - opened_ports:
2023-03-28 22:08:52,660: DEBUG -   - 22
2023-03-28 22:08:52,661: DEBUG -   - 25
2023-03-28 22:08:52,662: DEBUG -   - 53
2023-03-28 22:08:52,662: DEBUG -   - 80
2023-03-28 22:08:52,662: DEBUG -   - 443
2023-03-28 22:08:52,663: DEBUG -   - 547
2023-03-28 22:08:52,663: DEBUG -   - 587
2023-03-28 22:08:52,663: DEBUG -   - 784
2023-03-28 22:08:52,664: DEBUG -   - 853
2023-03-28 22:08:52,664: DEBUG -   - 993
2023-03-28 22:08:52,664: DEBUG -   - 1883
2023-03-28 22:08:52,665: DEBUG -   - 1900
2023-03-28 22:08:52,665: DEBUG -   - 5222
2023-03-28 22:08:52,666: DEBUG -   - 5269
2023-03-28 22:08:52,666: DEBUG -   - 5353
2023-03-28 22:08:52,667: DEBUG -   - 7359
2023-03-28 22:08:52,761: DEBUG - + ynh_app_setting_set --app=adguardhome --key=dns_over_https --value=true
2023-03-28 22:08:52,762: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:52,917: DEBUG - + app=adguardhome
2023-03-28 22:08:52,918: DEBUG - + [[ dns_over_https =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:52,919: DEBUG - + ynh_app_setting set adguardhome dns_over_https true
2023-03-28 22:08:53,228: INFO - [##+.................] > Finding an available port...
2023-03-28 22:08:53,231: DEBUG - ++ ynh_find_port --port=3000
2023-03-28 22:08:53,256: DEBUG - ++ test -n 3000
2023-03-28 22:08:53,256: DEBUG - ++ ynh_port_available --port=3000
2023-03-28 22:08:53,283: DEBUG - ++ ss --numeric --listening --tcp --udp
2023-03-28 22:08:53,284: DEBUG - ++ awk '{print$5}'
2023-03-28 22:08:53,285: DEBUG - ++ grep --quiet --extended-regexp ':3000$'
2023-03-28 22:08:53,347: DEBUG - ++ grep -q 'port: '\''3000'\''' /etc/yunohost/apps/adguardhome/settings.yml /etc/yunohost/apps/elasticsearch7/settings.yml /etc/yunohost/apps/emoncms/settings.yml /etc/yunohost/apps/firefly-iii/settings.yml /etc/yunohost/apps/grocy/settings.yml /etc/yunohost/apps/homarr/settings.yml /etc/yunohost/apps/homeassistant/settings.yml /etc/yunohost/apps/jellyfin/settings.yml /etc/yunohost/apps/librespeed/settings.yml /etc/yunohost/apps/matomo/settings.yml /etc/yunohost/apps/mosquitto/settings.yml /etc/yunohost/apps/nextcloud/settings.yml /etc/yunohost/apps/nodered/settings.yml /etc/yunohost/apps/owntracks/settings.yml /etc/yunohost/apps/prettynoemiecms/settings.yml /etc/yunohost/apps/rainloop/settings.yml /etc/yunohost/apps/roundcube/settings.yml /etc/yunohost/apps/wikijs/settings.yml
2023-03-28 22:08:53,353: DEBUG - ++ return 0
2023-03-28 22:08:53,354: DEBUG - ++ echo 3000
2023-03-28 22:08:53,357: DEBUG - + port=3000
2023-03-28 22:08:53,358: DEBUG - + ynh_app_setting_set --app=adguardhome --key=port --value=3000
2023-03-28 22:08:53,358: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:53,596: DEBUG - + app=adguardhome
2023-03-28 22:08:53,601: DEBUG - + [[ port =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:53,602: DEBUG - + ynh_app_setting set adguardhome port 3000
2023-03-28 22:08:53,778: DEBUG - + adguard_port=53
2023-03-28 22:08:53,778: DEBUG - + ynh_app_setting_set --app=adguardhome --key=adguard_port --value=53
2023-03-28 22:08:53,779: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:08:53,935: DEBUG - + app=adguardhome
2023-03-28 22:08:53,936: DEBUG - + [[ adguard_port =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:08:53,937: DEBUG - + ynh_app_setting set adguardhome adguard_port 53
2023-03-28 22:08:54,071: DEBUG - + ynh_exec_warn_less yunohost firewall allow --no-upnp TCP 53
2023-03-28 22:08:54,072: DEBUG - + [[ 6 -eq 1 ]]
2023-03-28 22:08:54,072: DEBUG - + yunohost firewall allow --no-upnp TCP 53
2023-03-28 22:08:55,728: DEBUG - Firewall reloaded
2023-03-28 22:08:55,741: DEBUG - opened_ports:
2023-03-28 22:08:55,742: DEBUG -   - 22
2023-03-28 22:08:55,742: DEBUG -   - 25
2023-03-28 22:08:55,742: DEBUG -   - 53
2023-03-28 22:08:55,743: DEBUG -   - 80
2023-03-28 22:08:55,743: DEBUG -   - 443
2023-03-28 22:08:55,744: DEBUG -   - 547
2023-03-28 22:08:55,744: DEBUG -   - 587
2023-03-28 22:08:55,744: DEBUG -   - 784
2023-03-28 22:08:55,744: DEBUG -   - 853
2023-03-28 22:08:55,745: DEBUG -   - 993
2023-03-28 22:08:55,745: DEBUG -   - 1883
2023-03-28 22:08:55,746: DEBUG -   - 1900
2023-03-28 22:08:55,746: DEBUG -   - 5222
2023-03-28 22:08:55,746: DEBUG -   - 5269
2023-03-28 22:08:55,747: DEBUG -   - 5353
2023-03-28 22:08:55,747: DEBUG -   - 7359
2023-03-28 22:08:55,842: DEBUG - + ynh_exec_warn_less yunohost firewall allow --no-upnp UDP 53
2023-03-28 22:08:55,843: DEBUG - + [[ 6 -eq 1 ]]
2023-03-28 22:08:55,844: DEBUG - + yunohost firewall allow --no-upnp UDP 53
2023-03-28 22:08:56,293: DEBUG - Port 53 is already opened for IPv4 connections
2023-03-28 22:08:56,294: DEBUG - Port 53 is already opened for IPv6 connections
2023-03-28 22:08:57,525: DEBUG - Firewall reloaded
2023-03-28 22:08:57,538: DEBUG - opened_ports:
2023-03-28 22:08:57,539: DEBUG -   - 22
2023-03-28 22:08:57,539: DEBUG -   - 25
2023-03-28 22:08:57,540: DEBUG -   - 53
2023-03-28 22:08:57,540: DEBUG -   - 80
2023-03-28 22:08:57,541: DEBUG -   - 443
2023-03-28 22:08:57,541: DEBUG -   - 547
2023-03-28 22:08:57,542: DEBUG -   - 587
2023-03-28 22:08:57,542: DEBUG -   - 784
2023-03-28 22:08:57,542: DEBUG -   - 853
2023-03-28 22:08:57,543: DEBUG -   - 993
2023-03-28 22:08:57,543: DEBUG -   - 1883
2023-03-28 22:08:57,543: DEBUG -   - 1900
2023-03-28 22:08:57,544: DEBUG -   - 5222
2023-03-28 22:08:57,546: DEBUG -   - 5269
2023-03-28 22:08:57,547: DEBUG -   - 5353
2023-03-28 22:08:57,548: DEBUG -   - 7359
2023-03-28 22:08:57,835: DEBUG - + ynh_install_app_dependencies python3-bcrypt python3-yaml
2023-03-28 22:08:57,835: DEBUG - + local 'dependencies=python3-bcrypt python3-yaml'
2023-03-28 22:08:57,835: INFO - [###+................] > Installing dependencies...
2023-03-28 22:08:57,837: DEBUG - ++ echo 'python3-bcrypt python3-yaml'
2023-03-28 22:08:57,838: DEBUG - ++ sed 's/\([^\<=\>]\)\ \([^(]\)/\1, \2/g'
2023-03-28 22:08:57,842: DEBUG - + dependencies='python3-bcrypt, python3-yaml'
2023-03-28 22:08:57,843: DEBUG - + local 'dependencies=python3-bcrypt, python3-yaml'
2023-03-28 22:08:57,844: DEBUG - ++ ynh_read_manifest --manifest_key=version
2023-03-28 22:08:57,889: DEBUG - ++ '[' '!' -e '' ']'
2023-03-28 22:08:57,890: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json ']'
2023-03-28 22:08:57,890: DEBUG - ++ manifest=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:08:57,891: DEBUG - ++ echo /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:08:57,891: DEBUG - ++ grep -q '\.json$'
2023-03-28 22:08:57,894: DEBUG - ++ jq .version /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json --raw-output
2023-03-28 22:08:57,987: DEBUG - + local version=0.107.26~ynh1
2023-03-28 22:08:57,990: DEBUG - + '[' -z 0.107.26~ynh1 ']'
2023-03-28 22:08:57,993: DEBUG - + '[' 0.107.26~ynh1 == null ']'
2023-03-28 22:08:57,994: DEBUG - + local dep_app=adguardhome
2023-03-28 22:08:57,995: DEBUG - + [[ python3-bcrypt, python3-yaml =~ [<=>] ]]
2023-03-28 22:08:57,995: DEBUG - ++ echo python3-bcrypt, python3-yaml
2023-03-28 22:08:57,996: DEBUG - ++ grep -oP '(?<=php)[0-9.]+(?=-|\>)'
2023-03-28 22:08:57,996: DEBUG - ++ sort -u
2023-03-28 22:08:57,998: DEBUG - + local specific_php_version=
2023-03-28 22:08:57,999: DEBUG - + grep --quiet php
2023-03-28 22:08:58,003: DEBUG - ++ ynh_package_is_installed postgresql-13
2023-03-28 22:08:58,028: DEBUG - ++ ynh_wait_dpkg_free
2023-03-28 22:08:58,420: DEBUG - ++ return 0
2023-03-28 22:08:58,421: DEBUG - ++ dpkg-query --show '--showformat=${Status}' postgresql-13
2023-03-28 22:08:58,422: DEBUG - ++ grep --count 'ok installed'
2023-03-28 22:08:58,457: DEBUG - ++ echo yes
2023-03-28 22:08:58,458: DEBUG - + local psql_installed=yes
2023-03-28 22:08:58,458: DEBUG - + [[ true == \t\r\u\e ]]
2023-03-28 22:08:58,459: DEBUG - + YNH_INSTALL_APP_DEPENDENCIES_REPLACE=false
2023-03-28 22:08:58,459: DEBUG - + cat
2023-03-28 22:08:58,462: DEBUG - + ynh_package_install_from_equivs /tmp/adguardhome-ynh-deps.control
2023-03-28 22:08:58,462: DEBUG - + local controlfile=/tmp/adguardhome-ynh-deps.control
2023-03-28 22:08:58,464: DEBUG - ++ grep '^Package: ' /tmp/adguardhome-ynh-deps.control
2023-03-28 22:08:58,465: DEBUG - ++ cut '--delimiter= ' --fields=2
2023-03-28 22:08:58,469: DEBUG - + local pkgname=adguardhome-ynh-deps
2023-03-28 22:08:58,471: DEBUG - ++ grep '^Version: ' /tmp/adguardhome-ynh-deps.control
2023-03-28 22:08:58,472: DEBUG - ++ cut '--delimiter= ' --fields=2
2023-03-28 22:08:58,476: DEBUG - + local pkgversion=0.107.26~ynh1
2023-03-28 22:08:58,477: DEBUG - + [[ -z adguardhome-ynh-deps ]]
2023-03-28 22:08:58,477: DEBUG - + [[ -z 0.107.26~ynh1 ]]
2023-03-28 22:08:58,478: DEBUG - + ynh_package_update
2023-03-28 22:08:58,478: DEBUG - + ynh_apt update
2023-03-28 22:08:58,478: DEBUG - + ynh_wait_dpkg_free
2023-03-28 22:08:58,884: DEBUG - + return 0
2023-03-28 22:08:58,884: DEBUG - + LC_ALL=C
2023-03-28 22:08:58,885: DEBUG - + DEBIAN_FRONTEND=noninteractive
2023-03-28 22:08:58,885: DEBUG - + apt-get --assume-yes --quiet -o=Acquire::Retries=3 -o=Dpkg::Use-Pty=0 update
2023-03-28 22:09:00,049: DEBUG - Get:1 http://security.debian.org/debian-security bullseye-security InRelease [48.4 kB]
2023-03-28 22:09:00,110: DEBUG - Hit:2 http://deb.debian.org/debian bullseye InRelease
2023-03-28 22:09:00,111: DEBUG - Hit:3 http://forge.yunohost.org/debian bullseye InRelease
2023-03-28 22:09:00,266: DEBUG - Get:4 http://deb.debian.org/debian bullseye-updates InRelease [44.1 kB]
2023-03-28 22:09:00,511: DEBUG - Hit:5 https://packages.sury.org/php bullseye InRelease
2023-03-28 22:09:04,878: DEBUG - Hit:6 http://archive.raspberrypi.org/debian bullseye InRelease
2023-03-28 22:09:05,209: DEBUG - Fetched 92.4 kB in 6s (15.0 kB/s)
2023-03-28 22:09:10,425: DEBUG - Reading package lists...
2023-03-28 22:09:10,484: DEBUG - ++ mktemp --directory
2023-03-28 22:09:10,487: DEBUG - + local TMPDIR=/tmp/tmp.rLtBTphMw6
2023-03-28 22:09:10,488: DEBUG - + rm -f /usr/share/equivs/template/debian/compat
2023-03-28 22:09:10,500: DEBUG - + ynh_wait_dpkg_free
2023-03-28 22:09:10,862: DEBUG - + return 0
2023-03-28 22:09:10,862: DEBUG - + cp /tmp/adguardhome-ynh-deps.control /tmp/tmp.rLtBTphMw6/control
2023-03-28 22:09:10,867: DEBUG - + cd /tmp/tmp.rLtBTphMw6
2023-03-28 22:09:10,868: DEBUG - + LC_ALL=C
2023-03-28 22:09:10,868: DEBUG - + equivs-build ./control
2023-03-28 22:09:11,790: DEBUG - dpkg-buildpackage: info: source package adguardhome-ynh-deps
2023-03-28 22:09:11,791: DEBUG - dpkg-buildpackage: info: source version 0.107.26~ynh1
2023-03-28 22:09:11,791: DEBUG - dpkg-buildpackage: info: source distribution unstable
2023-03-28 22:09:11,792: DEBUG - dpkg-buildpackage: info: source changed by Equivs Dummy Package Generator <root@maindomain.tld>
2023-03-28 22:09:11,945: DEBUG -  dpkg-source --before-build .
2023-03-28 22:09:11,946: DEBUG - dpkg-buildpackage: info: host architecture arm64
2023-03-28 22:09:12,328: DEBUG -  debian/rules clean
2023-03-28 22:09:12,347: DEBUG - dh clean
2023-03-28 22:09:12,665: DEBUG -    dh_clean
2023-03-28 22:09:12,761: DEBUG -  debian/rules binary
2023-03-28 22:09:12,765: DEBUG - dh binary
2023-03-28 22:09:12,963: DEBUG -    dh_update_autotools_config
2023-03-28 22:09:13,052: DEBUG -    dh_autoreconf
2023-03-28 22:09:13,199: DEBUG -    create-stamp debian/debhelper-build-stamp
2023-03-28 22:09:13,200: DEBUG -    dh_prep
2023-03-28 22:09:13,295: DEBUG -    dh_install
2023-03-28 22:09:13,393: DEBUG -    dh_installdocs
2023-03-28 22:09:13,529: DEBUG -    dh_installchangelogs
2023-03-28 22:09:13,816: DEBUG -    dh_perl
2023-03-28 22:09:13,939: DEBUG -    dh_link
2023-03-28 22:09:14,040: DEBUG -    dh_strip_nondeterminism
2023-03-28 22:09:14,394: DEBUG -    dh_compress
2023-03-28 22:09:14,541: DEBUG -    dh_fixperms
2023-03-28 22:09:14,679: DEBUG -    dh_missing
2023-03-28 22:09:14,762: DEBUG -    dh_installdeb
2023-03-28 22:09:14,869: DEBUG -    dh_gencontrol
2023-03-28 22:09:15,347: DEBUG -    dh_md5sums
2023-03-28 22:09:15,453: DEBUG -    dh_builddeb
2023-03-28 22:09:15,546: DEBUG - dpkg-deb: building package 'adguardhome-ynh-deps' in '../adguardhome-ynh-deps_0.107.26~ynh1_all.deb'.
2023-03-28 22:09:15,596: DEBUG -  dpkg-genbuildinfo --build=binary
2023-03-28 22:09:18,395: DEBUG -  dpkg-genchanges --build=binary >../adguardhome-ynh-deps_0.107.26~ynh1_arm64.changes
2023-03-28 22:09:18,653: DEBUG - dpkg-genchanges: info: binary-only upload (no source code included)
2023-03-28 22:09:18,662: DEBUG -  dpkg-source --after-build .
2023-03-28 22:09:18,978: DEBUG - dpkg-buildpackage: info: binary-only upload (no source included)
2023-03-28 22:09:18,987: DEBUG - 
2023-03-28 22:09:18,987: DEBUG - The package has been created.
2023-03-28 22:09:18,988: DEBUG - Attention, the package has been created in the current directory,
2023-03-28 22:09:18,988: DEBUG - not in ".." as indicated by the message above!
2023-03-28 22:09:18,993: DEBUG - + LC_ALL=C
2023-03-28 22:09:18,994: DEBUG - + dpkg --force-depends --install ./adguardhome-ynh-deps_0.107.26~ynh1_all.deb
2023-03-28 22:09:18,995: DEBUG - + tee ./dpkg_log
2023-03-28 22:09:19,118: DEBUG - Selecting previously unselected package adguardhome-ynh-deps.
2023-03-28 22:09:19,211: DEBUG - (Reading database ... 64269 files and directories currently installed.)
2023-03-28 22:09:19,218: DEBUG - Preparing to unpack .../adguardhome-ynh-deps_0.107.26~ynh1_all.deb ...
2023-03-28 22:09:19,223: DEBUG - Unpacking adguardhome-ynh-deps (0.107.26~ynh1) ...
2023-03-28 22:09:19,276: DEBUG - dpkg: adguardhome-ynh-deps: dependency problems, but configuring anyway as you requested:
2023-03-28 22:09:19,277: DEBUG -  adguardhome-ynh-deps depends on python3-bcrypt; however:
2023-03-28 22:09:19,280: DEBUG -   Package python3-bcrypt is not installed.
2023-03-28 22:09:19,280: DEBUG - 
2023-03-28 22:09:19,280: DEBUG - Setting up adguardhome-ynh-deps (0.107.26~ynh1) ...
2023-03-28 22:09:19,364: DEBUG - + ynh_package_install --fix-broken
2023-03-28 22:09:19,365: DEBUG - + ynh_apt --no-remove --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold install --fix-broken
2023-03-28 22:09:19,365: DEBUG - + ynh_wait_dpkg_free
2023-03-28 22:09:19,731: DEBUG - + return 0
2023-03-28 22:09:19,732: DEBUG - + LC_ALL=C
2023-03-28 22:09:19,732: DEBUG - + DEBIAN_FRONTEND=noninteractive
2023-03-28 22:09:19,733: DEBUG - + apt-get --assume-yes --quiet -o=Acquire::Retries=3 -o=Dpkg::Use-Pty=0 --no-remove --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold install --fix-broken
2023-03-28 22:09:22,024: DEBUG - Reading package lists...
2023-03-28 22:09:22,759: DEBUG - Building dependency tree...
2023-03-28 22:09:22,761: DEBUG - Reading state information...
2023-03-28 22:09:23,474: DEBUG - Correcting dependencies... Done
2023-03-28 22:09:24,332: DEBUG - The following additional packages will be installed:
2023-03-28 22:09:24,334: DEBUG -   python3-bcrypt
2023-03-28 22:09:24,419: DEBUG - The following NEW packages will be installed:
2023-03-28 22:09:24,421: DEBUG -   python3-bcrypt
2023-03-28 22:09:26,825: DEBUG - 0 upgraded, 1 newly installed, 0 to remove and 0 not upgraded.
2023-03-28 22:09:26,826: DEBUG - Need to get 0 B/30.2 kB of archives.
2023-03-28 22:09:26,827: DEBUG - After this operation, 116 kB of additional disk space will be used.
2023-03-28 22:09:26,889: DEBUG - Selecting previously unselected package python3-bcrypt.
2023-03-28 22:09:26,982: DEBUG - (Reading database ... 64273 files and directories currently installed.)
2023-03-28 22:09:26,989: DEBUG - Preparing to unpack .../python3-bcrypt_3.1.7-4_arm64.deb ...
2023-03-28 22:09:26,994: DEBUG - Unpacking python3-bcrypt (3.1.7-4) ...
2023-03-28 22:09:27,215: DEBUG - Setting up python3-bcrypt (3.1.7-4) ...
2023-03-28 22:09:28,340: DEBUG - + [[ -n /tmp/tmp.rLtBTphMw6 ]]
2023-03-28 22:09:28,341: DEBUG - + rm --recursive --force /tmp/tmp.rLtBTphMw6
2023-03-28 22:09:28,359: DEBUG - + ynh_package_is_installed adguardhome-ynh-deps
2023-03-28 22:09:28,388: DEBUG - + ynh_wait_dpkg_free
2023-03-28 22:09:28,840: DEBUG - + return 0
2023-03-28 22:09:28,842: DEBUG - + dpkg-query --show '--showformat=${Status}' adguardhome-ynh-deps
2023-03-28 22:09:28,843: DEBUG - + grep --count 'ok installed'
2023-03-28 22:09:28,878: DEBUG - + rm /tmp/adguardhome-ynh-deps.control
2023-03-28 22:09:28,900: DEBUG - ++ ynh_package_is_installed postgresql-13
2023-03-28 22:09:28,925: DEBUG - ++ ynh_wait_dpkg_free
2023-03-28 22:09:29,299: DEBUG - ++ return 0
2023-03-28 22:09:29,300: DEBUG - ++ dpkg-query --show '--showformat=${Status}' postgresql-13
2023-03-28 22:09:29,301: DEBUG - ++ grep --count 'ok installed'
2023-03-28 22:09:29,336: DEBUG - ++ echo yes
2023-03-28 22:09:29,337: DEBUG - + local psql_installed2=yes
2023-03-28 22:09:29,338: DEBUG - + [[ yes != \y\e\s ]]
2023-03-28 22:09:29,523: INFO - [####+...............] > Configuring system user...
2023-03-28 22:09:29,526: DEBUG - + ynh_system_user_create --username=adguardhome --home_dir=/var/www/adguardhome --groups=ssl-cert
2023-03-28 22:09:29,728: DEBUG - + use_shell=0
2023-03-28 22:09:29,729: DEBUG - + home_dir=/var/www/adguardhome
2023-03-28 22:09:29,729: DEBUG - + groups=ssl-cert
2023-03-28 22:09:29,730: DEBUG - + ynh_system_user_exists adguardhome
2023-03-28 22:09:29,753: DEBUG - + getent passwd adguardhome
2023-03-28 22:09:29,769: DEBUG - + '[' -n /var/www/adguardhome ']'
2023-03-28 22:09:29,770: DEBUG - + local 'user_home_dir=--home-dir /var/www/adguardhome'
2023-03-28 22:09:29,771: DEBUG - + local 'shell=--shell /usr/sbin/nologin'
2023-03-28 22:09:29,771: DEBUG - + useradd --home-dir /var/www/adguardhome --system --user-group adguardhome --shell /usr/sbin/nologin
2023-03-28 22:09:29,966: DEBUG - + for group in $groups
2023-03-28 22:09:29,967: DEBUG - + usermod -a -G ssl-cert adguardhome
2023-03-28 22:09:30,204: INFO - [#####++++...........] > Setting up source files...
2023-03-28 22:09:30,207: DEBUG - + ynh_app_setting_set --app=adguardhome --key=final_path --value=/var/www/adguardhome
2023-03-28 22:09:30,207: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:30,364: DEBUG - + app=adguardhome
2023-03-28 22:09:30,365: DEBUG - + [[ final_path =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:30,366: DEBUG - + ynh_app_setting set adguardhome final_path /var/www/adguardhome
2023-03-28 22:09:30,536: DEBUG - + ynh_setup_source --dest_dir=/var/www/adguardhome --source_id=arm64
2023-03-28 22:09:30,672: DEBUG - + keep=
2023-03-28 22:09:30,672: DEBUG - + full_replace=0
2023-03-28 22:09:30,673: DEBUG - + test -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.toml
2023-03-28 22:09:30,674: DEBUG - + source_id=arm64
2023-03-28 22:09:30,674: DEBUG - + local src_file_path=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,675: DEBUG - ++ grep SOURCE_URL= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,676: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,688: DEBUG - + local src_url=https://github.com/AdguardTeam/AdGuardHome/releases/download/v0.107.26/AdGuardHome_linux_arm64.tar.gz
2023-03-28 22:09:30,690: DEBUG - ++ grep SOURCE_SUM= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,691: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,696: DEBUG - + local src_sum=709eefbefe18ca8d2bd3578eb9923a8ea7382c59920e6565f386898f0c64b91e
2023-03-28 22:09:30,698: DEBUG - ++ grep SOURCE_SUM_PRG= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,698: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,704: DEBUG - + local src_sumprg=sha256sum
2023-03-28 22:09:30,706: DEBUG - ++ grep SOURCE_FORMAT= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,707: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,711: DEBUG - + local src_format=tar.gz
2023-03-28 22:09:30,713: DEBUG - ++ grep SOURCE_IN_SUBDIR= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,714: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,718: DEBUG - + local src_in_subdir=2
2023-03-28 22:09:30,720: DEBUG - ++ grep SOURCE_FILENAME= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,721: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,726: DEBUG - + local src_rename=
2023-03-28 22:09:30,728: DEBUG - ++ grep SOURCE_EXTRACT= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,729: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,733: DEBUG - + local src_extract=true
2023-03-28 22:09:30,735: DEBUG - ++ grep SOURCE_PLATFORM= /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/arm64.src
2023-03-28 22:09:30,736: DEBUG - ++ cut --delimiter== --fields=2-
2023-03-28 22:09:30,741: DEBUG - + local src_platform=
2023-03-28 22:09:30,742: DEBUG - + src_sumprg=sha256sum
2023-03-28 22:09:30,742: DEBUG - + src_in_subdir=2
2023-03-28 22:09:30,743: DEBUG - + src_format=tar.gz
2023-03-28 22:09:30,744: DEBUG - ++ echo tar.gz
2023-03-28 22:09:30,744: DEBUG - ++ tr '[:upper:]' '[:lower:]'
2023-03-28 22:09:30,752: DEBUG - + src_format=tar.gz
2023-03-28 22:09:30,752: DEBUG - + src_extract=true
2023-03-28 22:09:30,753: DEBUG - + [[ true != \t\r\u\e ]]
2023-03-28 22:09:30,753: DEBUG - + local local_src=/opt/yunohost-apps-src/adguardhome/arm64
2023-03-28 22:09:30,753: DEBUG - ++ dirname /var/cache/yunohost/download/adguardhome/arm64
2023-03-28 22:09:30,760: DEBUG - + mkdir -p /var/cache/yunohost/download/adguardhome
2023-03-28 22:09:30,773: DEBUG - + src_filename=/var/cache/yunohost/download/adguardhome/arm64
2023-03-28 22:09:30,774: DEBUG - + '[' tar.gz = docker ']'
2023-03-28 22:09:30,775: DEBUG - + test -e /opt/yunohost-apps-src/adguardhome/arm64
2023-03-28 22:09:30,775: DEBUG - + '[' -n https://github.com/AdguardTeam/AdGuardHome/releases/download/v0.107.26/AdGuardHome_linux_arm64.tar.gz ']'
2023-03-28 22:09:30,775: DEBUG - + '[' -e /var/cache/yunohost/download/adguardhome/arm64 ']'
2023-03-28 22:09:30,776: DEBUG - + '[' '!' -e /var/cache/yunohost/download/adguardhome/arm64 ']'
2023-03-28 22:09:30,777: DEBUG - ++ wget --tries 3 --no-dns-cache --timeout 900 --no-verbose --output-document=/var/cache/yunohost/download/adguardhome/arm64 https://github.com/AdguardTeam/AdGuardHome/releases/download/v0.107.26/AdGuardHome_linux_arm64.tar.gz
2023-03-28 22:09:39,478: DEBUG - + out='2023-03-28 22:09:39 URL:https://objects.githubusercontent.com/github-production-release-asset-2e65be/62712899/369afc5c-3e72-4edd-a0cd-d38ab5de356c?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAIWNJYAX4CSVEH53A%2F20230329%2Fus-east-1%2Fs3%2Faws4_request&X-Amz-Date=20230329T050931Z&X-Amz-Expires=300&X-Amz-Signature=1dfe6f375d547a814837e33bf88334a29cc75db3b4055399b661a1d68cae53d5&X-Amz-SignedHeaders=host&actor_id=0&key_id=0&repo_id=62712899&response-content-disposition=attachment%3B%20filename%3DAdGuardHome_linux_arm64.tar.gz&response-content-type=application%2Foctet-stream [8824687/8824687] -> "/var/cache/yunohost/download/adguardhome/arm64" [1]'
2023-03-28 22:09:39,481: DEBUG - + sha256sum --check --status
2023-03-28 22:09:39,599: DEBUG - + rm -rf /var/cache/yunohost/files_to_keep_during_setup_source/
2023-03-28 22:09:39,602: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:39,604: DEBUG - + mkdir --parents /var/www/adguardhome
2023-03-28 22:09:39,617: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:39,618: DEBUG - + '[' -n /var/www/adguardhome ']'
2023-03-28 22:09:39,618: DEBUG - + '[' /var/www/adguardhome == /var/www/adguardhome ']'
2023-03-28 22:09:39,619: DEBUG - + _ynh_apply_default_permissions /var/www/adguardhome
2023-03-28 22:09:39,619: DEBUG - + local target=/var/www/adguardhome
2023-03-28 22:09:39,620: DEBUG - ++ ynh_read_manifest --manifest_key=requirements.yunohost
2023-03-28 22:09:39,621: DEBUG - ++ tr -d '<>= '
2023-03-28 22:09:39,664: DEBUG - ++ '[' '!' -e '' ']'
2023-03-28 22:09:39,665: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json ']'
2023-03-28 22:09:39,666: DEBUG - ++ manifest=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:39,666: DEBUG - ++ echo /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:39,667: DEBUG - ++ grep -q '\.json$'
2023-03-28 22:09:39,669: DEBUG - ++ jq .requirements.yunohost /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json --raw-output
2023-03-28 22:09:39,761: DEBUG - + local ynh_requirement=4.3.0
2023-03-28 22:09:39,761: DEBUG - + dpkg --compare-versions 1.0 ge 2
2023-03-28 22:09:39,765: DEBUG - + '[' -z 4.3.0 ']'
2023-03-28 22:09:39,766: DEBUG - + '[' 4.3.0 == null ']'
2023-03-28 22:09:39,766: DEBUG - + dpkg --compare-versions 4.3.0 ge 4.2
2023-03-28 22:09:39,769: DEBUG - + chmod o-rwx /var/www/adguardhome
2023-03-28 22:09:39,776: DEBUG - + chmod g-w /var/www/adguardhome
2023-03-28 22:09:39,779: DEBUG - + chown -R root:root /var/www/adguardhome
2023-03-28 22:09:39,794: DEBUG - + ynh_system_user_exists adguardhome
2023-03-28 22:09:39,817: DEBUG - + getent passwd adguardhome
2023-03-28 22:09:39,825: DEBUG - + chown adguardhome:adguardhome /var/www/adguardhome
2023-03-28 22:09:39,834: DEBUG - + echo /var/www/adguardhome
2023-03-28 22:09:39,835: DEBUG - + grep -q '^/etc/cron'
2023-03-28 22:09:39,840: DEBUG - + [[ true == \f\a\l\s\e ]]
2023-03-28 22:09:39,840: DEBUG - + [[ tar.gz == \d\o\c\k\e\r ]]
2023-03-28 22:09:39,840: DEBUG - + [[ tar.gz == \z\i\p ]]
2023-03-28 22:09:39,841: DEBUG - + local strip=
2023-03-28 22:09:39,841: DEBUG - + '[' 2 '!=' false ']'
2023-03-28 22:09:39,841: DEBUG - + '[' 2 == true ']'
2023-03-28 22:09:39,842: DEBUG - + local sub_dirs=2
2023-03-28 22:09:39,842: DEBUG - + strip='--strip-components 2'
2023-03-28 22:09:39,842: DEBUG - + [[ tar.gz =~ ^tar.gz|tar.bz2|tar.xz$ ]]
2023-03-28 22:09:39,843: DEBUG - + tar --extract --file=/var/cache/yunohost/download/adguardhome/arm64 --directory=/var/www/adguardhome --strip-components 2
2023-03-28 22:09:40,240: DEBUG - + ynh_secure_remove --file=/var/cache/yunohost/download/adguardhome/arm64
2023-03-28 22:09:40,303: DEBUG - + '[' -d /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/sources/patches/ ']'
2023-03-28 22:09:40,303: DEBUG - + test -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/sources/extra_files/arm64
2023-03-28 22:09:40,304: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:40,304: DEBUG - + rm -rf /var/cache/yunohost/files_to_keep_during_setup_source/
2023-03-28 22:09:40,306: DEBUG - + chmod 750 /var/www/adguardhome
2023-03-28 22:09:40,309: DEBUG - + chmod -R o-rwx /var/www/adguardhome
2023-03-28 22:09:40,313: DEBUG - + chown -R adguardhome:adguardhome /var/www/adguardhome
2023-03-28 22:09:40,317: DEBUG - + setcap 'CAP_NET_BIND_SERVICE=+eip CAP_NET_RAW=+eip' /var/www/adguardhome/AdGuardHome
2023-03-28 22:09:40,515: INFO - [#########++.........] > Configuring NGINX web server...
2023-03-28 22:09:40,518: DEBUG - + ynh_add_nginx_config
2023-03-28 22:09:40,519: DEBUG - + local finalnginxconf=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,519: DEBUG - + ynh_add_config --template=nginx.conf --destination=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,595: DEBUG - + '[' -f /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/nginx.conf ']'
2023-03-28 22:09:40,596: DEBUG - + template_path=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/nginx.conf
2023-03-28 22:09:40,596: DEBUG - + ynh_backup_if_checksum_is_different --file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,620: DEBUG - + local checksum_setting_name=checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf
2023-03-28 22:09:40,621: DEBUG - ++ ynh_app_setting_get --app=adguardhome --key=checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf
2023-03-28 22:09:40,622: DEBUG - ++ local _globalapp=adguardhome
2023-03-28 22:09:40,703: DEBUG - ++ app=adguardhome
2023-03-28 22:09:40,704: DEBUG - ++ [[ checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:40,704: DEBUG - ++ ynh_app_setting get adguardhome checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf
2023-03-28 22:09:40,837: DEBUG - + local checksum_value=
2023-03-28 22:09:40,838: DEBUG - + backup_file_checksum=
2023-03-28 22:09:40,838: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:40,838: DEBUG - + touch /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,845: DEBUG - + chown root:root /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,848: DEBUG - + chmod 640 /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,852: DEBUG - + cp -f /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/nginx.conf /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,862: DEBUG - + _ynh_apply_default_permissions /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,863: DEBUG - + local target=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:40,865: DEBUG - ++ ynh_read_manifest --manifest_key=requirements.yunohost
2023-03-28 22:09:40,866: DEBUG - ++ tr -d '<>= '
2023-03-28 22:09:40,912: DEBUG - ++ '[' '!' -e '' ']'
2023-03-28 22:09:40,913: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json ']'
2023-03-28 22:09:40,914: DEBUG - ++ manifest=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:40,914: DEBUG - ++ echo /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:40,914: DEBUG - ++ grep -q '\.json$'
2023-03-28 22:09:40,917: DEBUG - ++ jq .requirements.yunohost /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json --raw-output
2023-03-28 22:09:41,009: DEBUG - + local ynh_requirement=4.3.0
2023-03-28 22:09:41,009: DEBUG - + dpkg --compare-versions 1.0 ge 2
2023-03-28 22:09:41,013: DEBUG - + '[' -z 4.3.0 ']'
2023-03-28 22:09:41,013: DEBUG - + '[' 4.3.0 == null ']'
2023-03-28 22:09:41,014: DEBUG - + dpkg --compare-versions 4.3.0 ge 4.2
2023-03-28 22:09:41,017: DEBUG - + chmod o-rwx /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,019: DEBUG - + chmod g-w /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,022: DEBUG - + chown -R root:root /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,025: DEBUG - + ynh_system_user_exists adguardhome
2023-03-28 22:09:41,051: DEBUG - + getent passwd adguardhome
2023-03-28 22:09:41,054: DEBUG - + chown adguardhome:adguardhome /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,058: DEBUG - + echo /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,059: DEBUG - + grep -q '^/etc/cron'
2023-03-28 22:09:41,063: DEBUG - + ynh_replace_vars --file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,089: DEBUG - + test -n /adguard
2023-03-28 22:09:41,090: DEBUG - + local path_url_slash_less=/adguard
2023-03-28 22:09:41,090: DEBUG - + ynh_replace_string --match_string=__PATH__/ --replace_string=/adguard/ --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,253: DEBUG - + sed --in-place $'s\001__PATH__/\001/adguard/\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,258: DEBUG - + ynh_replace_string --match_string=__PATH__ --replace_string=/adguard --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,422: DEBUG - + sed --in-place $'s\001__PATH__\001/adguard\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,427: DEBUG - + test -n adguardhome
2023-03-28 22:09:41,428: DEBUG - + ynh_replace_string --match_string=__NAME__ --replace_string=adguardhome --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,592: DEBUG - + sed --in-place $'s\001__NAME__\001adguardhome\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,597: DEBUG - + ynh_replace_string --match_string=__NAMETOCHANGE__ --replace_string=adguardhome --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,762: DEBUG - + sed --in-place $'s\001__NAMETOCHANGE__\001adguardhome\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,767: DEBUG - + ynh_replace_string --match_string=__USER__ --replace_string=adguardhome --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,932: DEBUG - + sed --in-place $'s\001__USER__\001adguardhome\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:41,938: DEBUG - + test -n /var/www/adguardhome
2023-03-28 22:09:41,941: DEBUG - + ynh_replace_string --match_string=__FINALPATH__ --replace_string=/var/www/adguardhome --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,105: DEBUG - + sed --in-place $'s\001__FINALPATH__\001/var/www/adguardhome\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,110: DEBUG - + ynh_replace_string --match_string=__INSTALL_DIR__ --replace_string=/var/www/adguardhome --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,279: DEBUG - + sed --in-place $'s\001__INSTALL_DIR__\001/var/www/adguardhome\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,284: DEBUG - + dpkg --compare-versions 1.0 lt 2
2023-03-28 22:09:42,288: DEBUG - + test -n 7.4
2023-03-28 22:09:42,289: DEBUG - + ynh_replace_string --match_string=__PHPVERSION__ --replace_string=7.4 --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,452: DEBUG - + sed --in-place $'s\001__PHPVERSION__\0017.4\001g' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,457: DEBUG - + test -n ''
2023-03-28 22:09:42,460: DEBUG - ++ grep -oP '__[A-Z0-9]+?[A-Z0-9_]*?[A-Z0-9]*?__' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,461: DEBUG - ++ sed 's@__\([^.]*\)__@\L\1@g'
2023-03-28 22:09:42,462: DEBUG - ++ sort --unique
2023-03-28 22:09:42,476: DEBUG - + uniques_vars=('port')
2023-03-28 22:09:42,477: DEBUG - + local delimit=@
2023-03-28 22:09:42,478: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:42,478: DEBUG - + [[ -v port ]]
2023-03-28 22:09:42,479: DEBUG - + match_string=__PORT__
2023-03-28 22:09:42,479: DEBUG - + match_string=__PORT__
2023-03-28 22:09:42,479: DEBUG - + replace_string=3000
2023-03-28 22:09:42,480: DEBUG - + replace_string=3000
2023-03-28 22:09:42,480: DEBUG - + replace_string=3000
2023-03-28 22:09:42,481: DEBUG - + sed --in-place s@__PORT__@3000@g /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,483: DEBUG - + ynh_store_file_checksum --file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,485: DEBUG - + update_only=0
2023-03-28 22:09:42,528: DEBUG - + local checksum_setting_name=checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf
2023-03-28 22:09:42,530: DEBUG - ++ md5sum /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:42,530: DEBUG - ++ cut '--delimiter= ' --fields=1
2023-03-28 22:09:42,537: DEBUG - + ynh_app_setting_set --app=adguardhome --key=checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf --value=195b949526eeb1046b5917fb0a1c823b
2023-03-28 22:09:42,537: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:42,703: DEBUG - + app=adguardhome
2023-03-28 22:09:42,704: DEBUG - + [[ checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:42,705: DEBUG - + ynh_app_setting set adguardhome checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf 195b949526eeb1046b5917fb0a1c823b
2023-03-28 22:09:42,840: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:42,840: DEBUG - + unset backup_file_checksum
2023-03-28 22:09:42,841: DEBUG - + '[' /adguard '!=' / ']'
2023-03-28 22:09:42,841: DEBUG - + ynh_replace_string '--match_string=^#sub_path_only' --replace_string= --target_file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:43,006: DEBUG - + sed --in-place 's^#sub_path_onlyg' /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:43,011: DEBUG - + ynh_store_file_checksum --file=/etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:43,014: DEBUG - + update_only=0
2023-03-28 22:09:43,056: DEBUG - + local checksum_setting_name=checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf
2023-03-28 22:09:43,057: DEBUG - ++ md5sum /etc/nginx/conf.d/domain2.tld.d/adguardhome.conf
2023-03-28 22:09:43,059: DEBUG - ++ cut '--delimiter= ' --fields=1
2023-03-28 22:09:43,065: DEBUG - + ynh_app_setting_set --app=adguardhome --key=checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf --value=ff5fce5ca5725683b39c04df9d948feb
2023-03-28 22:09:43,066: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:43,228: DEBUG - + app=adguardhome
2023-03-28 22:09:43,228: DEBUG - + [[ checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:43,229: DEBUG - + ynh_app_setting set adguardhome checksum__etc_nginx_conf.d_domain2.tld.d_adguardhome.conf ff5fce5ca5725683b39c04df9d948feb
2023-03-28 22:09:43,368: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:43,369: DEBUG - + unset backup_file_checksum
2023-03-28 22:09:43,370: DEBUG - + ynh_systemd_action --service_name=nginx --action=reload
2023-03-28 22:09:43,577: DEBUG - + service_name=nginx
2023-03-28 22:09:43,578: DEBUG - + action=reload
2023-03-28 22:09:43,578: DEBUG - + line_match=
2023-03-28 22:09:43,579: DEBUG - + length=20
2023-03-28 22:09:43,580: DEBUG - + log_path=/var/log/nginx/nginx.log
2023-03-28 22:09:43,580: DEBUG - + timeout=300
2023-03-28 22:09:43,581: DEBUG - + '[' reload == stop ']'
2023-03-28 22:09:43,583: DEBUG - + '[' reload == reload ']'
2023-03-28 22:09:43,583: DEBUG - + action=reload-or-restart
2023-03-28 22:09:43,584: DEBUG - ++ cut -d+ -f1
2023-03-28 22:09:43,584: DEBUG - ++ date --utc --rfc-3339=seconds
2023-03-28 22:09:43,587: DEBUG - + local 'time_start=2023-03-29 05:09:43 UTC'
2023-03-28 22:09:43,587: DEBUG - + systemctl reload-or-restart nginx
2023-03-28 22:09:48,074: INFO - [###########+........] > Adding a configuration file...
2023-03-28 22:09:48,077: DEBUG - ++ head -n1
2023-03-28 22:09:48,078: DEBUG - ++ grep -oP '(?<=dev )\w+'
2023-03-28 22:09:48,079: DEBUG - +++ ip -4 route get 1.2.3.4
2023-03-28 22:09:48,117: DEBUG - ++ echo '1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0
2023-03-28 22:09:48,118: DEBUG -     cache '
2023-03-28 22:09:48,119: DEBUG - + ipv4_interface=eth0
2023-03-28 22:09:48,122: DEBUG - ++ head -n1
2023-03-28 22:09:48,123: DEBUG - ++ grep -oP '(?<=dev )\w+'
2023-03-28 22:09:48,125: DEBUG - +++ ip -6 route get ::1.2.3.4
2023-03-28 22:09:48,132: DEBUG - ++ echo ''
2023-03-28 22:09:48,133: DEBUG - ++ true
2023-03-28 22:09:48,134: DEBUG - + ipv6_interface=
2023-03-28 22:09:48,134: DEBUG - + '[' -z eth0 ']'
2023-03-28 22:09:48,134: DEBUG - + '[' eth0 '!=' '' ']'
2023-03-28 22:09:48,135: DEBUG - + '[' -z eth0 ']'
2023-03-28 22:09:48,135: DEBUG - + '[' -z '' ']'
2023-03-28 22:09:48,135: DEBUG - + echo -e 'bind-interfaces\nexcept-interface=eth0'
2023-03-28 22:09:48,154: DEBUG - + systemctl restart dnsmasq
2023-03-28 22:09:51,192: DEBUG - + ynh_store_file_checksum --file=/etc/dnsmasq.d/adguardhome
2023-03-28 22:09:51,194: DEBUG - + update_only=0
2023-03-28 22:09:51,238: DEBUG - + local checksum_setting_name=checksum__etc_dnsmasq.d_adguardhome
2023-03-28 22:09:51,240: DEBUG - ++ md5sum /etc/dnsmasq.d/adguardhome
2023-03-28 22:09:51,241: DEBUG - ++ cut '--delimiter= ' --fields=1
2023-03-28 22:09:51,245: DEBUG - + ynh_app_setting_set --app=adguardhome --key=checksum__etc_dnsmasq.d_adguardhome --value=a6203241e73e173d867fef85a438ac11
2023-03-28 22:09:51,246: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:51,415: DEBUG - + app=adguardhome
2023-03-28 22:09:51,415: DEBUG - + [[ checksum__etc_dnsmasq.d_adguardhome =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:51,416: DEBUG - + ynh_app_setting set adguardhome checksum__etc_dnsmasq.d_adguardhome a6203241e73e173d867fef85a438ac11
2023-03-28 22:09:51,553: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:51,553: DEBUG - + unset backup_file_checksum
2023-03-28 22:09:51,557: DEBUG - ++ head -n1
2023-03-28 22:09:51,558: DEBUG - +++ ip -4 route get 1.2.3.4
2023-03-28 22:09:51,560: DEBUG - ++ head -n1
2023-03-28 22:09:51,565: DEBUG - ++ echo '1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0
2023-03-28 22:09:51,566: DEBUG -     cache '
2023-03-28 22:09:51,567: DEBUG - + ipv4_route_output='1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0 '
2023-03-28 22:09:51,570: DEBUG - ++ head -n1
2023-03-28 22:09:51,571: DEBUG - +++ ip -6 route get ::1.2.3.4
2023-03-28 22:09:51,577: DEBUG - ++ echo ''
2023-03-28 22:09:51,579: DEBUG - + ipv6_route_output=
2023-03-28 22:09:51,580: DEBUG - + ipv4_addr=
2023-03-28 22:09:51,583: DEBUG - +++ echo 1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0
2023-03-28 22:09:51,584: DEBUG - +++ wc -w
2023-03-28 22:09:51,602: DEBUG - ++ seq 9 -1 1
2023-03-28 22:09:51,606: DEBUG - + for i in $(seq "$(echo $ipv4_route_output | wc -w)" -1 1)
2023-03-28 22:09:51,608: DEBUG - ++ echo 1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0
2023-03-28 22:09:51,609: DEBUG - ++ awk '{print $9}'
2023-03-28 22:09:51,639: DEBUG - + ip=0
2023-03-28 22:09:51,639: DEBUG - + ynh_validate_ip4 --ip_address=0
2023-03-28 22:09:51,665: DEBUG - + ynh_validate_ip --family=4 --ip_address=0
2023-03-28 22:09:51,745: DEBUG - + '[' 4 == 4 ']'
2023-03-28 22:09:51,746: DEBUG - + python3 /dev/stdin
2023-03-28 22:09:51,838: DEBUG - + for i in $(seq "$(echo $ipv4_route_output | wc -w)" -1 1)
2023-03-28 22:09:51,841: DEBUG - ++ echo 1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0
2023-03-28 22:09:51,841: DEBUG - ++ awk '{print $8}'
2023-03-28 22:09:51,850: DEBUG - + ip=uid
2023-03-28 22:09:51,850: DEBUG - + ynh_validate_ip4 --ip_address=uid
2023-03-28 22:09:51,875: DEBUG - + ynh_validate_ip --family=4 --ip_address=uid
2023-03-28 22:09:51,958: DEBUG - + '[' 4 == 4 ']'
2023-03-28 22:09:51,959: DEBUG - + python3 /dev/stdin
2023-03-28 22:09:52,050: DEBUG - + for i in $(seq "$(echo $ipv4_route_output | wc -w)" -1 1)
2023-03-28 22:09:52,053: DEBUG - ++ echo 1.2.3.4 via 192.168.50.1 dev eth0 src 192.168.50.136 uid 0
2023-03-28 22:09:52,054: DEBUG - ++ awk '{print $7}'
2023-03-28 22:09:52,061: DEBUG - + ip=192.168.50.136
2023-03-28 22:09:52,062: DEBUG - + ynh_validate_ip4 --ip_address=192.168.50.136
2023-03-28 22:09:52,089: DEBUG - + ynh_validate_ip --family=4 --ip_address=192.168.50.136
2023-03-28 22:09:52,171: DEBUG - + '[' 4 == 4 ']'
2023-03-28 22:09:52,171: DEBUG - + python3 /dev/stdin
2023-03-28 22:09:52,264: DEBUG - + ipv4_addr='- 192.168.50.136'
2023-03-28 22:09:52,265: DEBUG - + break
2023-03-28 22:09:52,265: DEBUG - + ipv6_addr=
2023-03-28 22:09:52,268: DEBUG - +++ echo
2023-03-28 22:09:52,269: DEBUG - +++ wc -w
2023-03-28 22:09:52,275: DEBUG - ++ seq 0 -1 1
2023-03-28 22:09:52,280: DEBUG - ++ python3 -c 'import bcrypt; print(bcrypt.hashpw(b"**********", bcrypt.gensalt(rounds=10)).decode())'
2023-03-28 22:09:52,485: DEBUG - + password=**********
2023-03-28 22:09:52,486: DEBUG - + ynh_app_setting_set --app=adguardhome --key=password '--value=$2b$10$dfNRvFKiC3H/UmogrEUoy.YI/3a1yimwnUhxI9F8g4fJLPWTWKRz.'
2023-03-28 22:09:52,486: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:52,653: DEBUG - + app=adguardhome
2023-03-28 22:09:52,653: DEBUG - + [[ password =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:52,654: DEBUG - + ynh_app_setting set adguardhome password **********
2023-03-28 22:09:52,791: DEBUG - + ynh_add_config --template=../conf/AdGuardHome.yaml --destination=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:52,874: DEBUG - + '[' -f /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/../conf/AdGuardHome.yaml ']'
2023-03-28 22:09:52,875: DEBUG - + template_path=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/../conf/AdGuardHome.yaml
2023-03-28 22:09:52,875: DEBUG - + ynh_backup_if_checksum_is_different --file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:52,901: DEBUG - + local checksum_setting_name=checksum__var_www_adguardhome_AdGuardHome.yaml
2023-03-28 22:09:52,902: DEBUG - ++ ynh_app_setting_get --app=adguardhome --key=checksum__var_www_adguardhome_AdGuardHome.yaml
2023-03-28 22:09:52,903: DEBUG - ++ local _globalapp=adguardhome
2023-03-28 22:09:52,986: DEBUG - ++ app=adguardhome
2023-03-28 22:09:52,987: DEBUG - ++ [[ checksum__var_www_adguardhome_AdGuardHome.yaml =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:52,988: DEBUG - ++ ynh_app_setting get adguardhome checksum__var_www_adguardhome_AdGuardHome.yaml
2023-03-28 22:09:53,124: DEBUG - + local checksum_value=
2023-03-28 22:09:53,124: DEBUG - + backup_file_checksum=
2023-03-28 22:09:53,125: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:53,125: DEBUG - + touch /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,127: DEBUG - + chown root:root /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,129: DEBUG - + chmod 640 /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,133: DEBUG - + cp -f /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/../conf/AdGuardHome.yaml /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,137: DEBUG - + _ynh_apply_default_permissions /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,138: DEBUG - + local target=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,140: DEBUG - ++ ynh_read_manifest --manifest_key=requirements.yunohost
2023-03-28 22:09:53,141: DEBUG - ++ tr -d '<>= '
2023-03-28 22:09:53,187: DEBUG - ++ '[' '!' -e '' ']'
2023-03-28 22:09:53,188: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json ']'
2023-03-28 22:09:53,189: DEBUG - ++ manifest=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:53,190: DEBUG - ++ echo /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:53,191: DEBUG - ++ grep -q '\.json$'
2023-03-28 22:09:53,194: DEBUG - ++ jq .requirements.yunohost /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json --raw-output
2023-03-28 22:09:53,294: DEBUG - + local ynh_requirement=4.3.0
2023-03-28 22:09:53,294: DEBUG - + dpkg --compare-versions 1.0 ge 2
2023-03-28 22:09:53,297: DEBUG - + '[' -z 4.3.0 ']'
2023-03-28 22:09:53,298: DEBUG - + '[' 4.3.0 == null ']'
2023-03-28 22:09:53,298: DEBUG - + dpkg --compare-versions 4.3.0 ge 4.2
2023-03-28 22:09:53,301: DEBUG - + chmod o-rwx /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,305: DEBUG - + chmod g-w /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,308: DEBUG - + chown -R root:root /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,311: DEBUG - + ynh_system_user_exists adguardhome
2023-03-28 22:09:53,338: DEBUG - + getent passwd adguardhome
2023-03-28 22:09:53,342: DEBUG - + chown adguardhome:adguardhome /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,346: DEBUG - + echo /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,347: DEBUG - + grep -q '^/etc/cron'
2023-03-28 22:09:53,352: DEBUG - + ynh_replace_vars --file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,377: DEBUG - + test -n /adguard
2023-03-28 22:09:53,378: DEBUG - + local path_url_slash_less=/adguard
2023-03-28 22:09:53,378: DEBUG - + ynh_replace_string --match_string=__PATH__/ --replace_string=/adguard/ --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,541: DEBUG - + sed --in-place $'s\001__PATH__/\001/adguard/\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,545: DEBUG - + ynh_replace_string --match_string=__PATH__ --replace_string=/adguard --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,714: DEBUG - + sed --in-place $'s\001__PATH__\001/adguard\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,718: DEBUG - + test -n adguardhome
2023-03-28 22:09:53,719: DEBUG - + ynh_replace_string --match_string=__NAME__ --replace_string=adguardhome --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,888: DEBUG - + sed --in-place $'s\001__NAME__\001adguardhome\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:53,892: DEBUG - + ynh_replace_string --match_string=__NAMETOCHANGE__ --replace_string=adguardhome --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,057: DEBUG - + sed --in-place $'s\001__NAMETOCHANGE__\001adguardhome\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,062: DEBUG - + ynh_replace_string --match_string=__USER__ --replace_string=adguardhome --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,234: DEBUG - + sed --in-place $'s\001__USER__\001adguardhome\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,239: DEBUG - + test -n /var/www/adguardhome
2023-03-28 22:09:54,239: DEBUG - + ynh_replace_string --match_string=__FINALPATH__ --replace_string=/var/www/adguardhome --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,399: DEBUG - + sed --in-place $'s\001__FINALPATH__\001/var/www/adguardhome\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,404: DEBUG - + ynh_replace_string --match_string=__INSTALL_DIR__ --replace_string=/var/www/adguardhome --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,577: DEBUG - + sed --in-place $'s\001__INSTALL_DIR__\001/var/www/adguardhome\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,581: DEBUG - + dpkg --compare-versions 1.0 lt 2
2023-03-28 22:09:54,586: DEBUG - + test -n 7.4
2023-03-28 22:09:54,586: DEBUG - + ynh_replace_string --match_string=__PHPVERSION__ --replace_string=7.4 --target_file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,759: DEBUG - + sed --in-place $'s\001__PHPVERSION__\0017.4\001g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,763: DEBUG - + test -n ''
2023-03-28 22:09:54,766: DEBUG - ++ grep -oP '__[A-Z0-9]+?[A-Z0-9_]*?[A-Z0-9]*?__' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,767: DEBUG - ++ sort --unique
2023-03-28 22:09:54,768: DEBUG - ++ sed 's@__\([^.]*\)__@\L\1@g'
2023-03-28 22:09:54,774: DEBUG - + uniques_vars=('adguard_port' 'admin' 'dns_over_https' 'ipv4_addr' 'ipv6_addr' 'password' 'port')
2023-03-28 22:09:54,775: DEBUG - + local delimit=@
2023-03-28 22:09:54,776: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,776: DEBUG - + [[ -v adguard_port ]]
2023-03-28 22:09:54,776: DEBUG - + match_string=__ADGUARD_PORT__
2023-03-28 22:09:54,777: DEBUG - + match_string=__ADGUARD_PORT__
2023-03-28 22:09:54,777: DEBUG - + replace_string=53
2023-03-28 22:09:54,777: DEBUG - + replace_string=53
2023-03-28 22:09:54,778: DEBUG - + replace_string=53
2023-03-28 22:09:54,778: DEBUG - + sed --in-place s@__ADGUARD_PORT__@53@g /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,780: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,781: DEBUG - + [[ -v admin ]]
2023-03-28 22:09:54,781: DEBUG - + match_string=__ADMIN__
2023-03-28 22:09:54,782: DEBUG - + match_string=__ADMIN__
2023-03-28 22:09:54,782: DEBUG - + replace_string=kirkrehn
2023-03-28 22:09:54,782: DEBUG - + replace_string=kirkrehn
2023-03-28 22:09:54,783: DEBUG - + replace_string=kirkrehn
2023-03-28 22:09:54,783: DEBUG - + sed --in-place s@__ADMIN__@kirkrehn@g /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,786: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,787: DEBUG - + [[ -v dns_over_https ]]
2023-03-28 22:09:54,787: DEBUG - + match_string=__DNS_OVER_HTTPS__
2023-03-28 22:09:54,788: DEBUG - + match_string=__DNS_OVER_HTTPS__
2023-03-28 22:09:54,788: DEBUG - + replace_string=true
2023-03-28 22:09:54,788: DEBUG - + replace_string=true
2023-03-28 22:09:54,789: DEBUG - + replace_string=true
2023-03-28 22:09:54,789: DEBUG - + sed --in-place s@__DNS_OVER_HTTPS__@true@g /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,792: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,793: DEBUG - + [[ -v ipv4_addr ]]
2023-03-28 22:09:54,793: DEBUG - + match_string=__IPV4_ADDR__
2023-03-28 22:09:54,794: DEBUG - + match_string=__IPV4_ADDR__
2023-03-28 22:09:54,794: DEBUG - + replace_string='- 192.168.50.136'
2023-03-28 22:09:54,794: DEBUG - + replace_string='- 192.168.50.136'
2023-03-28 22:09:54,795: DEBUG - + replace_string='- 192.168.50.136'
2023-03-28 22:09:54,795: DEBUG - + sed --in-place 's@__IPV4_ADDR__@- 192.168.50.136@g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,798: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,798: DEBUG - + [[ -v ipv6_addr ]]
2023-03-28 22:09:54,799: DEBUG - + match_string=__IPV6_ADDR__
2023-03-28 22:09:54,799: DEBUG - + match_string=__IPV6_ADDR__
2023-03-28 22:09:54,800: DEBUG - + replace_string=
2023-03-28 22:09:54,800: DEBUG - + replace_string=
2023-03-28 22:09:54,800: DEBUG - + replace_string=
2023-03-28 22:09:54,801: DEBUG - + sed --in-place s@__IPV6_ADDR__@@g /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,804: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,804: DEBUG - + [[ -v password ]]
2023-03-28 22:09:54,805: DEBUG - + match_string=__PASSWORD__
2023-03-28 22:09:54,805: DEBUG - + match_string=__PASSWORD__
2023-03-28 22:09:54,806: DEBUG - + replace_string=**********
2023-03-28 22:09:54,806: DEBUG - + replace_string=**********
2023-03-28 22:09:54,806: DEBUG - + replace_string=**********
2023-03-28 22:09:54,807: DEBUG - + sed --in-place 's@__PASSWORD__@$2b$10$dfNRvFKiC3H/UmogrEUoy.YI/3a1yimwnUhxI9F8g4fJLPWTWKRz.@g' /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,810: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:54,811: DEBUG - + [[ -v port ]]
2023-03-28 22:09:54,811: DEBUG - + match_string=__PORT__
2023-03-28 22:09:54,812: DEBUG - + match_string=__PORT__
2023-03-28 22:09:54,812: DEBUG - + replace_string=3000
2023-03-28 22:09:54,812: DEBUG - + replace_string=3000
2023-03-28 22:09:54,813: DEBUG - + replace_string=3000
2023-03-28 22:09:54,813: DEBUG - + sed --in-place s@__PORT__@3000@g /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,816: DEBUG - + ynh_store_file_checksum --file=/var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,819: DEBUG - + update_only=0
2023-03-28 22:09:54,865: DEBUG - + local checksum_setting_name=checksum__var_www_adguardhome_AdGuardHome.yaml
2023-03-28 22:09:54,867: DEBUG - ++ md5sum /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:54,868: DEBUG - ++ cut '--delimiter= ' --fields=1
2023-03-28 22:09:54,873: DEBUG - + ynh_app_setting_set --app=adguardhome --key=checksum__var_www_adguardhome_AdGuardHome.yaml --value=3e20935739ee123ec0b47f3339035f4d
2023-03-28 22:09:54,874: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:55,044: DEBUG - + app=adguardhome
2023-03-28 22:09:55,044: DEBUG - + [[ checksum__var_www_adguardhome_AdGuardHome.yaml =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:55,045: DEBUG - + ynh_app_setting set adguardhome checksum__var_www_adguardhome_AdGuardHome.yaml 3e20935739ee123ec0b47f3339035f4d
2023-03-28 22:09:55,184: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:55,184: DEBUG - + unset backup_file_checksum
2023-03-28 22:09:55,185: DEBUG - + chmod 600 /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:55,187: DEBUG - + chown -R adguardhome:adguardhome /var/www/adguardhome/AdGuardHome.yaml
2023-03-28 22:09:55,455: INFO - [############+.......] > Configuring a systemd service...
2023-03-28 22:09:55,458: DEBUG - + ynh_add_systemd_config
2023-03-28 22:09:55,462: DEBUG - + service=adguardhome
2023-03-28 22:09:55,463: DEBUG - + template=systemd.service
2023-03-28 22:09:55,463: DEBUG - + ynh_add_config --template=systemd.service --destination=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,572: DEBUG - + '[' -f /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/systemd.service ']'
2023-03-28 22:09:55,573: DEBUG - + template_path=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/systemd.service
2023-03-28 22:09:55,574: DEBUG - + ynh_backup_if_checksum_is_different --file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,609: DEBUG - + local checksum_setting_name=checksum__etc_systemd_system_adguardhome.service
2023-03-28 22:09:55,611: DEBUG - ++ ynh_app_setting_get --app=adguardhome --key=checksum__etc_systemd_system_adguardhome.service
2023-03-28 22:09:55,612: DEBUG - ++ local _globalapp=adguardhome
2023-03-28 22:09:55,734: DEBUG - ++ app=adguardhome
2023-03-28 22:09:55,734: DEBUG - ++ [[ checksum__etc_systemd_system_adguardhome.service =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:55,735: DEBUG - ++ ynh_app_setting get adguardhome checksum__etc_systemd_system_adguardhome.service
2023-03-28 22:09:55,871: DEBUG - + local checksum_value=
2023-03-28 22:09:55,871: DEBUG - + backup_file_checksum=
2023-03-28 22:09:55,872: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:55,872: DEBUG - + touch /etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,885: DEBUG - + chown root:root /etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,889: DEBUG - + chmod 640 /etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,891: DEBUG - + cp -f /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/conf/systemd.service /etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,895: DEBUG - + _ynh_apply_default_permissions /etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,896: DEBUG - + local target=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:55,898: DEBUG - ++ ynh_read_manifest --manifest_key=requirements.yunohost
2023-03-28 22:09:55,899: DEBUG - ++ tr -d '<>= '
2023-03-28 22:09:55,948: DEBUG - ++ '[' '!' -e '' ']'
2023-03-28 22:09:55,949: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json ']'
2023-03-28 22:09:55,950: DEBUG - ++ manifest=/var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:55,950: DEBUG - ++ echo /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json
2023-03-28 22:09:55,950: DEBUG - ++ grep -q '\.json$'
2023-03-28 22:09:55,954: DEBUG - ++ jq .requirements.yunohost /var/cache/yunohost/app_tmp_work_dirs/app_wpw3ph9y/manifest.json --raw-output
2023-03-28 22:09:56,037: DEBUG - + local ynh_requirement=4.3.0
2023-03-28 22:09:56,038: DEBUG - + dpkg --compare-versions 1.0 ge 2
2023-03-28 22:09:56,041: DEBUG - + '[' -z 4.3.0 ']'
2023-03-28 22:09:56,042: DEBUG - + '[' 4.3.0 == null ']'
2023-03-28 22:09:56,042: DEBUG - + dpkg --compare-versions 4.3.0 ge 4.2
2023-03-28 22:09:56,046: DEBUG - + chmod o-rwx /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,049: DEBUG - + chmod g-w /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,052: DEBUG - + chown -R root:root /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,055: DEBUG - + ynh_system_user_exists adguardhome
2023-03-28 22:09:56,081: DEBUG - + getent passwd adguardhome
2023-03-28 22:09:56,085: DEBUG - + chown adguardhome:adguardhome /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,089: DEBUG - + echo /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,090: DEBUG - + grep -q '^/etc/cron'
2023-03-28 22:09:56,095: DEBUG - + ynh_replace_vars --file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,121: DEBUG - + test -n /adguard
2023-03-28 22:09:56,121: DEBUG - + local path_url_slash_less=/adguard
2023-03-28 22:09:56,122: DEBUG - + ynh_replace_string --match_string=__PATH__/ --replace_string=/adguard/ --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,284: DEBUG - + sed --in-place $'s\001__PATH__/\001/adguard/\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,291: DEBUG - + ynh_replace_string --match_string=__PATH__ --replace_string=/adguard --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,462: DEBUG - + sed --in-place $'s\001__PATH__\001/adguard\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,466: DEBUG - + test -n adguardhome
2023-03-28 22:09:56,467: DEBUG - + ynh_replace_string --match_string=__NAME__ --replace_string=adguardhome --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,631: DEBUG - + sed --in-place $'s\001__NAME__\001adguardhome\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,635: DEBUG - + ynh_replace_string --match_string=__NAMETOCHANGE__ --replace_string=adguardhome --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,808: DEBUG - + sed --in-place $'s\001__NAMETOCHANGE__\001adguardhome\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,812: DEBUG - + ynh_replace_string --match_string=__USER__ --replace_string=adguardhome --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,983: DEBUG - + sed --in-place $'s\001__USER__\001adguardhome\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:56,987: DEBUG - + test -n /var/www/adguardhome
2023-03-28 22:09:56,988: DEBUG - + ynh_replace_string --match_string=__FINALPATH__ --replace_string=/var/www/adguardhome --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,151: DEBUG - + sed --in-place $'s\001__FINALPATH__\001/var/www/adguardhome\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,156: DEBUG - + ynh_replace_string --match_string=__INSTALL_DIR__ --replace_string=/var/www/adguardhome --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,328: DEBUG - + sed --in-place $'s\001__INSTALL_DIR__\001/var/www/adguardhome\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,332: DEBUG - + dpkg --compare-versions 1.0 lt 2
2023-03-28 22:09:57,336: DEBUG - + test -n 7.4
2023-03-28 22:09:57,337: DEBUG - + ynh_replace_string --match_string=__PHPVERSION__ --replace_string=7.4 --target_file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,500: DEBUG - + sed --in-place $'s\001__PHPVERSION__\0017.4\001g' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,505: DEBUG - + test -n ''
2023-03-28 22:09:57,507: DEBUG - ++ grep -oP '__[A-Z0-9]+?[A-Z0-9_]*?[A-Z0-9]*?__' /etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,509: DEBUG - ++ sed 's@__\([^.]*\)__@\L\1@g'
2023-03-28 22:09:57,510: DEBUG - ++ sort --unique
2023-03-28 22:09:57,516: DEBUG - + uniques_vars=('app')
2023-03-28 22:09:57,517: DEBUG - + local delimit=@
2023-03-28 22:09:57,518: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-03-28 22:09:57,518: DEBUG - + [[ -v app ]]
2023-03-28 22:09:57,518: DEBUG - + match_string=__APP__
2023-03-28 22:09:57,518: DEBUG - + match_string=__APP__
2023-03-28 22:09:57,519: DEBUG - + replace_string=adguardhome
2023-03-28 22:09:57,519: DEBUG - + replace_string=adguardhome
2023-03-28 22:09:57,519: DEBUG - + replace_string=adguardhome
2023-03-28 22:09:57,520: DEBUG - + sed --in-place s@__APP__@adguardhome@g /etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,521: DEBUG - + ynh_store_file_checksum --file=/etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,524: DEBUG - + update_only=0
2023-03-28 22:09:57,568: DEBUG - + local checksum_setting_name=checksum__etc_systemd_system_adguardhome.service
2023-03-28 22:09:57,570: DEBUG - ++ md5sum /etc/systemd/system/adguardhome.service
2023-03-28 22:09:57,571: DEBUG - ++ cut '--delimiter= ' --fields=1
2023-03-28 22:09:57,575: DEBUG - + ynh_app_setting_set --app=adguardhome --key=checksum__etc_systemd_system_adguardhome.service --value=ae9a2901199e4774608266f886b6c18d
2023-03-28 22:09:57,576: DEBUG - + local _globalapp=adguardhome
2023-03-28 22:09:57,751: DEBUG - + app=adguardhome
2023-03-28 22:09:57,751: DEBUG - + [[ checksum__etc_systemd_system_adguardhome.service =~ (unprotected|protected|skipped)_ ]]
2023-03-28 22:09:57,752: DEBUG - + ynh_app_setting set adguardhome checksum__etc_systemd_system_adguardhome.service ae9a2901199e4774608266f886b6c18d
2023-03-28 22:09:57,892: DEBUG - + '[' -n '' ']'
2023-03-28 22:09:57,893: DEBUG - + unset backup_file_checksum
2023-03-28 22:09:57,893: DEBUG - + systemctl enable adguardhome --quiet
2023-03-28 22:09:59,250: DEBUG - + systemctl daemon-reload
2023-03-28 22:09:59,936: INFO - [#############+......] > Integrating service in YunoHost...
2023-03-28 22:09:59,938: DEBUG - + yunohost service add adguardhome '--description=Ads & trackers blocking DNS server' --needs_exposed_ports 53
2023-03-28 22:10:01,386: DEBUG - The service 'adguardhome' was added
2023-03-28 22:10:01,761: INFO - [##############++....] > Starting a systemd service...
2023-03-28 22:10:01,764: DEBUG - + ynh_systemd_action --service_name=adguardhome --action=restart --log_path=systemd
2023-03-28 22:10:02,165: DEBUG - + service_name=adguardhome
2023-03-28 22:10:02,165: DEBUG - + action=restart
2023-03-28 22:10:02,166: DEBUG - + line_match=
2023-03-28 22:10:02,166: DEBUG - + length=20
2023-03-28 22:10:02,167: DEBUG - + log_path=systemd
2023-03-28 22:10:02,167: DEBUG - + timeout=300
2023-03-28 22:10:02,168: DEBUG - + '[' restart == stop ']'
2023-03-28 22:10:02,169: DEBUG - + '[' restart == reload ']'
2023-03-28 22:10:02,170: DEBUG - ++ date --utc --rfc-3339=seconds
2023-03-28 22:10:02,170: DEBUG - ++ cut -d+ -f1
2023-03-28 22:10:02,173: DEBUG - + local 'time_start=2023-03-29 05:10:02 UTC'
2023-03-28 22:10:02,174: DEBUG - + systemctl restart adguardhome
2023-03-28 22:10:02,366: INFO - [################+...] > Configuring permissions...
2023-03-28 22:10:02,367: DEBUG - + ynh_permission_create --permission=api --label=api --url=re:domain2.tld/dns-query --allowed=visitors --auth_header=false --show_tile=false --protected=true
2023-03-28 22:10:03,497: DEBUG - + url=re:domain2.tld/dns-query
2023-03-28 22:10:03,498: DEBUG - + additional_urls=
2023-03-28 22:10:03,499: DEBUG - + auth_header=false
2023-03-28 22:10:03,499: DEBUG - + allowed=visitors
2023-03-28 22:10:03,499: DEBUG - + label=api
2023-03-28 22:10:03,500: DEBUG - + show_tile=false
2023-03-28 22:10:03,500: DEBUG - + protected=true
2023-03-28 22:10:03,500: DEBUG - + [[ -n re:domain2.tld/dns-query ]]
2023-03-28 22:10:03,501: DEBUG - + url=',url='\''re:domain2.tld/dns-query'\'''
2023-03-28 22:10:03,502: DEBUG - + [[ -n false ]]
2023-03-28 22:10:03,502: DEBUG - + '[' false == true ']'
2023-03-28 22:10:03,503: DEBUG - + auth_header=,auth_header=False
2023-03-28 22:10:03,503: DEBUG - + [[ -n visitors ]]
2023-03-28 22:10:03,503: DEBUG - + allowed=',allowed=['\''visitors'\'']'
2023-03-28 22:10:03,503: DEBUG - + [[ -n api ]]
2023-03-28 22:10:03,504: DEBUG - + label=',label='\''api'\'''
2023-03-28 22:10:03,504: DEBUG - + [[ -n false ]]
2023-03-28 22:10:03,504: DEBUG - + '[' false == true ']'
2023-03-28 22:10:03,505: DEBUG - + show_tile=,show_tile=False
2023-03-28 22:10:03,506: DEBUG - + [[ -n true ]]
2023-03-28 22:10:03,506: DEBUG - + '[' true == true ']'
2023-03-28 22:10:03,507: DEBUG - + protected=,protected=True
2023-03-28 22:10:03,507: DEBUG - + yunohost tools shell -c 'from yunohost.permission import permission_create; permission_create('\''adguardhome.api'\'' ,url='\''re:domain2.tld/dns-query'\''  ,auth_header=False ,allowed=['\''visitors'\''] ,label='\''api'\'' ,show_tile=False ,protected=True)'
2023-03-28 22:10:07,758: DEBUG - + ynh_systemd_action --service_name=nginx --action=reload
2023-03-28 22:10:07,761: INFO - [#################++.] > Reloading NGINX web server...
2023-03-28 22:10:07,979: DEBUG - + service_name=nginx
2023-03-28 22:10:07,980: DEBUG - + action=reload
2023-03-28 22:10:07,980: DEBUG - + line_match=
2023-03-28 22:10:07,981: DEBUG - + length=20
2023-03-28 22:10:07,982: DEBUG - + log_path=/var/log/nginx/nginx.log
2023-03-28 22:10:07,982: DEBUG - + timeout=300
2023-03-28 22:10:07,983: DEBUG - + '[' reload == stop ']'
2023-03-28 22:10:07,985: DEBUG - + '[' reload == reload ']'
2023-03-28 22:10:07,986: DEBUG - + action=reload-or-restart
2023-03-28 22:10:07,986: DEBUG - ++ date --utc --rfc-3339=seconds
2023-03-28 22:10:07,987: DEBUG - ++ cut -d+ -f1
2023-03-28 22:10:07,987: DEBUG - + local 'time_start=2023-03-29 05:10:07 UTC'
2023-03-28 22:10:07,988: DEBUG - + systemctl reload-or-restart nginx
2023-03-28 22:10:12,953: INFO - [####################] > Installation of adguardhome completed
2023-03-28 22:10:12,956: DEBUG - + ynh_exit_properly
2023-03-28 22:10:13,960: DEBUG - Checking that required services are up and running...
2023-03-28 22:10:17,152: SUCCESS - Installation completed
```
