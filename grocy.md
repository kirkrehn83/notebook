---
share: true
---
```ad-abstract
tagline of app

```

```toc

```

## faq

| **item** | **description** |
| --- | --- |
| url | kirkrehn.online |
| admin user | kirkrehn |
| admin pass| kirkser |
| admin e-mail | kirk@kirkrehn.online |

### api keys

| **key** | **secret** |
| --- | --- |
| | |

## config

```bash

```

## logs
### install logs
```bash
ended_at: 2023-04-04 21:28:43.177642
env:
  BASH_XTRACEFD: '7'
  YNH_APP_ACTION: restore
  YNH_APP_BACKUP_DIR: /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup
  YNH_APP_BASEDIR: /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings
  YNH_APP_ID: grocy
  YNH_APP_INSTANCE_NAME: grocy
  YNH_APP_INSTANCE_NUMBER: '1'
  YNH_APP_MANIFEST_VERSION: 3.3.2~ynh3
  YNH_APP_PACKAGING_FORMAT: '2.0'
  YNH_ARCH: arm64
  YNH_BACKUP_CSV: /home/yunohost.backup/tmp/20230401-051906/backup.csv
  YNH_BACKUP_DIR: /home/yunohost.backup/tmp/20230401-051906
  YNH_CWD: /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup
  YNH_DEBIAN_VERSION: bullseye
  YNH_INTERFACE: cli
  YNH_STDRETURN: /tmp/tmp9iiqjpj1/stdreturn
error: null
interface: cli
operation: backup_restore_app
parent: null
related_to:
- - app
  - grocy
started_at: 2023-04-04 21:27:36.082230
success: true
yunohost_version: 11.1.16

============

2023-04-04 22:27:36,104: INFO - Restoring grocy...
2023-04-04 22:27:36,350: DEBUG - initializing ldap interface
2023-04-04 22:27:37,135: DEBUG - Permission 'grocy.main' updated
2023-04-04 22:27:37,431: DEBUG - To view the log of the operation 'Update URL related to permission 'grocy'', use the command 'yunohost log show 20230404-212737-permission_url-grocy'
2023-04-04 22:27:38,145: DEBUG - Permission 'grocy.main' created
2023-04-04 22:27:38,146: DEBUG - To view the log of the operation 'Create permission 'grocy'', use the command 'yunohost log show 20230404-212736-permission_create-grocy'
2023-04-04 22:27:38,573: DEBUG - The permission database has been resynchronized
2023-04-04 22:27:39,066: DEBUG - SSOwat configuration regenerated
2023-04-04 22:27:39,092: DEBUG - Loading migration 0022_php73_to_php74_pools...
2023-04-04 22:27:39,102: DEBUG - Loading migration 0026_new_admins_group...
2023-04-04 22:27:39,105: DEBUG - Loading migration 0021_migrate_to_bullseye...
2023-04-04 22:27:39,107: DEBUG - Loading migration 0025_global_settings_to_configpanel...
2023-04-04 22:27:39,109: DEBUG - Loading migration 0023_postgresql_11_to_13...
2023-04-04 22:27:39,110: DEBUG - Loading migration 0024_rebuild_python_venv...
2023-04-04 22:27:39,164: DEBUG - Restoring the app 'grocy'...
2023-04-04 22:27:39,229: INFO - Provisionning sources...
2023-04-04 22:27:39,229: INFO - Provisionning system_user...
2023-04-04 22:27:40,742: INFO - Provisionning install_dir...
2023-04-04 22:27:40,802: INFO - Provisionning permissions...
2023-04-04 22:27:41,622: DEBUG - Nothing to update in LDAP
2023-04-04 22:27:41,921: DEBUG - Permission 'grocy.main' updated
2023-04-04 22:27:41,921: DEBUG - To view the log of the operation 'Update accesses for permission 'grocy'', use the command 'yunohost log show 20230404-212741-user_permission_update-grocy'
2023-04-04 22:27:42,627: DEBUG - Nothing to update in LDAP
2023-04-04 22:27:42,628: DEBUG - Permission 'grocy.main' updated
2023-04-04 22:27:42,928: DEBUG - To view the log of the operation 'Update URL related to permission 'grocy'', use the command 'yunohost log show 20230404-212742-permission_url-grocy'
2023-04-04 22:27:43,419: DEBUG - The permission database has been resynchronized
2023-04-04 22:27:43,961: DEBUG - SSOwat configuration regenerated
2023-04-04 22:27:43,975: INFO - Provisionning apt...
2023-04-04 22:27:44,072: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./provision_or_update_apt"  7>&1']'
2023-04-04 22:27:44,090: DEBUG - + source /usr/share/yunohost/helpers
2023-04-04 22:27:44,092: DEBUG - +++ set +o
2023-04-04 22:27:44,092: DEBUG - +++ grep xtrace
2023-04-04 22:27:44,095: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-04-04 22:27:44,096: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-04-04 22:27:44,137: DEBUG - + ynh_abort_if_errors
2023-04-04 22:27:44,138: DEBUG - + trap ynh_exit_properly EXIT
2023-04-04 22:27:44,139: DEBUG - + ynh_install_app_dependencies php8.0-ldap php8.0-mbstring php8.0-fileinfo php8.0-sqlite3 php8.0-gd php8.0-intl
2023-04-04 22:27:44,139: DEBUG - + local 'dependencies=php8.0-ldap php8.0-mbstring php8.0-fileinfo php8.0-sqlite3 php8.0-gd php8.0-intl'
2023-04-04 22:27:44,140: DEBUG - ++ echo 'php8.0-ldap php8.0-mbstring php8.0-fileinfo php8.0-sqlite3 php8.0-gd php8.0-intl'
2023-04-04 22:27:44,140: DEBUG - ++ sed 's/\([^\<=\>]\)\ \([^(]\)/\1, \2/g'
2023-04-04 22:27:44,145: DEBUG - + dependencies='php8.0-ldap, php8.0-mbstring, php8.0-fileinfo, php8.0-sqlite3, php8.0-gd, php8.0-intl'
2023-04-04 22:27:44,145: DEBUG - + local 'dependencies=php8.0-ldap, php8.0-mbstring, php8.0-fileinfo, php8.0-sqlite3, php8.0-gd, php8.0-intl'
2023-04-04 22:27:44,146: DEBUG - ++ ynh_read_manifest --manifest_key=version
2023-04-04 22:27:44,183: DEBUG - ++ '[' '!' -e '' ']'
2023-04-04 22:27:44,183: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_hsa1ivm8/manifest.json ']'
2023-04-04 22:27:44,184: DEBUG - ++ '[' -e /var/cache/yunohost/app_tmp_work_dirs/app_hsa1ivm8/manifest.toml ']'
2023-04-04 22:27:44,185: DEBUG - ++ manifest=/var/cache/yunohost/app_tmp_work_dirs/app_hsa1ivm8/manifest.toml
2023-04-04 22:27:44,185: DEBUG - ++ echo /var/cache/yunohost/app_tmp_work_dirs/app_hsa1ivm8/manifest.toml
2023-04-04 22:27:44,185: DEBUG - ++ grep -q '\.json$'
2023-04-04 22:27:44,189: DEBUG - ++ cat /var/cache/yunohost/app_tmp_work_dirs/app_hsa1ivm8/manifest.toml
2023-04-04 22:27:44,189: DEBUG - ++ jq .version --raw-output
2023-04-04 22:27:44,190: DEBUG - ++ python3 -c 'import json, toml, sys; print(json.dumps(toml.load(sys.stdin)))'
2023-04-04 22:27:44,366: DEBUG - + local version=3.3.2~ynh3
2023-04-04 22:27:44,367: DEBUG - + '[' -z 3.3.2~ynh3 ']'
2023-04-04 22:27:44,367: DEBUG - + '[' 3.3.2~ynh3 == null ']'
2023-04-04 22:27:44,368: DEBUG - + local dep_app=grocy
2023-04-04 22:27:44,368: DEBUG - + [[ php8.0-ldap, php8.0-mbstring, php8.0-fileinfo, php8.0-sqlite3, php8.0-gd, php8.0-intl =~ [<=>] ]]
2023-04-04 22:27:44,369: DEBUG - ++ echo php8.0-ldap, php8.0-mbstring, php8.0-fileinfo, php8.0-sqlite3, php8.0-gd, php8.0-intl
2023-04-04 22:27:44,369: DEBUG - ++ grep -oP '(?<=php)[0-9.]+(?=-|\>)'
2023-04-04 22:27:44,369: DEBUG - ++ sort -u
2023-04-04 22:27:44,375: DEBUG - + local specific_php_version=8.0
2023-04-04 22:27:44,375: DEBUG - + [[ -n 8.0 ]]
2023-04-04 22:27:44,376: DEBUG - ++ echo 8.0
2023-04-04 22:27:44,377: DEBUG - ++ wc -l
2023-04-04 22:27:44,382: DEBUG - + [[ 1 -eq 1 ]]
2023-04-04 22:27:44,382: DEBUG - + dependencies+=', php8.0, php8.0-fpm, php8.0-common'
2023-04-04 22:27:44,383: DEBUG - ++ ynh_app_setting_get --app=grocy --key=phpversion
2023-04-04 22:27:44,383: DEBUG - ++ local _globalapp=grocy
2023-04-04 22:27:44,444: DEBUG - ++ app=grocy
2023-04-04 22:27:44,444: DEBUG - ++ [[ phpversion =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:27:44,445: DEBUG - ++ ynh_app_setting get grocy phpversion
2023-04-04 22:27:44,582: DEBUG - + local old_phpversion=8.0
2023-04-04 22:27:44,583: DEBUG - + '[' -n 8.0 ']'
2023-04-04 22:27:44,583: DEBUG - + '[' 8.0 '!=' 8.0 ']'
2023-04-04 22:27:44,583: DEBUG - + ynh_app_setting_set --app=grocy --key=phpversion --value=8.0
2023-04-04 22:27:44,583: DEBUG - + local _globalapp=grocy
2023-04-04 22:27:44,708: DEBUG - + app=grocy
2023-04-04 22:27:44,708: DEBUG - + [[ phpversion =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:27:44,709: DEBUG - + ynh_app_setting set grocy phpversion 8.0
2023-04-04 22:27:44,844: DEBUG - + test -e /usr/bin/php7.4
2023-04-04 22:27:44,845: DEBUG - + update-alternatives --set php /usr/bin/php7.4
2023-04-04 22:27:44,869: DEBUG - ++ ynh_package_is_installed postgresql-13
2023-04-04 22:27:44,890: DEBUG - ++ ynh_wait_dpkg_free
2023-04-04 22:27:45,234: DEBUG - ++ return 0
2023-04-04 22:27:45,235: DEBUG - ++ dpkg-query --show '--showformat=${Status}' postgresql-13
2023-04-04 22:27:45,235: DEBUG - ++ grep --count 'ok installed'
2023-04-04 22:27:45,274: DEBUG - ++ echo yes
2023-04-04 22:27:45,275: DEBUG - + local psql_installed=yes
2023-04-04 22:27:45,276: DEBUG - + [[ true == \t\r\u\e ]]
2023-04-04 22:27:45,276: DEBUG - + YNH_INSTALL_APP_DEPENDENCIES_REPLACE=false
2023-04-04 22:27:45,276: DEBUG - + cat
2023-04-04 22:27:45,278: DEBUG - + ynh_package_install_from_equivs /tmp/grocy-ynh-deps.control
2023-04-04 22:27:45,279: DEBUG - + local controlfile=/tmp/grocy-ynh-deps.control
2023-04-04 22:27:45,280: DEBUG - ++ grep '^Package: ' /tmp/grocy-ynh-deps.control
2023-04-04 22:27:45,280: DEBUG - ++ cut '--delimiter= ' --fields=2
2023-04-04 22:27:45,284: DEBUG - + local pkgname=grocy-ynh-deps
2023-04-04 22:27:45,285: DEBUG - ++ grep '^Version: ' /tmp/grocy-ynh-deps.control
2023-04-04 22:27:45,286: DEBUG - ++ cut '--delimiter= ' --fields=2
2023-04-04 22:27:45,291: DEBUG - + local pkgversion=3.3.2~ynh3
2023-04-04 22:27:45,291: DEBUG - + [[ -z grocy-ynh-deps ]]
2023-04-04 22:27:45,292: DEBUG - + [[ -z 3.3.2~ynh3 ]]
2023-04-04 22:27:45,292: DEBUG - + ynh_package_update
2023-04-04 22:27:45,292: DEBUG - + ynh_apt update
2023-04-04 22:27:45,292: DEBUG - + ynh_wait_dpkg_free
2023-04-04 22:27:45,612: DEBUG - + return 0
2023-04-04 22:27:45,612: DEBUG - + LC_ALL=C
2023-04-04 22:27:45,612: DEBUG - + DEBIAN_FRONTEND=noninteractive
2023-04-04 22:27:45,613: DEBUG - + apt-get --assume-yes --quiet -o=Acquire::Retries=3 -o=Dpkg::Use-Pty=0 update
2023-04-04 22:27:47,621: DEBUG - Hit:1 http://archive.raspberrypi.org/debian bullseye InRelease
2023-04-04 22:27:51,691: DEBUG - Hit:2 http://security.debian.org/debian-security bullseye-security InRelease
2023-04-04 22:27:51,702: DEBUG - Hit:3 http://deb.debian.org/debian bullseye InRelease
2023-04-04 22:27:51,830: DEBUG - Hit:4 http://forge.yunohost.org/debian bullseye InRelease
2023-04-04 22:27:51,924: DEBUG - Get:5 http://deb.debian.org/debian bullseye-updates InRelease [44.1 kB]
2023-04-04 22:27:52,290: DEBUG - Hit:6 https://packages.sury.org/php bullseye InRelease
2023-04-04 22:27:52,862: DEBUG - Fetched 44.1 kB in 7s (6242 B/s)
2023-04-04 22:27:56,855: DEBUG - Reading package lists...
2023-04-04 22:27:57,037: DEBUG - ++ mktemp --directory
2023-04-04 22:27:57,057: DEBUG - + local TMPDIR=/tmp/tmp.p0W7ymHmbT
2023-04-04 22:27:57,057: DEBUG - + rm -f /usr/share/equivs/template/debian/compat
2023-04-04 22:27:57,663: DEBUG - + ynh_wait_dpkg_free
2023-04-04 22:27:58,022: DEBUG - + return 0
2023-04-04 22:27:58,023: DEBUG - + cp /tmp/grocy-ynh-deps.control /tmp/tmp.p0W7ymHmbT/control
2023-04-04 22:27:58,029: DEBUG - + cd /tmp/tmp.p0W7ymHmbT
2023-04-04 22:27:58,030: DEBUG - + LC_ALL=C
2023-04-04 22:27:58,031: DEBUG - + equivs-build ./control
2023-04-04 22:27:58,663: DEBUG - dpkg-buildpackage: info: source package grocy-ynh-deps
2023-04-04 22:27:58,664: DEBUG - dpkg-buildpackage: info: source version 3.3.2~ynh3
2023-04-04 22:27:58,664: DEBUG - dpkg-buildpackage: info: source distribution unstable
2023-04-04 22:27:58,665: DEBUG - dpkg-buildpackage: info: source changed by Equivs Dummy Package Generator <root@maindomain.tld>
2023-04-04 22:27:58,793: DEBUG -  dpkg-source --before-build .
2023-04-04 22:27:58,794: DEBUG - dpkg-buildpackage: info: host architecture arm64
2023-04-04 22:27:59,133: DEBUG -  debian/rules clean
2023-04-04 22:27:59,146: DEBUG - dh clean
2023-04-04 22:27:59,406: DEBUG -    dh_clean
2023-04-04 22:27:59,497: DEBUG -  debian/rules binary
2023-04-04 22:27:59,500: DEBUG - dh binary
2023-04-04 22:27:59,696: DEBUG -    dh_update_autotools_config
2023-04-04 22:27:59,777: DEBUG -    dh_autoreconf
2023-04-04 22:27:59,911: DEBUG -    create-stamp debian/debhelper-build-stamp
2023-04-04 22:27:59,911: DEBUG -    dh_prep
2023-04-04 22:27:59,996: DEBUG -    dh_install
2023-04-04 22:28:00,094: DEBUG -    dh_installdocs
2023-04-04 22:28:00,216: DEBUG -    dh_installchangelogs
2023-04-04 22:28:00,474: DEBUG -    dh_perl
2023-04-04 22:28:00,579: DEBUG -    dh_link
2023-04-04 22:28:00,682: DEBUG -    dh_strip_nondeterminism
2023-04-04 22:28:00,978: DEBUG -    dh_compress
2023-04-04 22:28:01,094: DEBUG -    dh_fixperms
2023-04-04 22:28:01,211: DEBUG -    dh_missing
2023-04-04 22:28:01,288: DEBUG -    dh_installdeb
2023-04-04 22:28:01,387: DEBUG -    dh_gencontrol
2023-04-04 22:28:01,758: DEBUG -    dh_md5sums
2023-04-04 22:28:01,861: DEBUG -    dh_builddeb
2023-04-04 22:28:01,942: DEBUG - dpkg-deb: building package 'grocy-ynh-deps' in '../grocy-ynh-deps_3.3.2~ynh3_all.deb'.
2023-04-04 22:28:02,015: DEBUG -  dpkg-genbuildinfo --build=binary
2023-04-04 22:28:11,028: DEBUG -  dpkg-genchanges --build=binary >../grocy-ynh-deps_3.3.2~ynh3_arm64.changes
2023-04-04 22:28:11,266: DEBUG - dpkg-genchanges: info: binary-only upload (no source code included)
2023-04-04 22:28:11,275: DEBUG -  dpkg-source --after-build .
2023-04-04 22:28:11,573: DEBUG - dpkg-buildpackage: info: binary-only upload (no source included)
2023-04-04 22:28:11,587: DEBUG - 
2023-04-04 22:28:11,588: DEBUG - The package has been created.
2023-04-04 22:28:11,588: DEBUG - Attention, the package has been created in the current directory,
2023-04-04 22:28:11,588: DEBUG - not in ".." as indicated by the message above!
2023-04-04 22:28:11,592: DEBUG - + LC_ALL=C
2023-04-04 22:28:11,593: DEBUG - + tee ./dpkg_log
2023-04-04 22:28:11,593: DEBUG - + dpkg --force-depends --install ./grocy-ynh-deps_3.3.2~ynh3_all.deb
2023-04-04 22:28:11,689: DEBUG - Selecting previously unselected package grocy-ynh-deps.
2023-04-04 22:28:12,212: DEBUG - (Reading database ... 57919 files and directories currently installed.)
2023-04-04 22:28:12,218: DEBUG - Preparing to unpack .../grocy-ynh-deps_3.3.2~ynh3_all.deb ...
2023-04-04 22:28:12,225: DEBUG - Unpacking grocy-ynh-deps (3.3.2~ynh3) ...
2023-04-04 22:28:12,299: DEBUG - dpkg: grocy-ynh-deps: dependency problems, but configuring anyway as you requested:
2023-04-04 22:28:12,299: DEBUG -  grocy-ynh-deps depends on php8.0-ldap; however:
2023-04-04 22:28:12,299: DEBUG -   Package php8.0-ldap is not installed.
2023-04-04 22:28:12,300: DEBUG -  grocy-ynh-deps depends on php8.0-mbstring; however:
2023-04-04 22:28:12,300: DEBUG -   Package php8.0-mbstring is not installed.
2023-04-04 22:28:12,300: DEBUG -  grocy-ynh-deps depends on php8.0-sqlite3; however:
2023-04-04 22:28:12,300: DEBUG -   Package php8.0-sqlite3 is not installed.
2023-04-04 22:28:12,301: DEBUG -  grocy-ynh-deps depends on php8.0-gd; however:
2023-04-04 22:28:12,301: DEBUG -   Package php8.0-gd is not installed.
2023-04-04 22:28:12,301: DEBUG -  grocy-ynh-deps depends on php8.0-intl; however:
2023-04-04 22:28:12,301: DEBUG -   Package php8.0-intl is not installed.
2023-04-04 22:28:12,301: DEBUG - 
2023-04-04 22:28:12,301: DEBUG - Setting up grocy-ynh-deps (3.3.2~ynh3) ...
2023-04-04 22:28:12,380: DEBUG - + ynh_package_install --fix-broken
2023-04-04 22:28:12,380: DEBUG - + ynh_apt --no-remove --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold install --fix-broken
2023-04-04 22:28:12,380: DEBUG - + ynh_wait_dpkg_free
2023-04-04 22:28:12,712: DEBUG - + return 0
2023-04-04 22:28:12,712: DEBUG - + LC_ALL=C
2023-04-04 22:28:12,713: DEBUG - + DEBIAN_FRONTEND=noninteractive
2023-04-04 22:28:12,713: DEBUG - + apt-get --assume-yes --quiet -o=Acquire::Retries=3 -o=Dpkg::Use-Pty=0 --no-remove --option Dpkg::Options::=--force-confdef --option Dpkg::Options::=--force-confold install --fix-broken
2023-04-04 22:28:13,852: DEBUG - Reading package lists...
2023-04-04 22:28:16,129: DEBUG - Building dependency tree...
2023-04-04 22:28:16,137: DEBUG - Reading state information...
2023-04-04 22:28:16,852: DEBUG - Correcting dependencies... Done
2023-04-04 22:28:17,697: DEBUG - The following additional packages will be installed:
2023-04-04 22:28:17,699: DEBUG -   php8.0-gd php8.0-intl php8.0-ldap php8.0-mbstring php8.0-sqlite3
2023-04-04 22:28:17,817: DEBUG - The following NEW packages will be installed:
2023-04-04 22:28:17,819: DEBUG -   php8.0-gd php8.0-intl php8.0-ldap php8.0-mbstring php8.0-sqlite3
2023-04-04 22:28:19,116: DEBUG - 0 upgraded, 5 newly installed, 0 to remove and 1 not upgraded.
2023-04-04 22:28:19,116: DEBUG - Need to get 576 kB of archives.
2023-04-04 22:28:19,117: DEBUG - After this operation, 1935 kB of additional disk space will be used.
2023-04-04 22:28:19,117: DEBUG - Get:1 https://packages.sury.org/php bullseye/main arm64 php8.0-gd arm64 1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35 [26.5 kB]
2023-04-04 22:28:19,564: DEBUG - Get:2 https://packages.sury.org/php bullseye/main arm64 php8.0-intl arm64 1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35 [113 kB]
2023-04-04 22:28:19,978: DEBUG - Get:3 https://packages.sury.org/php bullseye/main arm64 php8.0-ldap arm64 1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35 [27.0 kB]
2023-04-04 22:28:20,019: DEBUG - Get:4 https://packages.sury.org/php bullseye/main arm64 php8.0-mbstring arm64 1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35 [384 kB]
2023-04-04 22:28:20,365: DEBUG - Get:5 https://packages.sury.org/php bullseye/main arm64 php8.0-sqlite3 arm64 1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35 [26.0 kB]
2023-04-04 22:28:21,778: DEBUG - Fetched 576 kB in 2s (231 kB/s)
2023-04-04 22:28:21,897: DEBUG - Selecting previously unselected package php8.0-gd.
2023-04-04 22:28:21,980: DEBUG - (Reading database ... 57923 files and directories currently installed.)
2023-04-04 22:28:21,986: DEBUG - Preparing to unpack .../php8.0-gd_1%3a8.0.28-1+0~20230214.50+debian11~1.gbp452b35_arm64.deb ...
2023-04-04 22:28:22,026: DEBUG - Unpacking php8.0-gd (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:22,296: DEBUG - Selecting previously unselected package php8.0-intl.
2023-04-04 22:28:22,307: DEBUG - Preparing to unpack .../php8.0-intl_1%3a8.0.28-1+0~20230214.50+debian11~1.gbp452b35_arm64.deb ...
2023-04-04 22:28:22,333: DEBUG - Unpacking php8.0-intl (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:22,555: DEBUG - Selecting previously unselected package php8.0-ldap.
2023-04-04 22:28:22,569: DEBUG - Preparing to unpack .../php8.0-ldap_1%3a8.0.28-1+0~20230214.50+debian11~1.gbp452b35_arm64.deb ...
2023-04-04 22:28:22,592: DEBUG - Unpacking php8.0-ldap (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:22,779: DEBUG - Selecting previously unselected package php8.0-mbstring.
2023-04-04 22:28:22,791: DEBUG - Preparing to unpack .../php8.0-mbstring_1%3a8.0.28-1+0~20230214.50+debian11~1.gbp452b35_arm64.deb ...
2023-04-04 22:28:22,812: DEBUG - Unpacking php8.0-mbstring (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:23,067: DEBUG - Selecting previously unselected package php8.0-sqlite3.
2023-04-04 22:28:23,079: DEBUG - Preparing to unpack .../php8.0-sqlite3_1%3a8.0.28-1+0~20230214.50+debian11~1.gbp452b35_arm64.deb ...
2023-04-04 22:28:23,101: DEBUG - Unpacking php8.0-sqlite3 (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:23,270: DEBUG - Setting up php8.0-mbstring (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:23,751: DEBUG - 
2023-04-04 22:28:23,753: DEBUG - Creating config file /etc/php/8.0/mods-available/mbstring.ini with new version
2023-04-04 22:28:24,333: DEBUG - Setting up php8.0-intl (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:24,781: DEBUG - 
2023-04-04 22:28:24,781: DEBUG - Creating config file /etc/php/8.0/mods-available/intl.ini with new version
2023-04-04 22:28:25,302: DEBUG - Setting up php8.0-gd (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:25,783: DEBUG - 
2023-04-04 22:28:25,784: DEBUG - Creating config file /etc/php/8.0/mods-available/gd.ini with new version
2023-04-04 22:28:26,387: DEBUG - Setting up php8.0-ldap (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:26,847: DEBUG - 
2023-04-04 22:28:26,847: DEBUG - Creating config file /etc/php/8.0/mods-available/ldap.ini with new version
2023-04-04 22:28:27,465: DEBUG - Setting up php8.0-sqlite3 (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:27,930: DEBUG - 
2023-04-04 22:28:27,931: DEBUG - Creating config file /etc/php/8.0/mods-available/sqlite3.ini with new version
2023-04-04 22:28:28,923: DEBUG - 
2023-04-04 22:28:28,924: DEBUG - Creating config file /etc/php/8.0/mods-available/pdo_sqlite.ini with new version
2023-04-04 22:28:29,427: DEBUG - Processing triggers for php8.0-fpm (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:30,005: DEBUG - Processing triggers for php8.0-phpdbg (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:30,024: DEBUG - Processing triggers for php8.0-cli (1:8.0.28-1+0~20230214.50+debian11~1.gbp452b35) ...
2023-04-04 22:28:30,636: DEBUG - + [[ -n /tmp/tmp.p0W7ymHmbT ]]
2023-04-04 22:28:30,636: DEBUG - + rm --recursive --force /tmp/tmp.p0W7ymHmbT
2023-04-04 22:28:30,639: DEBUG - + ynh_package_is_installed grocy-ynh-deps
2023-04-04 22:28:30,662: DEBUG - + ynh_wait_dpkg_free
2023-04-04 22:28:30,999: DEBUG - + return 0
2023-04-04 22:28:31,001: DEBUG - + dpkg-query --show '--showformat=${Status}' grocy-ynh-deps
2023-04-04 22:28:31,002: DEBUG - + grep --count 'ok installed'
2023-04-04 22:28:31,036: DEBUG - + rm /tmp/grocy-ynh-deps.control
2023-04-04 22:28:31,042: DEBUG - ++ ynh_package_is_installed postgresql-13
2023-04-04 22:28:31,073: DEBUG - ++ ynh_wait_dpkg_free
2023-04-04 22:28:31,417: DEBUG - ++ return 0
2023-04-04 22:28:31,418: DEBUG - ++ dpkg-query --show '--showformat=${Status}' postgresql-13
2023-04-04 22:28:31,419: DEBUG - ++ grep --count 'ok installed'
2023-04-04 22:28:31,450: DEBUG - ++ echo yes
2023-04-04 22:28:31,451: DEBUG - + local psql_installed2=yes
2023-04-04 22:28:31,452: DEBUG - + [[ yes != \y\e\s ]]
2023-04-04 22:28:31,453: DEBUG - + ynh_exit_properly
2023-04-04 22:28:31,454: DEBUG - + [[ provision_or_update_apt =~ ^install$|^upgrade$|^restore$ ]]
2023-04-04 22:28:32,458: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "/var/cache/yunohost/app_tmp_work_dirs/app_9m0hq3xt/restore"  7>&1']'
2023-04-04 22:28:32,470: DEBUG - + source ../settings/scripts/_common.sh
2023-04-04 22:28:32,471: DEBUG - + source /usr/share/yunohost/helpers
2023-04-04 22:28:32,472: DEBUG - +++ set +o
2023-04-04 22:28:32,473: DEBUG - +++ grep xtrace
2023-04-04 22:28:32,477: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-04-04 22:28:32,477: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-04-04 22:28:32,687: INFO - [+++++++++++.........] > Restoring grocy main directory...
2023-04-04 22:28:32,688: DEBUG - + ynh_restore_file --origin_path=/var/www/grocy
2023-04-04 22:28:32,740: DEBUG - + origin_path=/var/www/grocy
2023-04-04 22:28:32,740: DEBUG - + dest_path=/var/www/grocy
2023-04-04 22:28:32,741: DEBUG - + not_mandatory=0
2023-04-04 22:28:32,741: DEBUG - + local archive_path=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/var/www/grocy
2023-04-04 22:28:32,742: DEBUG - + '[' '!' -d /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/var/www/grocy ']'
2023-04-04 22:28:32,742: DEBUG - + [[ -e /var/www/grocy ]]
2023-04-04 22:28:32,743: DEBUG - ++ du --summarize --bytes /var/www/grocy
2023-04-04 22:28:32,743: DEBUG - ++ cut --delimiter=/ --fields=1
2023-04-04 22:28:32,753: DEBUG - + [[ 4096	 -le 500000000 ]]
2023-04-04 22:28:32,754: DEBUG - ++ date +%Y%m%d.%H%M%S
2023-04-04 22:28:32,757: DEBUG - + local backup_file=/var/cache/yunohost/appconfbackup//var/www/grocy.backup.20230404.222832
2023-04-04 22:28:32,758: DEBUG - ++ dirname /var/cache/yunohost/appconfbackup//var/www/grocy.backup.20230404.222832
2023-04-04 22:28:32,762: DEBUG - + mkdir --parents /var/cache/yunohost/appconfbackup//var/www
2023-04-04 22:28:32,773: DEBUG - + mv /var/www/grocy /var/cache/yunohost/appconfbackup//var/www/grocy.backup.20230404.222832
2023-04-04 22:28:32,778: DEBUG - ++ dirname /var/www/grocy
2023-04-04 22:28:32,781: DEBUG - + mkdir --parents /var/www
2023-04-04 22:28:32,784: DEBUG - + mountpoint --quiet /home/yunohost.backup/tmp/20230401-051906
2023-04-04 22:28:32,793: DEBUG - + mv /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/var/www/grocy /var/www/grocy
2023-04-04 22:28:32,796: DEBUG - + [[ /var/www/grocy == \/\e\t\c\/\n\g\i\n\x\/\c\o\n\f\.\d\/* ]]
2023-04-04 22:28:32,797: DEBUG - + chmod -R o-rwx /var/www/grocy
2023-04-04 22:28:33,052: DEBUG - + chown -R grocy:www-data /var/www/grocy
2023-04-04 22:28:33,459: INFO - [###########++.......] > Restoring PHP-FPM configuration...
2023-04-04 22:28:33,460: DEBUG - + ynh_restore_file --origin_path=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:33,511: DEBUG - + origin_path=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:33,512: DEBUG - + dest_path=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:33,512: DEBUG - + not_mandatory=0
2023-04-04 22:28:33,513: DEBUG - + local archive_path=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:33,513: DEBUG - + '[' '!' -d /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/php/8.0/fpm/pool.d/grocy.conf ']'
2023-04-04 22:28:33,513: DEBUG - + '[' '!' -f /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/php/8.0/fpm/pool.d/grocy.conf ']'
2023-04-04 22:28:33,514: DEBUG - + [[ -e /etc/php/8.0/fpm/pool.d/grocy.conf ]]
2023-04-04 22:28:33,514: DEBUG - ++ dirname /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:33,516: DEBUG - + mkdir --parents /etc/php/8.0/fpm/pool.d
2023-04-04 22:28:33,519: DEBUG - + mountpoint --quiet /home/yunohost.backup/tmp/20230401-051906
2023-04-04 22:28:33,523: DEBUG - + mv /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/php/8.0/fpm/pool.d/grocy.conf /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:33,527: DEBUG - + [[ /etc/php/8.0/fpm/pool.d/grocy.conf == \/\e\t\c\/\n\g\i\n\x\/\c\o\n\f\.\d\/* ]]
2023-04-04 22:28:33,527: DEBUG - + ynh_add_fpm_config --usage=low --footprint=low --phpversion=8.0
2023-04-04 22:28:33,528: DEBUG - + local _globalphpversion=8.0
2023-04-04 22:28:33,772: DEBUG - + package=
2023-04-04 22:28:33,773: DEBUG - + use_template=1
2023-04-04 22:28:33,773: DEBUG - + usage=low
2023-04-04 22:28:33,773: DEBUG - + footprint=low
2023-04-04 22:28:33,774: DEBUG - + '[' -n low ']'
2023-04-04 22:28:33,774: DEBUG - + use_template=0
2023-04-04 22:28:33,774: DEBUG - + dedicated_service=0
2023-04-04 22:28:33,774: DEBUG - + dpkg --compare-versions 2.0 lt 2
2023-04-04 22:28:33,778: DEBUG - + phpversion=8.0
2023-04-04 22:28:33,779: DEBUG - ++ ynh_app_setting_get --app=grocy --key=phpversion
2023-04-04 22:28:33,780: DEBUG - ++ local _globalapp=grocy
2023-04-04 22:28:33,845: DEBUG - ++ app=grocy
2023-04-04 22:28:33,845: DEBUG - ++ [[ phpversion =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:33,846: DEBUG - ++ ynh_app_setting get grocy phpversion
2023-04-04 22:28:33,976: DEBUG - + local old_phpversion=8.0
2023-04-04 22:28:33,977: DEBUG - + '[' -n 8.0 ']'
2023-04-04 22:28:33,977: DEBUG - + '[' 8.0 '!=' 8.0 ']'
2023-04-04 22:28:33,977: DEBUG - + '[' -n '' ']'
2023-04-04 22:28:33,978: DEBUG - + local fpm_service=php8.0-fpm
2023-04-04 22:28:33,978: DEBUG - + local fpm_config_dir=/etc/php/8.0/fpm
2023-04-04 22:28:33,979: DEBUG - + mkdir --parents /etc/php/8.0/fpm/pool.d
2023-04-04 22:28:33,980: DEBUG - + ynh_app_setting_set --app=grocy --key=fpm_config_dir --value=/etc/php/8.0/fpm
2023-04-04 22:28:33,980: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:34,119: DEBUG - + app=grocy
2023-04-04 22:28:34,120: DEBUG - + [[ fpm_config_dir =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:34,120: DEBUG - + ynh_app_setting set grocy fpm_config_dir /etc/php/8.0/fpm
2023-04-04 22:28:34,261: DEBUG - + ynh_app_setting_set --app=grocy --key=fpm_service --value=php8.0-fpm
2023-04-04 22:28:34,262: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:34,404: DEBUG - + app=grocy
2023-04-04 22:28:34,405: DEBUG - + [[ fpm_service =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:34,405: DEBUG - + ynh_app_setting set grocy fpm_service php8.0-fpm
2023-04-04 22:28:34,547: DEBUG - + ynh_app_setting_set --app=grocy --key=fpm_dedicated_service --value=0
2023-04-04 22:28:34,548: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:34,686: DEBUG - + app=grocy
2023-04-04 22:28:34,686: DEBUG - + [[ fpm_dedicated_service =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:34,687: DEBUG - + ynh_app_setting set grocy fpm_dedicated_service 0
2023-04-04 22:28:34,819: DEBUG - + ynh_app_setting_set --app=grocy --key=phpversion --value=8.0
2023-04-04 22:28:34,819: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:34,956: DEBUG - + app=grocy
2023-04-04 22:28:34,957: DEBUG - + [[ phpversion =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:34,958: DEBUG - + ynh_app_setting set grocy phpversion 8.0
2023-04-04 22:28:35,109: DEBUG - + ynh_app_setting_set --app=grocy --key=fpm_footprint --value=low
2023-04-04 22:28:35,109: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:35,237: DEBUG - + app=grocy
2023-04-04 22:28:35,238: DEBUG - + [[ fpm_footprint =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:35,239: DEBUG - + ynh_app_setting set grocy fpm_footprint low
2023-04-04 22:28:35,381: DEBUG - + ynh_app_setting_set --app=grocy --key=fpm_usage --value=low
2023-04-04 22:28:35,382: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:35,549: DEBUG - + app=grocy
2023-04-04 22:28:35,550: DEBUG - + [[ fpm_usage =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:35,551: DEBUG - + ynh_app_setting set grocy fpm_usage low
2023-04-04 22:28:35,701: DEBUG - + ynh_get_scalable_phpfpm --usage=low --footprint=low
2023-04-04 22:28:35,798: DEBUG - + footprint=low
2023-04-04 22:28:35,798: DEBUG - + usage=low
2023-04-04 22:28:35,799: DEBUG - + print=0
2023-04-04 22:28:35,799: DEBUG - + '[' low = low ']'
2023-04-04 22:28:35,800: DEBUG - + footprint=20
2023-04-04 22:28:35,800: DEBUG - + '[' 20 -le 20 ']'
2023-04-04 22:28:35,801: DEBUG - + min_spare_servers_factor=8
2023-04-04 22:28:35,801: DEBUG - + '[' low = low ']'
2023-04-04 22:28:35,801: DEBUG - + php_pm=ondemand
2023-04-04 22:28:35,801: DEBUG - ++ ynh_get_ram --total --ignore_swap
2023-04-04 22:28:35,916: DEBUG - ++ ignore_swap=1
2023-04-04 22:28:35,917: DEBUG - ++ only_swap=0
2023-04-04 22:28:35,917: DEBUG - ++ free=0
2023-04-04 22:28:35,918: DEBUG - ++ total=1
2023-04-04 22:28:35,920: DEBUG - +++ LC_ALL=C
2023-04-04 22:28:35,921: DEBUG - +++ vmstat --stats --unit M
2023-04-04 22:28:35,922: DEBUG - +++ grep 'total memory'
2023-04-04 22:28:35,922: DEBUG - +++ awk '{print $1}'
2023-04-04 22:28:35,932: DEBUG - ++ local total_ram=3794
2023-04-04 22:28:35,934: DEBUG - +++ LC_ALL=C
2023-04-04 22:28:35,935: DEBUG - +++ vmstat --stats --unit M
2023-04-04 22:28:35,936: DEBUG - +++ awk '{print $1}'
2023-04-04 22:28:35,936: DEBUG - +++ grep 'total swap'
2023-04-04 22:28:35,942: DEBUG - ++ local total_swap=99
2023-04-04 22:28:35,942: DEBUG - ++ local total_ram_swap=3893
2023-04-04 22:28:35,943: DEBUG - ++ local ram=3893
2023-04-04 22:28:35,943: DEBUG - ++ ram=3794
2023-04-04 22:28:35,944: DEBUG - ++ echo 3794
2023-04-04 22:28:35,944: DEBUG - + local max_ram=3794
2023-04-04 22:28:35,944: DEBUG - + php_max_children=94
2023-04-04 22:28:35,945: DEBUG - + '[' ondemand = static ']'
2023-04-04 22:28:35,945: DEBUG - ++ at_least_one 94
2023-04-04 22:28:35,945: DEBUG - ++ '[' 94 -le 0 ']'
2023-04-04 22:28:35,946: DEBUG - ++ echo 94
2023-04-04 22:28:35,946: DEBUG - + php_max_children=94
2023-04-04 22:28:35,947: DEBUG - ++ nproc
2023-04-04 22:28:35,954: DEBUG - + local core_number=4
2023-04-04 22:28:35,955: DEBUG - + local max_proc=16
2023-04-04 22:28:35,955: DEBUG - + '[' 94 -gt 16 ']'
2023-04-04 22:28:35,956: DEBUG - + php_max_children=16
2023-04-04 22:28:35,956: DEBUG - ++ ynh_app_setting_get --app=grocy --key=php_forced_max_children
2023-04-04 22:28:35,957: DEBUG - ++ local _globalapp=grocy
2023-04-04 22:28:36,026: DEBUG - ++ app=grocy
2023-04-04 22:28:36,027: DEBUG - ++ [[ php_forced_max_children =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:36,028: DEBUG - ++ ynh_app_setting get grocy php_forced_max_children
2023-04-04 22:28:36,162: DEBUG - + local php_forced_max_children=
2023-04-04 22:28:36,162: DEBUG - + '[' -n '' ']'
2023-04-04 22:28:36,163: DEBUG - + '[' ondemand = dynamic ']'
2023-04-04 22:28:36,163: DEBUG - + php_min_spare_servers=0
2023-04-04 22:28:36,164: DEBUG - + php_max_spare_servers=0
2023-04-04 22:28:36,164: DEBUG - + php_start_servers=0
2023-04-04 22:28:36,165: DEBUG - + local phpfpm_path=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.conf
2023-04-04 22:28:36,166: DEBUG - [__APP__]
2023-04-04 22:28:36,166: DEBUG - 
2023-04-04 22:28:36,167: DEBUG - user = __APP__
2023-04-04 22:28:36,167: DEBUG - group = __APP__
2023-04-04 22:28:36,168: DEBUG - 
2023-04-04 22:28:36,168: DEBUG - chdir = __INSTALL_DIR__
2023-04-04 22:28:36,169: DEBUG - 
2023-04-04 22:28:36,169: DEBUG - listen = /var/run/php/php__PHPVERSION__-fpm-__APP__.sock
2023-04-04 22:28:36,170: DEBUG - listen.owner = www-data
2023-04-04 22:28:36,170: DEBUG - listen.group = www-data
2023-04-04 22:28:36,171: DEBUG - 
2023-04-04 22:28:36,171: DEBUG - pm = __PHP_PM__
2023-04-04 22:28:36,171: DEBUG - pm.max_children = __PHP_MAX_CHILDREN__
2023-04-04 22:28:36,172: DEBUG - pm.max_requests = 500
2023-04-04 22:28:36,172: DEBUG - request_terminate_timeout = 1d
2023-04-04 22:28:36,172: DEBUG - '
2023-04-04 22:28:36,173: DEBUG - + '[' ondemand = dynamic ']'
2023-04-04 22:28:36,173: DEBUG - + '[' ondemand = ondemand ']'
2023-04-04 22:28:36,174: DEBUG - pm.process_idle_timeout = 10s
2023-04-04 22:28:36,174: DEBUG - '
2023-04-04 22:28:36,175: DEBUG - + '[' -e /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/extra_php-fpm.conf ']'
2023-04-04 22:28:36,175: DEBUG - + cat /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/extra_php-fpm.conf
2023-04-04 22:28:36,175: DEBUG - + local finalphpconf=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,175: DEBUG - + ynh_add_config --template=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.conf --destination=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,238: DEBUG - + '[' -f /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf//home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.conf ']'
2023-04-04 22:28:36,239: DEBUG - + '[' -f /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.conf ']'
2023-04-04 22:28:36,239: DEBUG - + template_path=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.conf
2023-04-04 22:28:36,239: DEBUG - + ynh_backup_if_checksum_is_different --file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,262: DEBUG - + local checksum_setting_name=checksum__etc_php_8.0_fpm_pool.d_grocy.conf
2023-04-04 22:28:36,262: DEBUG - ++ ynh_app_setting_get --app=grocy --key=checksum__etc_php_8.0_fpm_pool.d_grocy.conf
2023-04-04 22:28:36,263: DEBUG - ++ local _globalapp=grocy
2023-04-04 22:28:36,341: DEBUG - ++ app=grocy
2023-04-04 22:28:36,341: DEBUG - ++ [[ checksum__etc_php_8.0_fpm_pool.d_grocy.conf =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:36,342: DEBUG - ++ ynh_app_setting get grocy checksum__etc_php_8.0_fpm_pool.d_grocy.conf
2023-04-04 22:28:36,473: DEBUG - + local checksum_value=0c4ce86fbc2c7cdadd7d34087b6547b2
2023-04-04 22:28:36,474: DEBUG - + backup_file_checksum=
2023-04-04 22:28:36,474: DEBUG - + '[' -n 0c4ce86fbc2c7cdadd7d34087b6547b2 ']'
2023-04-04 22:28:36,474: DEBUG - + '[' -e /etc/php/8.0/fpm/pool.d/grocy.conf ']'
2023-04-04 22:28:36,475: DEBUG - + md5sum --check --status
2023-04-04 22:28:36,478: DEBUG - + touch /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,481: DEBUG - + chown root:root /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,484: DEBUG - + chmod 640 /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,486: DEBUG - + cp -f /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.conf /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,490: DEBUG - + _ynh_apply_default_permissions /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,490: DEBUG - + local target=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,493: DEBUG - ++ ynh_read_manifest --manifest_key=requirements.yunohost
2023-04-04 22:28:36,494: DEBUG - ++ tr -d '<>= '
2023-04-04 22:28:36,535: DEBUG - ++ '[' '!' -e '' ']'
2023-04-04 22:28:36,536: DEBUG - ++ '[' -e /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/manifest.json ']'
2023-04-04 22:28:36,536: DEBUG - ++ '[' -e /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/manifest.toml ']'
2023-04-04 22:28:36,537: DEBUG - ++ manifest=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/manifest.toml
2023-04-04 22:28:36,538: DEBUG - ++ echo /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/manifest.toml
2023-04-04 22:28:36,539: DEBUG - ++ grep -q '\.json$'
2023-04-04 22:28:36,544: DEBUG - ++ cat /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/manifest.toml
2023-04-04 22:28:36,545: DEBUG - ++ python3 -c 'import json, toml, sys; print(json.dumps(toml.load(sys.stdin)))'
2023-04-04 22:28:36,546: DEBUG - ++ jq .requirements.yunohost --raw-output
2023-04-04 22:28:36,696: DEBUG - + local ynh_requirement=null
2023-04-04 22:28:36,697: DEBUG - + dpkg --compare-versions 2.0 ge 2
2023-04-04 22:28:36,700: DEBUG - + chmod o-rwx /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,702: DEBUG - + chmod g-w /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,705: DEBUG - + chown -R root:root /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,708: DEBUG - + ynh_system_user_exists grocy
2023-04-04 22:28:36,732: DEBUG - + getent passwd grocy
2023-04-04 22:28:36,736: DEBUG - + chown grocy:grocy /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,744: DEBUG - + echo /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,745: DEBUG - + grep -q '^/etc/cron'
2023-04-04 22:28:36,749: DEBUG - + ynh_replace_vars --file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,771: DEBUG - + test -n /
2023-04-04 22:28:36,772: DEBUG - + local path_url_slash_less=
2023-04-04 22:28:36,772: DEBUG - + ynh_replace_string --match_string=__PATH__/ --replace_string=/ --target_file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,920: DEBUG - + sed --in-place $'s\001__PATH__/\001/\001g' /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:36,924: DEBUG - + ynh_replace_string --match_string=__PATH__ --replace_string=/ --target_file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,069: DEBUG - + sed --in-place $'s\001__PATH__\001/\001g' /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,073: DEBUG - + test -n grocy
2023-04-04 22:28:37,074: DEBUG - + ynh_replace_string --match_string=__NAME__ --replace_string=grocy --target_file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,218: DEBUG - + sed --in-place $'s\001__NAME__\001grocy\001g' /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,222: DEBUG - + ynh_replace_string --match_string=__NAMETOCHANGE__ --replace_string=grocy --target_file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,368: DEBUG - + sed --in-place $'s\001__NAMETOCHANGE__\001grocy\001g' /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,372: DEBUG - + ynh_replace_string --match_string=__USER__ --replace_string=grocy --target_file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,516: DEBUG - + sed --in-place $'s\001__USER__\001grocy\001g' /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,520: DEBUG - + test -n ''
2023-04-04 22:28:37,521: DEBUG - + dpkg --compare-versions 2.0 lt 2
2023-04-04 22:28:37,524: DEBUG - + test -n ''
2023-04-04 22:28:37,526: DEBUG - ++ grep -oP '__[A-Z0-9]+?[A-Z0-9_]*?[A-Z0-9]*?__' /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,527: DEBUG - ++ sed 's@__\([^.]*\)__@\L\1@g'
2023-04-04 22:28:37,528: DEBUG - ++ sort --unique
2023-04-04 22:28:37,533: DEBUG - + uniques_vars=('app' 'install_dir' 'php_max_children' 'php_pm' 'phpversion')
2023-04-04 22:28:37,534: DEBUG - + local delimit=@
2023-04-04 22:28:37,534: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-04-04 22:28:37,534: DEBUG - + [[ -v app ]]
2023-04-04 22:28:37,534: DEBUG - + match_string=__APP__
2023-04-04 22:28:37,535: DEBUG - + match_string=__APP__
2023-04-04 22:28:37,535: DEBUG - + replace_string=grocy
2023-04-04 22:28:37,535: DEBUG - + replace_string=grocy
2023-04-04 22:28:37,536: DEBUG - + replace_string=grocy
2023-04-04 22:28:37,536: DEBUG - + sed --in-place s@__APP__@grocy@g /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,538: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-04-04 22:28:37,538: DEBUG - + [[ -v install_dir ]]
2023-04-04 22:28:37,539: DEBUG - + match_string=__INSTALL_DIR__
2023-04-04 22:28:37,539: DEBUG - + match_string=__INSTALL_DIR__
2023-04-04 22:28:37,539: DEBUG - + replace_string=/var/www/grocy
2023-04-04 22:28:37,540: DEBUG - + replace_string=/var/www/grocy
2023-04-04 22:28:37,540: DEBUG - + replace_string=/var/www/grocy
2023-04-04 22:28:37,540: DEBUG - + sed --in-place s@__INSTALL_DIR__@/var/www/grocy@g /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,546: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-04-04 22:28:37,549: DEBUG - + [[ -v php_max_children ]]
2023-04-04 22:28:37,549: DEBUG - + match_string=__PHP_MAX_CHILDREN__
2023-04-04 22:28:37,550: DEBUG - + match_string=__PHP_MAX_CHILDREN__
2023-04-04 22:28:37,550: DEBUG - + replace_string=16
2023-04-04 22:28:37,551: DEBUG - + replace_string=16
2023-04-04 22:28:37,551: DEBUG - + replace_string=16
2023-04-04 22:28:37,552: DEBUG - + sed --in-place s@__PHP_MAX_CHILDREN__@16@g /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,555: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-04-04 22:28:37,556: DEBUG - + [[ -v php_pm ]]
2023-04-04 22:28:37,560: DEBUG - + match_string=__PHP_PM__
2023-04-04 22:28:37,560: DEBUG - + match_string=__PHP_PM__
2023-04-04 22:28:37,562: DEBUG - + replace_string=ondemand
2023-04-04 22:28:37,563: DEBUG - + replace_string=ondemand
2023-04-04 22:28:37,563: DEBUG - + replace_string=ondemand
2023-04-04 22:28:37,563: DEBUG - + sed --in-place s@__PHP_PM__@ondemand@g /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,564: DEBUG - + for one_var in "${uniques_vars[@]}"
2023-04-04 22:28:37,564: DEBUG - + [[ -v phpversion ]]
2023-04-04 22:28:37,564: DEBUG - + match_string=__PHPVERSION__
2023-04-04 22:28:37,565: DEBUG - + match_string=__PHPVERSION__
2023-04-04 22:28:37,565: DEBUG - + replace_string=8.0
2023-04-04 22:28:37,565: DEBUG - + replace_string=8.0
2023-04-04 22:28:37,566: DEBUG - + replace_string=8.0
2023-04-04 22:28:37,566: DEBUG - + sed --in-place s@__PHPVERSION__@8.0@g /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,566: DEBUG - + ynh_store_file_checksum --file=/etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,568: DEBUG - + update_only=0
2023-04-04 22:28:37,605: DEBUG - + local checksum_setting_name=checksum__etc_php_8.0_fpm_pool.d_grocy.conf
2023-04-04 22:28:37,607: DEBUG - ++ md5sum /etc/php/8.0/fpm/pool.d/grocy.conf
2023-04-04 22:28:37,608: DEBUG - ++ cut '--delimiter= ' --fields=1
2023-04-04 22:28:37,611: DEBUG - + ynh_app_setting_set --app=grocy --key=checksum__etc_php_8.0_fpm_pool.d_grocy.conf --value=0c4ce86fbc2c7cdadd7d34087b6547b2
2023-04-04 22:28:37,612: DEBUG - + local _globalapp=grocy
2023-04-04 22:28:37,755: DEBUG - + app=grocy
2023-04-04 22:28:37,756: DEBUG - + [[ checksum__etc_php_8.0_fpm_pool.d_grocy.conf =~ (unprotected|protected|skipped)_ ]]
2023-04-04 22:28:37,757: DEBUG - + ynh_app_setting set grocy checksum__etc_php_8.0_fpm_pool.d_grocy.conf 0c4ce86fbc2c7cdadd7d34087b6547b2
2023-04-04 22:28:37,897: DEBUG - + '[' -n '' ']'
2023-04-04 22:28:37,898: DEBUG - + unset backup_file_checksum
2023-04-04 22:28:37,898: DEBUG - + '[' -e /home/yunohost.backup/tmp/20230401-051906/apps/grocy/settings/conf/php-fpm.ini ']'
2023-04-04 22:28:37,898: DEBUG - + php-fpm8.0 --test
2023-04-04 22:28:38,099: DEBUG - + ynh_systemd_action --service_name=php8.0-fpm --action=reload
2023-04-04 22:28:38,300: DEBUG - + service_name=php8.0-fpm
2023-04-04 22:28:38,304: DEBUG - + action=reload
2023-04-04 22:28:38,305: DEBUG - + line_match=
2023-04-04 22:28:38,305: DEBUG - + length=20
2023-04-04 22:28:38,306: DEBUG - + log_path=/var/log/php8.0-fpm/php8.0-fpm.log
2023-04-04 22:28:38,306: DEBUG - + timeout=300
2023-04-04 22:28:38,306: DEBUG - + '[' reload == stop ']'
2023-04-04 22:28:38,307: DEBUG - + '[' reload == reload ']'
2023-04-04 22:28:38,307: DEBUG - + action=reload-or-restart
2023-04-04 22:28:38,307: DEBUG - ++ date --utc --rfc-3339=seconds
2023-04-04 22:28:38,307: DEBUG - ++ cut -d+ -f1
2023-04-04 22:28:38,309: DEBUG - + local 'time_start=2023-04-04 21:28:38 UTC'
2023-04-04 22:28:38,309: DEBUG - + systemctl reload-or-restart php8.0-fpm
2023-04-04 22:28:38,521: INFO - [#############++.....] > Restoring the NGINX configuration...
2023-04-04 22:28:38,523: DEBUG - + ynh_restore_file --origin_path=/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,579: DEBUG - + origin_path=/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,580: DEBUG - + dest_path=/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,580: DEBUG - + not_mandatory=0
2023-04-04 22:28:38,581: DEBUG - + local archive_path=/home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,581: DEBUG - + '[' '!' -d /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf ']'
2023-04-04 22:28:38,581: DEBUG - + '[' '!' -f /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf ']'
2023-04-04 22:28:38,582: DEBUG - + [[ -e /etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf ]]
2023-04-04 22:28:38,582: DEBUG - ++ dirname /etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,584: DEBUG - + mkdir --parents /etc/nginx/conf.d/grocy.maindomain.tld.d
2023-04-04 22:28:38,587: DEBUG - + mountpoint --quiet /home/yunohost.backup/tmp/20230401-051906
2023-04-04 22:28:38,592: DEBUG - + mv /home/yunohost.backup/tmp/20230401-051906/apps/grocy/backup/etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf /etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,595: DEBUG - + [[ /etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf == \/\e\t\c\/\n\g\i\n\x\/\c\o\n\f\.\d\/* ]]
2023-04-04 22:28:38,596: DEBUG - + grep 'php7.3.*sock' /etc/nginx/conf.d/grocy.maindomain.tld.d/grocy.conf
2023-04-04 22:28:38,774: INFO - [###############++...] > Reloading NGINX web server and PHP-FPM...
2023-04-04 22:28:38,776: DEBUG - + ynh_systemd_action --service_name=php8.0-fpm --action=reload
2023-04-04 22:28:38,979: DEBUG - + service_name=php8.0-fpm
2023-04-04 22:28:38,979: DEBUG - + action=reload
2023-04-04 22:28:38,980: DEBUG - + line_match=
2023-04-04 22:28:38,980: DEBUG - + length=20
2023-04-04 22:28:38,981: DEBUG - + log_path=/var/log/php8.0-fpm/php8.0-fpm.log
2023-04-04 22:28:38,982: DEBUG - + timeout=300
2023-04-04 22:28:38,983: DEBUG - + '[' reload == stop ']'
2023-04-04 22:28:38,985: DEBUG - + '[' reload == reload ']'
2023-04-04 22:28:38,986: DEBUG - + action=reload-or-restart
2023-04-04 22:28:38,986: DEBUG - ++ date --utc --rfc-3339=seconds
2023-04-04 22:28:38,987: DEBUG - ++ cut -d+ -f1
2023-04-04 22:28:38,988: DEBUG - + local 'time_start=2023-04-04 21:28:38 UTC'
2023-04-04 22:28:38,988: DEBUG - + systemctl reload-or-restart php8.0-fpm
2023-04-04 22:28:39,014: DEBUG - + ynh_systemd_action --service_name=nginx --action=reload
2023-04-04 22:28:39,231: DEBUG - + service_name=nginx
2023-04-04 22:28:39,232: DEBUG - + action=reload
2023-04-04 22:28:39,232: DEBUG - + line_match=
2023-04-04 22:28:39,232: DEBUG - + length=20
2023-04-04 22:28:39,232: DEBUG - + log_path=/var/log/nginx/nginx.log
2023-04-04 22:28:39,232: DEBUG - + timeout=300
2023-04-04 22:28:39,233: DEBUG - + '[' reload == stop ']'
2023-04-04 22:28:39,233: DEBUG - + '[' reload == reload ']'
2023-04-04 22:28:39,234: DEBUG - + action=reload-or-restart
2023-04-04 22:28:39,236: DEBUG - ++ date --utc --rfc-3339=seconds
2023-04-04 22:28:39,237: DEBUG - ++ cut -d+ -f1
2023-04-04 22:28:39,241: DEBUG - + local 'time_start=2023-04-04 21:28:39 UTC'
2023-04-04 22:28:39,242: DEBUG - + systemctl reload-or-restart nginx
2023-04-04 22:28:42,171: INFO - [####################] > Restoration completed for grocy
2023-04-04 22:28:42,172: DEBUG - + ynh_exit_properly
2023-04-04 22:28:42,173: DEBUG - + [[ restore =~ ^install$|^upgrade$|^restore$ ]]
```

### subdomain registration
```bash

```

### let's encrypt certificate 
```bash
args:
  force: true
  no_checks: true
ended_at: 2023-04-04 21:30:04.885862
error: null
interface: cli
operation: letsencrypt_cert_install
parent: null
related_to:
- - domain
  - grocy.maindomain.tld
started_at: 2023-04-04 21:29:28.904851
success: true
yunohost_version: 11.1.16

============

2023-04-04 22:29:28,919: DEBUG - Making sure tmp folders exists...
2023-04-04 22:29:28,968: DEBUG - Fetching IP from https://ip.yunohost.org 
2023-04-04 22:29:35,458: DEBUG - IP fetched: xx.xx.xx.xx
2023-04-04 22:29:35,472: DEBUG - No default route for IPv6, so assuming there's no IP address for that version
2023-04-04 22:29:35,472: DEBUG - IP fetched: None
2023-04-04 22:29:35,484: DEBUG - Prepare key and certificate signing request (CSR) for grocy.maindomain.tld...
2023-04-04 22:29:36,574: DEBUG - Saving to /tmp/acme-challenge-private/grocy.maindomain.tld.csr.
2023-04-04 22:29:36,575: DEBUG - Now using ACME Tiny to sign the certificate...
2023-04-04 22:29:36,575: INFO - Parsing account key...
2023-04-04 22:29:36,612: INFO - Parsing CSR...
2023-04-04 22:29:36,629: INFO - Found domains: grocy.maindomain.tld
2023-04-04 22:29:36,630: INFO - Getting directory...
2023-04-04 22:29:37,148: INFO - Directory found!
2023-04-04 22:29:37,148: INFO - Registering account...
2023-04-04 22:29:37,664: INFO - Already registered!
2023-04-04 22:29:37,665: INFO - Creating new order...
2023-04-04 22:29:38,498: INFO - Order created!
2023-04-04 22:29:39,112: INFO - Verifying grocy.maindomain.tld...
2023-04-04 22:29:40,536: INFO - grocy.maindomain.tld verified!
2023-04-04 22:29:40,537: INFO - Signing certificate...
2023-04-04 22:29:42,473: INFO - Certificate signed!
2023-04-04 22:29:42,474: DEBUG - Saving the key and signed certificate...
2023-04-04 22:29:42,477: DEBUG - Enabling the certificate for domain grocy.maindomain.tld ...
2023-04-04 22:29:42,480: DEBUG - Restarting services...
2023-04-04 22:29:42,691: DEBUG - Running 'systemctl restart dovecot'
2023-04-04 22:29:44,305: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nginx 7>&1']'
2023-04-04 22:29:44,325: DEBUG - + set -e
2023-04-04 22:29:44,326: DEBUG - + . /usr/share/yunohost/helpers
2023-04-04 22:29:44,327: DEBUG - +++ set +o
2023-04-04 22:29:44,328: DEBUG - +++ grep xtrace
2023-04-04 22:29:44,330: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-04-04 22:29:44,331: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-04-04 22:29:44,370: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nginx
2023-04-04 22:29:44,371: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nginx
2023-04-04 22:29:44,371: DEBUG - + cd /usr/share/yunohost/conf/nginx
2023-04-04 22:29:44,372: DEBUG - + nginx_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx
2023-04-04 22:29:44,372: DEBUG - + nginx_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:44,373: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:44,378: DEBUG - + cp plain/acme-challenge.conf.inc plain/global.conf plain/ssowat.conf plain/yunohost_http_errors.conf.inc plain/yunohost_panel.conf.inc plain/yunohost_sso.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:44,386: DEBUG - ++ yunohost settings get misc.portal.ssowat_panel_overlay_enabled
2023-04-04 22:29:44,387: DEBUG - ++ int_to_bool
2023-04-04 22:29:44,388: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-04-04 22:29:45,092: DEBUG - + panel_overlay=True
2023-04-04 22:29:45,092: DEBUG - + '[' True == False ']'
2023-04-04 22:29:45,094: DEBUG - ++ cat /etc/yunohost/current_host
2023-04-04 22:29:45,096: DEBUG - + main_domain=maindomain.tld
2023-04-04 22:29:45,098: DEBUG - ++ yunohost settings get security.nginx.nginx_redirect_to_https
2023-04-04 22:29:45,099: DEBUG - ++ int_to_bool
2023-04-04 22:29:45,100: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-04-04 22:29:45,751: DEBUG - + export redirect_to_https=True
2023-04-04 22:29:45,752: DEBUG - + redirect_to_https=True
2023-04-04 22:29:45,752: DEBUG - ++ yunohost settings get security.nginx.nginx_compatibility
2023-04-04 22:29:46,392: DEBUG - + export compatibility=intermediate
2023-04-04 22:29:46,393: DEBUG - + compatibility=intermediate
2023-04-04 22:29:46,394: DEBUG - ++ yunohost settings get security.experimental.security_experimental_enabled
2023-04-04 22:29:46,395: DEBUG - ++ int_to_bool
2023-04-04 22:29:46,395: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-04-04 22:29:47,040: DEBUG - + export experimental=False
2023-04-04 22:29:47,041: DEBUG - + experimental=False
2023-04-04 22:29:47,041: DEBUG - + ynh_render_template security.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-04-04 22:29:47,041: DEBUG - + local template_path=security.conf.inc
2023-04-04 22:29:47,042: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-04-04 22:29:47,042: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-04-04 22:29:47,043: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:47,046: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:47,047: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:47,047: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:47,268: DEBUG - ++ yunohost domain cert status --json
2023-04-04 22:29:48,056: DEBUG - + cert_status='{"certificates": {"maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "energy.maindomain.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "grocy.maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "home.maindomain.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "homeassistant.maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "nextcloud.maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "nodered.maindomain.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "owntracks.maindomain.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "wikijs.maindomain.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "domain2.tld": {"CA_type": "letsencrypt", "validity": 85, "style": "success", "summary": "letsencrypt"}, "domain3.tld": {"CA_type": "letsencrypt", "validity": 83, "style": "success", "summary": "letsencrypt"}}}'
2023-04-04 22:29:48,058: DEBUG - ++ yunohost domain list --features xmpp --output-as json
2023-04-04 22:29:48,059: DEBUG - ++ jq -r '.domains[]'
2023-04-04 22:29:48,837: DEBUG - + xmpp_domain_list=
2023-04-04 22:29:48,839: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-04-04 22:29:48,840: DEBUG - ++ jq -r '.domains[]'
2023-04-04 22:29:49,613: DEBUG - + mail_domain_list='maindomain.tld
2023-04-04 22:29:49,614: DEBUG - energy.maindomain.tld
2023-04-04 22:29:49,614: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:49,614: DEBUG - home.maindomain.tld
2023-04-04 22:29:49,615: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:49,615: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:49,615: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:49,616: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:49,616: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:49,617: DEBUG - domain2.tld
2023-04-04 22:29:49,617: DEBUG - domain3.tld'
2023-04-04 22:29:49,618: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:49,618: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-04-04 22:29:49,618: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-04-04 22:29:49,619: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-04-04 22:29:49,619: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-04-04 22:29:49,621: DEBUG - + export domain
2023-04-04 22:29:49,622: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:49,624: DEBUG - ++ jq '.certificates."maindomain.tld".CA_type'
2023-04-04 22:29:49,625: DEBUG - ++ tr -d '"'
2023-04-04 22:29:49,707: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:49,707: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:49,708: DEBUG - + grep -q '^maindomain.tld$'
2023-04-04 22:29:49,712: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:49,712: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:49,713: DEBUG - energy.maindomain.tld
2023-04-04 22:29:49,714: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:49,714: DEBUG - home.maindomain.tld
2023-04-04 22:29:49,715: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:49,715: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:49,715: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:49,717: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:49,718: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:49,719: DEBUG - domain2.tld
2023-04-04 22:29:49,720: DEBUG - domain3.tld'
2023-04-04 22:29:49,721: DEBUG - + grep -q '^maindomain.tld$'
2023-04-04 22:29:49,722: DEBUG - + export mail_enabled=True
2023-04-04 22:29:49,723: DEBUG - + mail_enabled=True
2023-04-04 22:29:49,723: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-04-04 22:29:49,725: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:49,726: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-04-04 22:29:49,726: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-04-04 22:29:49,727: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:49,728: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:49,729: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:49,729: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:49,992: DEBUG - + '[' True == True ']'
2023-04-04 22:29:49,993: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:49,994: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:49,994: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:49,996: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:49,997: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail
2023-04-04 22:29:50,000: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:50,001: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:50,001: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:50,207: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:50,210: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:50,210: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d
2023-04-04 22:29:50,211: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d
2023-04-04 22:29:50,213: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:50,214: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:50,217: DEBUG - + export domain
2023-04-04 22:29:50,218: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:50,220: DEBUG - ++ jq '.certificates."energy.maindomain.tld".CA_type'
2023-04-04 22:29:50,221: DEBUG - ++ tr -d '"'
2023-04-04 22:29:50,309: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:50,310: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:50,311: DEBUG - + grep -q '^energy.maindomain.tld$'
2023-04-04 22:29:50,314: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:50,315: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:50,316: DEBUG - energy.maindomain.tld
2023-04-04 22:29:50,317: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:50,317: DEBUG - home.maindomain.tld
2023-04-04 22:29:50,317: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:50,318: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:50,320: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:50,320: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:50,320: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:50,321: DEBUG - domain2.tld
2023-04-04 22:29:50,321: DEBUG - domain3.tld'
2023-04-04 22:29:50,322: DEBUG - + grep -q '^energy.maindomain.tld$'
2023-04-04 22:29:50,323: DEBUG - + export mail_enabled=True
2023-04-04 22:29:50,324: DEBUG - + mail_enabled=True
2023-04-04 22:29:50,324: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-04-04 22:29:50,324: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:50,325: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-04-04 22:29:50,326: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-04-04 22:29:50,327: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:50,327: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:50,328: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:50,328: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:50,528: DEBUG - + '[' True == True ']'
2023-04-04 22:29:50,529: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:50,529: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:50,530: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:50,530: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:50,532: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail
2023-04-04 22:29:50,535: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:50,536: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:50,536: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:50,720: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:50,722: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:50,723: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d
2023-04-04 22:29:50,724: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d
2023-04-04 22:29:50,727: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:50,727: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:50,730: DEBUG - + export domain
2023-04-04 22:29:50,733: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:50,735: DEBUG - ++ jq '.certificates."grocy.maindomain.tld".CA_type'
2023-04-04 22:29:50,736: DEBUG - ++ tr -d '"'
2023-04-04 22:29:50,826: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:50,827: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:50,827: DEBUG - + grep -q '^grocy.maindomain.tld$'
2023-04-04 22:29:50,831: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:50,832: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:50,833: DEBUG - energy.maindomain.tld
2023-04-04 22:29:50,833: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:50,833: DEBUG - home.maindomain.tld
2023-04-04 22:29:50,834: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:50,834: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:50,836: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:50,836: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:50,837: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:50,837: DEBUG - domain2.tld
2023-04-04 22:29:50,837: DEBUG - domain3.tld'
2023-04-04 22:29:50,838: DEBUG - + grep -q '^grocy.maindomain.tld$'
2023-04-04 22:29:50,839: DEBUG - + export mail_enabled=True
2023-04-04 22:29:50,840: DEBUG - + mail_enabled=True
2023-04-04 22:29:50,840: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf
2023-04-04 22:29:50,841: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:50,841: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf
2023-04-04 22:29:50,843: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf
2023-04-04 22:29:50,843: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:50,844: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:50,844: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:50,844: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:51,042: DEBUG - + '[' True == True ']'
2023-04-04 22:29:51,042: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:51,043: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:51,043: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:51,044: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:51,045: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail
2023-04-04 22:29:51,048: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:51,049: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:51,049: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:51,229: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:51,232: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:51,233: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d
2023-04-04 22:29:51,233: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d
2023-04-04 22:29:51,240: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:51,240: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:51,243: DEBUG - + export domain
2023-04-04 22:29:51,245: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:51,246: DEBUG - ++ tr -d '"'
2023-04-04 22:29:51,247: DEBUG - ++ jq '.certificates."home.maindomain.tld".CA_type'
2023-04-04 22:29:51,332: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:51,333: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:51,334: DEBUG - + grep -q '^home.maindomain.tld$'
2023-04-04 22:29:51,338: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:51,338: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:51,339: DEBUG - energy.maindomain.tld
2023-04-04 22:29:51,340: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:51,340: DEBUG - home.maindomain.tld
2023-04-04 22:29:51,340: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:51,341: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:51,341: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:51,341: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:51,342: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:51,342: DEBUG - domain2.tld
2023-04-04 22:29:51,343: DEBUG - domain3.tld'
2023-04-04 22:29:51,343: DEBUG - + grep -q '^home.maindomain.tld$'
2023-04-04 22:29:51,344: DEBUG - + export mail_enabled=True
2023-04-04 22:29:51,344: DEBUG - + mail_enabled=True
2023-04-04 22:29:51,344: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-04-04 22:29:51,345: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:51,345: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-04-04 22:29:51,345: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-04-04 22:29:51,346: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:51,349: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:51,349: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:51,350: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:51,549: DEBUG - + '[' True == True ']'
2023-04-04 22:29:51,549: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:51,550: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:51,550: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:51,551: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:51,553: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail
2023-04-04 22:29:51,556: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:51,557: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:51,557: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:51,738: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:51,741: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:51,741: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d
2023-04-04 22:29:51,742: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d
2023-04-04 22:29:51,745: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:51,745: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:51,748: DEBUG - + export domain
2023-04-04 22:29:51,751: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:51,752: DEBUG - ++ jq '.certificates."homeassistant.maindomain.tld".CA_type'
2023-04-04 22:29:51,753: DEBUG - ++ tr -d '"'
2023-04-04 22:29:51,837: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:51,838: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:51,839: DEBUG - + grep -q '^homeassistant.maindomain.tld$'
2023-04-04 22:29:51,842: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:51,843: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:51,844: DEBUG - energy.maindomain.tld
2023-04-04 22:29:51,844: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:51,845: DEBUG - home.maindomain.tld
2023-04-04 22:29:51,845: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:51,845: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:51,846: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:51,846: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:51,846: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:51,847: DEBUG - domain2.tld
2023-04-04 22:29:51,847: DEBUG - domain3.tld'
2023-04-04 22:29:51,848: DEBUG - + grep -q '^homeassistant.maindomain.tld$'
2023-04-04 22:29:51,848: DEBUG - + export mail_enabled=True
2023-04-04 22:29:51,849: DEBUG - + mail_enabled=True
2023-04-04 22:29:51,849: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-04-04 22:29:51,849: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:51,850: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-04-04 22:29:51,850: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-04-04 22:29:51,851: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:51,854: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:51,854: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:51,855: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:52,052: DEBUG - + '[' True == True ']'
2023-04-04 22:29:52,053: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:52,053: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:52,054: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:52,054: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:52,056: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail
2023-04-04 22:29:52,059: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:52,060: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:52,060: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:52,240: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:52,242: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:52,243: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d
2023-04-04 22:29:52,243: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d
2023-04-04 22:29:52,246: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:52,247: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:52,250: DEBUG - + export domain
2023-04-04 22:29:52,252: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:52,254: DEBUG - ++ jq '.certificates."nextcloud.maindomain.tld".CA_type'
2023-04-04 22:29:52,255: DEBUG - ++ tr -d '"'
2023-04-04 22:29:52,340: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:52,341: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:52,341: DEBUG - + grep -q '^nextcloud.maindomain.tld$'
2023-04-04 22:29:52,345: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:52,346: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:52,347: DEBUG - energy.maindomain.tld
2023-04-04 22:29:52,347: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:52,347: DEBUG - home.maindomain.tld
2023-04-04 22:29:52,348: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:52,348: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:52,349: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:52,349: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:52,349: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:52,350: DEBUG - domain2.tld
2023-04-04 22:29:52,350: DEBUG - domain3.tld'
2023-04-04 22:29:52,351: DEBUG - + grep -q '^nextcloud.maindomain.tld$'
2023-04-04 22:29:52,351: DEBUG - + export mail_enabled=True
2023-04-04 22:29:52,351: DEBUG - + mail_enabled=True
2023-04-04 22:29:52,352: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-04-04 22:29:52,352: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:52,353: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-04-04 22:29:52,353: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-04-04 22:29:52,354: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:52,356: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:52,357: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:52,357: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:52,562: DEBUG - + '[' True == True ']'
2023-04-04 22:29:52,562: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:52,563: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:52,564: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:52,564: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:52,566: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail
2023-04-04 22:29:52,571: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:52,572: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:52,572: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:52,770: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:52,773: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:52,774: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d
2023-04-04 22:29:52,774: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d
2023-04-04 22:29:52,777: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:52,777: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:52,780: DEBUG - + export domain
2023-04-04 22:29:52,782: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:52,784: DEBUG - ++ jq '.certificates."nodered.maindomain.tld".CA_type'
2023-04-04 22:29:52,784: DEBUG - ++ tr -d '"'
2023-04-04 22:29:52,877: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:52,878: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:52,879: DEBUG - + grep -q '^nodered.maindomain.tld$'
2023-04-04 22:29:52,883: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:52,884: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:52,885: DEBUG - energy.maindomain.tld
2023-04-04 22:29:52,885: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:52,885: DEBUG - home.maindomain.tld
2023-04-04 22:29:52,886: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:52,886: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:52,886: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:52,887: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:52,887: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:52,887: DEBUG - domain2.tld
2023-04-04 22:29:52,888: DEBUG - domain3.tld'
2023-04-04 22:29:52,889: DEBUG - + grep -q '^nodered.maindomain.tld$'
2023-04-04 22:29:52,889: DEBUG - + export mail_enabled=True
2023-04-04 22:29:52,889: DEBUG - + mail_enabled=True
2023-04-04 22:29:52,889: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf
2023-04-04 22:29:52,890: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:52,890: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf
2023-04-04 22:29:52,891: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf
2023-04-04 22:29:52,891: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:52,894: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:52,895: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:52,895: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:53,091: DEBUG - + '[' True == True ']'
2023-04-04 22:29:53,092: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:53,092: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:53,093: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:53,093: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:53,095: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail
2023-04-04 22:29:53,098: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:53,099: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:53,099: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:53,279: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:53,281: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:53,282: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d
2023-04-04 22:29:53,282: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d
2023-04-04 22:29:53,285: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:53,286: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:53,289: DEBUG - + export domain
2023-04-04 22:29:53,291: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:53,292: DEBUG - ++ jq '.certificates."owntracks.maindomain.tld".CA_type'
2023-04-04 22:29:53,294: DEBUG - ++ tr -d '"'
2023-04-04 22:29:53,379: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:53,380: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:53,381: DEBUG - + grep -q '^owntracks.maindomain.tld$'
2023-04-04 22:29:53,384: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:53,385: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:53,386: DEBUG - energy.maindomain.tld
2023-04-04 22:29:53,386: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:53,386: DEBUG - home.maindomain.tld
2023-04-04 22:29:53,387: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:53,387: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:53,387: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:53,388: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:53,389: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:53,389: DEBUG - domain2.tld
2023-04-04 22:29:53,389: DEBUG - domain3.tld'
2023-04-04 22:29:53,390: DEBUG - + grep -q '^owntracks.maindomain.tld$'
2023-04-04 22:29:53,390: DEBUG - + export mail_enabled=True
2023-04-04 22:29:53,390: DEBUG - + mail_enabled=True
2023-04-04 22:29:53,391: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf
2023-04-04 22:29:53,391: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:53,391: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf
2023-04-04 22:29:53,392: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf
2023-04-04 22:29:53,393: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:53,395: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:53,396: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:53,396: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:53,593: DEBUG - + '[' True == True ']'
2023-04-04 22:29:53,594: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:53,594: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:53,594: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:53,595: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:53,596: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail
2023-04-04 22:29:53,600: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:53,600: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:53,601: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:53,781: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:53,783: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:53,784: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d
2023-04-04 22:29:53,784: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d
2023-04-04 22:29:53,787: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:53,788: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/
2023-04-04 22:29:53,791: DEBUG - + export domain
2023-04-04 22:29:53,793: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:53,794: DEBUG - ++ jq '.certificates."wikijs.maindomain.tld".CA_type'
2023-04-04 22:29:53,795: DEBUG - ++ tr -d '"'
2023-04-04 22:29:53,896: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:53,897: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:53,898: DEBUG - + grep -q '^wikijs.maindomain.tld$'
2023-04-04 22:29:53,901: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:53,902: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:53,903: DEBUG - energy.maindomain.tld
2023-04-04 22:29:53,903: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:53,904: DEBUG - home.maindomain.tld
2023-04-04 22:29:53,904: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:53,904: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:53,905: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:53,905: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:53,905: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:53,906: DEBUG - domain2.tld
2023-04-04 22:29:53,906: DEBUG - domain3.tld'
2023-04-04 22:29:53,906: DEBUG - + grep -q '^wikijs.maindomain.tld$'
2023-04-04 22:29:53,907: DEBUG - + export mail_enabled=True
2023-04-04 22:29:53,907: DEBUG - + mail_enabled=True
2023-04-04 22:29:53,908: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-04-04 22:29:53,908: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:53,909: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-04-04 22:29:53,909: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-04-04 22:29:53,910: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:53,914: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:53,914: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:53,915: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:54,110: DEBUG - + '[' True == True ']'
2023-04-04 22:29:54,111: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:54,111: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:54,112: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:54,112: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:54,114: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail
2023-04-04 22:29:54,117: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:54,118: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:54,118: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:54,298: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d/yunohost_local.conf
2023-04-04 22:29:54,300: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:54,301: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d
2023-04-04 22:29:54,301: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d
2023-04-04 22:29:54,304: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail/
2023-04-04 22:29:54,304: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail/
2023-04-04 22:29:54,307: DEBUG - + export domain
2023-04-04 22:29:54,309: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:54,311: DEBUG - ++ jq '.certificates."domain2.tld".CA_type'
2023-04-04 22:29:54,312: DEBUG - ++ tr -d '"'
2023-04-04 22:29:54,397: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:54,397: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:54,399: DEBUG - + grep -q '^domain2.tld$'
2023-04-04 22:29:54,401: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:54,402: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:54,403: DEBUG - energy.maindomain.tld
2023-04-04 22:29:54,404: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:54,404: DEBUG - home.maindomain.tld
2023-04-04 22:29:54,404: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:54,405: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:54,405: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:54,406: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:54,406: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:54,406: DEBUG - domain2.tld
2023-04-04 22:29:54,407: DEBUG - domain3.tld'
2023-04-04 22:29:54,407: DEBUG - + grep -q '^domain2.tld$'
2023-04-04 22:29:54,408: DEBUG - + export mail_enabled=True
2023-04-04 22:29:54,408: DEBUG - + mail_enabled=True
2023-04-04 22:29:54,408: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-04-04 22:29:54,409: DEBUG - + local template_path=server.tpl.conf
2023-04-04 22:29:54,409: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-04-04 22:29:54,410: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-04-04 22:29:54,411: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-04-04 22:29:54,414: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:54,415: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:54,415: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:54,621: DEBUG - + '[' True == True ']'
2023-04-04 22:29:54,622: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:54,623: DEBUG - + local template_path=autoconfig.tpl.xml
2023-04-04 22:29:54,623: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:54,623: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail//config-v1.1.xml
2023-04-04 22:29:54,626: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail
2023-04-04 22:29:54,629: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-04-04 22:29:54,630: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-04-04 22:29:54,630: DEBUG -                     ).render(os.environ));'
2023-04-04 22:29:54,810: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d/yunohost_local.conf
2023-04-04 22:29:54,813: DEBUG - + for domain in $YNH_DOMAINS
2023-04-04 22:29:54,813: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.d
2023-04-04 22:29:54,814: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.d
2023-04-04 22:29:54,816: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail/
2023-04-04 22:29:54,817: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail/
2023-04-04 22:29:54,820: DEBUG - + export domain
2023-04-04 22:29:54,822: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-04-04 22:29:54,824: DEBUG - ++ jq '.certificates."domain3.tld".CA_type'
2023-04-04 22:29:54,825: DEBUG - ++ tr -d '"'
2023-04-04 22:29:54,914: DEBUG - + export domain_cert_ca=letsencrypt
2023-04-04 22:29:54,914: DEBUG - + domain_cert_ca=letsencrypt
2023-04-04 22:29:54,915: DEBUG - + grep -q '^domain3.tld$'
2023-04-04 22:29:54,918: DEBUG - + export xmpp_enabled=False
2023-04-04 22:29:54,919: DEBUG - + xmpp_enabled=False
2023-04-04 22:29:54,920: DEBUG - energy.maindomain.tld
2023-04-04 22:29:54,920: DEBUG - grocy.maindomain.tld
2023-04-04 22:29:54,921: DEBUG - home.maindomain.tld
2023-04-04 22:29:54,921: DEBUG - homeassistant.maindomain.tld
2023-04-04 22:29:54,921: DEBUG - nextcloud.maindomain.tld
2023-04-04 22:29:54,922: DEBUG - nodered.maindomain.tld
2023-04-04 22:29:54,922: DEBUG - owntracks.maindomain.tld
2023-04-04 22:29:54,923: DEBUG - wikijs.maindomain.tld
2023-04-04 22:29:54,923: DEBUG - domain2.tld
2023-04-04 22:29:54,924: DEBUG - domain3.tld'
2023-04-04 22:29:54,924: DEBUG - + grep -q '^domain3.tld$'
2023-04-04 22:29:54,924: DEBUG - + export mail_enabled=True
2023-04-04 22:29:54,925: DEBUG - + mail_enabled=True
2023-04-04 22:29:54,925: DEBUG - + ynh_render_template server.tp
```

### transfer domain 
```bash

```

### diagnosis logs 
```bash

```

## notes
- 