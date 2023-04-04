---
share: true
---
```ad-abstract
for configs set through yunohost.local or cli 
```

## faq

| **item** | **description** |
| --- | --- |
| url | yunohost.local |
| main-domain url | kirkrehn.mydns.me |
| web-ui access url | |
| ssh root user | root |
|ssh root pass | kirkhomelab |
| web ui admin user | kirkrehn |
| web ui admin pass | kirkster |


## troubleshooting

### entropy/memory errors and timeouts 

> [!WARNING] diagnosis
> log shows frequent `rngd` errors and `entropy` notices after server timeouts on web ui yet remains accessible via ssh on local network 


> [!NOTE] solution
> install rngd-tools to generate and fill entropy with random numbers without user input, should generate continuously in background when entropy is near limit and prevent frequent timeouts thus far experienced


```cpp
sudo apt-get update -qq
sudo apt-get install -y rng-tools

# verify rngd installed correctly
rngd --version
# check output
rngd 5

# to populate entropy pool, run rngd
sudo rngd

# this starts rngd in background then /dev/random is continously fed with random numbers from /dev/hwrandom
```

## logs

### set kirkrehn.myddns.me as main-domain
```sh
args:
  new_main_domain: maindomain.tld
ended_at: 2023-03-31 08:29:24.358971
error: null
interface: api
operation: domain_main_domain
parent: null
related_to:
- - domain
  - maindomain.tld
started_at: 2023-03-31 08:27:45.412795
success: true
yunohost_version: 11.1.15

============

2023-03-31 09:27:45,699: DEBUG - b''
2023-03-31 09:27:45,725: DEBUG - b''
2023-03-31 09:27:45,754: DEBUG - b''
2023-03-31 09:27:46,237: DEBUG - SSOwat configuration regenerated
2023-03-31 09:27:46,314: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./01-yunohost" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/yunohost 7>&1']'
2023-03-31 09:27:46,340: DEBUG - + set -e
2023-03-31 09:27:46,342: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/yunohost
2023-03-31 09:27:46,342: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/yunohost
2023-03-31 09:27:46,343: DEBUG - + cd /usr/share/yunohost/conf/yunohost
2023-03-31 09:27:46,343: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system
2023-03-31 09:27:46,346: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/
2023-03-31 09:27:46,349: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/cron.daily/
2023-03-31 09:27:46,353: DEBUG - + cat
2023-03-31 09:27:46,356: DEBUG - + cat
2023-03-31 09:27:46,359: DEBUG - + cat
2023-03-31 09:27:46,362: DEBUG - + ls -l /etc/yunohost/dyndns/Kdomain3.tld.+165+1234.key
2023-03-31 09:27:46,374: DEBUG - -rw------- 1 root root 124 Mar 28 09:16 /etc/yunohost/dyndns/Kdomain3.tld.+165+1234.key
2023-03-31 09:27:46,374: DEBUG - + cat
2023-03-31 09:27:46,378: DEBUG - + systemctl
2023-03-31 09:27:46,379: DEBUG - + grep -q ntp.service
2023-03-31 09:27:46,392: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/ntp.service.d/
2023-03-31 09:27:46,396: DEBUG - + cat
2023-03-31 09:27:46,399: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/nftables.service.d/
2023-03-31 09:27:46,402: DEBUG - + cat
2023-03-31 09:27:46,405: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/logind.conf.d/
2023-03-31 09:27:46,409: DEBUG - + cat
2023-03-31 09:27:46,412: DEBUG - + cp yunohost-api.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-api.service
2023-03-31 09:27:46,420: DEBUG - + cp yunohost-firewall.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-firewall.service
2023-03-31 09:27:46,424: DEBUG - + cp yunoprompt.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunoprompt.service
2023-03-31 09:27:46,429: DEBUG - + cp proc-hidepid.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/proc-hidepid.service
2023-03-31 09:27:46,433: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/dpkg/origins/
2023-03-31 09:27:46,437: DEBUG - + cp dpkg-origins /var/cache/yunohost/regenconf/pending/yunohost/etc/dpkg/origins/yunohost
2023-03-31 09:27:47,441: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./02-ssl" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/ssl 7>&1']'
2023-03-31 09:27:47,461: DEBUG - + set -e
2023-03-31 09:27:47,462: DEBUG - + ssl_dir=/usr/share/yunohost/ssl
2023-03-31 09:27:47,463: DEBUG - + template_dir=/usr/share/yunohost/conf/ssl/
2023-03-31 09:27:47,463: DEBUG - + ynh_ca=/etc/yunohost/certs/yunohost.org/ca.pem
2023-03-31 09:27:47,464: DEBUG - + ynh_crt=/etc/yunohost/certs/yunohost.org/crt.pem
2023-03-31 09:27:47,464: DEBUG - + ynh_key=**********
2023-03-31 09:27:47,465: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/ssl
2023-03-31 09:27:47,465: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/ssl
2023-03-31 09:27:47,465: DEBUG - + install -D -m 644 /usr/share/yunohost/conf/ssl//openssl.cnf /var/cache/yunohost/regenconf/pending/ssl//usr/share/yunohost/ssl/openssl.cnf
2023-03-31 09:27:48,469: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./03-ssh" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/ssh 7>&1']'
2023-03-31 09:27:48,489: DEBUG - + set -e
2023-03-31 09:27:48,490: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:27:48,492: DEBUG - +++ set +o
2023-03-31 09:27:48,493: DEBUG - +++ grep xtrace
2023-03-31 09:27:48,496: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:27:48,497: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:27:48,537: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/ssh
2023-03-31 09:27:48,537: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/ssh
2023-03-31 09:27:48,538: DEBUG - + cd /usr/share/yunohost/conf/ssh
2023-03-31 09:27:48,539: DEBUG - + [[ -f /proc/net/if_inet6 ]]
2023-03-31 09:27:48,539: DEBUG - + ipv6_enabled=true
2023-03-31 09:27:48,539: DEBUG - ++ ls /etc/ssh/ssh_host_ed25519_key /etc/ssh/ssh_host_rsa_key /etc/ssh/ssh_host_ecdsa_key
2023-03-31 09:27:48,543: DEBUG - + ssh_keys='/etc/ssh/ssh_host_ecdsa_key
2023-03-31 09:27:48,543: DEBUG - /etc/ssh/ssh_host_ed25519_key
2023-03-31 09:27:48,544: DEBUG - /etc/ssh/ssh_host_rsa_key'
2023-03-31 09:27:48,544: DEBUG - ++ yunohost settings get security.ssh.ssh_compatibility
2023-03-31 09:27:49,193: DEBUG - + export compatibility=modern
2023-03-31 09:27:49,194: DEBUG - + compatibility=modern
2023-03-31 09:27:49,194: DEBUG - ++ yunohost settings get security.ssh.ssh_port
2023-03-31 09:27:49,846: DEBUG - + export port=22
2023-03-31 09:27:49,847: DEBUG - + port=22
2023-03-31 09:27:49,848: DEBUG - ++ yunohost settings get security.ssh.ssh_password_authentication
2023-03-31 09:27:49,849: DEBUG - ++ int_to_bool
2023-03-31 09:27:49,850: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:27:50,511: DEBUG - + export password_authentication=True
2023-03-31 09:27:50,512: DEBUG - + password_authentication=True
2023-03-31 09:27:50,513: DEBUG - + export ssh_keys
2023-03-31 09:27:50,513: DEBUG - + export ipv6_enabled
2023-03-31 09:27:50,513: DEBUG - + ynh_render_template sshd_config /var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-31 09:27:50,514: DEBUG - + local template_path=sshd_config
2023-03-31 09:27:50,514: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-31 09:27:50,515: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-31 09:27:50,515: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/ssh/etc/ssh
2023-03-31 09:27:50,519: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:27:50,520: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:27:50,520: DEBUG -                     ).render(os.environ));'
2023-03-31 09:27:51,524: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./06-slapd" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/slapd 7>&1']'
2023-03-31 09:27:51,544: DEBUG - + set -e
2023-03-31 09:27:51,545: DEBUG - + tmp_backup_dir_file=/root/slapd-backup-dir.txt
2023-03-31 09:27:51,545: DEBUG - + config=/usr/share/yunohost/conf/slapd/config.ldif
2023-03-31 09:27:51,545: DEBUG - + db_init=/usr/share/yunohost/conf/slapd/db_init.ldif
2023-03-31 09:27:51,547: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/slapd
2023-03-31 09:27:51,547: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/slapd
2023-03-31 09:27:51,548: DEBUG - + rm -f /root/slapd-backup-dir.txt
2023-03-31 09:27:51,552: DEBUG - ++ grep '^database' /etc/ldap/slapd.conf
2023-03-31 09:27:51,553: DEBUG - ++ awk '{print $2}'
2023-03-31 09:27:51,560: DEBUG - + curr_backend=
2023-03-31 09:27:51,561: DEBUG - + '[' -e /etc/ldap/slapd.conf ']'
2023-03-31 09:27:51,561: DEBUG - + ldap_dir=/var/cache/yunohost/regenconf/pending/slapd/etc/ldap
2023-03-31 09:27:51,561: DEBUG - + schema_dir=/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema
2023-03-31 09:27:51,562: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/slapd/etc/ldap /var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema
2023-03-31 09:27:51,564: DEBUG - + cd /usr/share/yunohost/conf/slapd
2023-03-31 09:27:51,564: DEBUG - + cp -a ldap.conf /var/cache/yunohost/regenconf/pending/slapd/etc/ldap
2023-03-31 09:27:51,571: DEBUG - + cp -a sudo.ldif mailserver.ldif permission.ldif /var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema
2023-03-31 09:27:51,577: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/slapd/etc/systemd/system/slapd.service.d/
2023-03-31 09:27:51,580: DEBUG - + cp systemd-override.conf /var/cache/yunohost/regenconf/pending/slapd/etc/systemd/system/slapd.service.d/ynh-override.conf
2023-03-31 09:27:51,587: DEBUG - + install -D -m 644 slapd.default /var/cache/yunohost/regenconf/pending/slapd/etc/default/slapd
2023-03-31 09:27:52,590: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./09-nslcd" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nslcd 7>&1']'
2023-03-31 09:27:52,611: DEBUG - + set -e
2023-03-31 09:27:52,612: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nslcd
2023-03-31 09:27:52,612: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nslcd
2023-03-31 09:27:52,613: DEBUG - + cd /usr/share/yunohost/conf/nslcd
2023-03-31 09:27:52,613: DEBUG - + install -D -m 644 nslcd.conf /var/cache/yunohost/regenconf/pending/nslcd/etc/nslcd.conf
2023-03-31 09:27:53,617: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./10-apt" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/apt 7>&1']'
2023-03-31 09:27:53,635: DEBUG - + set -e
2023-03-31 09:27:53,636: DEBUG - + readonly YNH_DEFAULT_PHP_VERSION=7.4
2023-03-31 09:27:53,636: DEBUG - + YNH_DEFAULT_PHP_VERSION=7.4
2023-03-31 09:27:53,637: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/apt
2023-03-31 09:27:53,637: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/apt
2023-03-31 09:27:53,638: DEBUG - + mkdir --parents /var/cache/yunohost/regenconf/pending/apt/etc/apt/preferences.d
2023-03-31 09:27:53,642: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/apt/etc/apt/sources.list.d/
2023-03-31 09:27:53,647: DEBUG - ++ lsb_release --codename --short
2023-03-31 09:27:53,778: DEBUG - Package: php-common
2023-03-31 09:27:53,778: DEBUG - Pin: origin "packages.sury.org"
2023-03-31 09:27:53,779: DEBUG - Pin-Priority: 500'
2023-03-31 09:27:53,779: DEBUG - + packages_to_refuse_from_sury='php php-* openssl libssl1.1 libssl-dev'
2023-03-31 09:27:53,780: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-31 09:27:53,781: DEBUG - Package: php
2023-03-31 09:27:53,781: DEBUG - Pin: origin "packages.sury.org"
2023-03-31 09:27:53,782: DEBUG - Pin-Priority: -1'
2023-03-31 09:27:53,782: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-31 09:27:53,782: DEBUG - Package: php-*
2023-03-31 09:27:53,783: DEBUG - Pin: origin "packages.sury.org"
2023-03-31 09:27:53,783: DEBUG - Pin-Priority: -1'
2023-03-31 09:27:53,783: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-31 09:27:53,784: DEBUG - Package: openssl
2023-03-31 09:27:53,784: DEBUG - Pin: origin "packages.sury.org"
2023-03-31 09:27:53,784: DEBUG - Pin-Priority: -1'
2023-03-31 09:27:53,785: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-31 09:27:53,785: DEBUG - Package: libssl1.1
2023-03-31 09:27:53,785: DEBUG - Pin: origin "packages.sury.org"
2023-03-31 09:27:53,786: DEBUG - Pin-Priority: -1'
2023-03-31 09:27:53,786: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-31 09:27:53,786: DEBUG - Package: libssl-dev
2023-03-31 09:27:53,787: DEBUG - Pin: origin "packages.sury.org"
2023-03-31 09:27:53,787: DEBUG - Pin-Priority: -1'
2023-03-31 09:27:53,787: DEBUG - 
2023-03-31 09:27:53,788: DEBUG - # PLEASE READ THIS WARNING AND DON'\''T EDIT THIS FILE
2023-03-31 09:27:53,788: DEBUG - 
2023-03-31 09:27:53,788: DEBUG - # You are probably reading this file because you tried to install apache2 or
2023-03-31 09:27:53,788: DEBUG - # bind9. These 2 packages conflict with YunoHost.
2023-03-31 09:27:53,789: DEBUG - 
2023-03-31 09:27:53,789: DEBUG - # Installing apache2 will break nginx and break the entire YunoHost ecosystem
2023-03-31 09:27:53,789: DEBUG - # on your server, therefore don'\''t remove those lines!
2023-03-31 09:27:53,790: DEBUG - 
2023-03-31 09:27:53,790: DEBUG - # You have been warned.
2023-03-31 09:27:53,790: DEBUG - 
2023-03-31 09:27:53,790: DEBUG - Package: apache2
2023-03-31 09:27:53,791: DEBUG - Pin: release *
2023-03-31 09:27:53,791: DEBUG - Pin-Priority: -1
2023-03-31 09:27:53,791: DEBUG - 
2023-03-31 09:27:53,791: DEBUG - Package: apache2-bin
2023-03-31 09:27:53,792: DEBUG - Pin: release *
2023-03-31 09:27:53,792: DEBUG - Pin-Priority: -1
2023-03-31 09:27:53,792: DEBUG - 
2023-03-31 09:27:53,792: DEBUG - # Also bind9 will conflict with dnsmasq.
2023-03-31 09:27:53,793: DEBUG - # Same story as for apache2.
2023-03-31 09:27:53,793: DEBUG - # Don'\''t install it, don'\''t remove those lines.
2023-03-31 09:27:53,793: DEBUG - 
2023-03-31 09:27:53,793: DEBUG - Package: bind9
2023-03-31 09:27:53,794: DEBUG - Pin: release *
2023-03-31 09:27:53,794: DEBUG - Pin-Priority: -1
2023-03-31 09:27:53,794: DEBUG - '
2023-03-31 09:27:54,798: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./12-metronome" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/metronome 7>&1']'
2023-03-31 09:27:54,817: DEBUG - + set -e
2023-03-31 09:27:54,819: DEBUG - + dpkg --list
2023-03-31 09:27:54,820: DEBUG - + grep -q 'ii *metronome '
2023-03-31 09:27:54,863: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/metronome
2023-03-31 09:27:54,864: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/metronome
2023-03-31 09:27:54,865: DEBUG - + cd /usr/share/yunohost/conf/metronome
2023-03-31 09:27:54,865: DEBUG - + metronome_dir=/var/cache/yunohost/regenconf/pending/metronome/etc/metronome
2023-03-31 09:27:54,865: DEBUG - + metronome_conf_dir=/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d
2023-03-31 09:27:54,866: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d
2023-03-31 09:27:54,868: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-31 09:27:54,871: DEBUG - + main_domain=maindomain.tld
2023-03-31 09:27:54,872: DEBUG - + cat metronome.cfg.lua
2023-03-31 09:27:54,872: DEBUG - + sed 's/{{ main_domain }}/maindomain.tld/g'
2023-03-31 09:27:54,876: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,877: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/domain2.tld.cfg.lua
2023-03-31 09:27:54,878: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,879: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/energy.domain2.tld.cfg.lua
2023-03-31 09:27:54,881: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,882: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/firefly.domain2.tld.cfg.lua
2023-03-31 09:27:54,883: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,884: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/home.domain2.tld.cfg.lua
2023-03-31 09:27:54,886: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,887: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/homeassistant.domain2.tld.cfg.lua
2023-03-31 09:27:54,888: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,889: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/nextcloud.domain2.tld.cfg.lua
2023-03-31 09:27:54,891: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,891: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/webmail.domain2.tld.cfg.lua
2023-03-31 09:27:54,893: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,894: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/wikijs.domain2.tld.cfg.lua
2023-03-31 09:27:54,896: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,896: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/maindomain.tld.cfg.lua
2023-03-31 09:27:54,898: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,899: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/energy.maindomain.tld.cfg.lua
2023-03-31 09:27:54,901: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,901: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/grocy.maindomain.tld.cfg.lua
2023-03-31 09:27:54,903: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,904: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/home.maindomain.tld.cfg.lua
2023-03-31 09:27:54,906: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,906: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/homeassistant.maindomain.tld.cfg.lua
2023-03-31 09:27:54,908: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,909: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/mqtt.maindomain.tld.cfg.lua
2023-03-31 09:27:54,910: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,911: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/nextcloud.maindomain.tld.cfg.lua
2023-03-31 09:27:54,913: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,914: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/nodered.maindomain.tld.cfg.lua
2023-03-31 09:27:54,916: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,916: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/owntracks.maindomain.tld.cfg.lua
2023-03-31 09:27:54,918: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,919: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/webmail.maindomain.tld.cfg.lua
2023-03-31 09:27:54,921: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,922: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/wikijs.maindomain.tld.cfg.lua
2023-03-31 09:27:54,924: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,924: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/domain3.tld.cfg.lua
2023-03-31 09:27:54,926: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,927: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/homeassistant.domain3.tld.cfg.lua
2023-03-31 09:27:54,929: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:27:54,929: DEBUG - + touch /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/wikijs.domain3.tld.cfg.lua
2023-03-31 09:27:54,933: DEBUG - ++ yunohost domain list --features xmpp --output-as json
2023-03-31 09:27:54,934: DEBUG - ++ jq -r '.domains[]'
2023-03-31 09:27:55,748: DEBUG - + domain_list=
2023-03-31 09:27:55,751: DEBUG - ++ ls -1 /etc/metronome/conf.d
2023-03-31 09:27:55,752: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*\.cfg\.lua$/ { print $1 }'
2023-03-31 09:27:55,763: DEBUG - + conf_files=
2023-03-31 09:27:56,772: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nginx 7>&1']'
2023-03-31 09:27:56,807: DEBUG - + set -e
2023-03-31 09:27:56,809: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:27:56,810: DEBUG - +++ set +o
2023-03-31 09:27:56,811: DEBUG - +++ grep xtrace
2023-03-31 09:27:56,820: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:27:56,821: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:27:56,897: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nginx
2023-03-31 09:27:56,897: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nginx
2023-03-31 09:27:56,898: DEBUG - + cd /usr/share/yunohost/conf/nginx
2023-03-31 09:27:56,898: DEBUG - + nginx_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx
2023-03-31 09:27:56,899: DEBUG - + nginx_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:27:56,899: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:27:56,902: DEBUG - + cp plain/acme-challenge.conf.inc plain/global.conf plain/ssowat.conf plain/yunohost_http_errors.conf.inc plain/yunohost_panel.conf.inc plain/yunohost_sso.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:27:56,908: DEBUG - ++ yunohost settings get misc.portal.ssowat_panel_overlay_enabled
2023-03-31 09:27:56,909: DEBUG - ++ int_to_bool
2023-03-31 09:27:56,910: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:27:57,557: DEBUG - + panel_overlay=True
2023-03-31 09:27:57,557: DEBUG - + '[' True == False ']'
2023-03-31 09:27:57,558: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-31 09:27:57,561: DEBUG - + main_domain=maindomain.tld
2023-03-31 09:27:57,563: DEBUG - ++ yunohost settings get security.nginx.nginx_redirect_to_https
2023-03-31 09:27:57,564: DEBUG - ++ int_to_bool
2023-03-31 09:27:57,565: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:27:58,216: DEBUG - + export redirect_to_https=True
2023-03-31 09:27:58,217: DEBUG - + redirect_to_https=True
2023-03-31 09:27:58,217: DEBUG - ++ yunohost settings get security.nginx.nginx_compatibility
2023-03-31 09:27:58,867: DEBUG - + export compatibility=intermediate
2023-03-31 09:27:58,867: DEBUG - + compatibility=intermediate
2023-03-31 09:27:58,868: DEBUG - ++ yunohost settings get security.experimental.security_experimental_enabled
2023-03-31 09:27:58,869: DEBUG - ++ int_to_bool
2023-03-31 09:27:58,870: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:27:59,519: DEBUG - + export experimental=False
2023-03-31 09:27:59,519: DEBUG - + experimental=False
2023-03-31 09:27:59,520: DEBUG - + ynh_render_template security.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-31 09:27:59,520: DEBUG - + local template_path=security.conf.inc
2023-03-31 09:27:59,521: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-31 09:27:59,521: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-31 09:27:59,522: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:27:59,526: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:27:59,526: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:27:59,527: DEBUG -                     ).render(os.environ));'
2023-03-31 09:27:59,715: DEBUG - ++ yunohost domain cert status --json
2023-03-31 09:28:00,514: DEBUG - + cert_status='{"certificates": {"domain2.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "energy.domain2.tld": {"CA_type": "letsencrypt", "validity": 83, "style": "success", "summary": "letsencrypt"}, "firefly.domain2.tld": {"CA_type": "selfsigned", "validity": 3647, "style": "warning", "summary": "selfsigned"}, "home.domain2.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "homeassistant.domain2.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "nextcloud.domain2.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "webmail.domain2.tld": {"CA_type": "letsencrypt", "validity": 83, "style": "success", "summary": "letsencrypt"}, "wikijs.domain2.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "energy.maindomain.tld": {"CA_type": "letsencrypt", "validity": 84, "style": "success", "summary": "letsencrypt"}, "grocy.maindomain.tld": {"CA_type": "letsencrypt", "validity": 57, "style": "success", "summary": "letsencrypt"}, "home.maindomain.tld": {"CA_type": "letsencrypt", "validity": 52, "style": "success", "summary": "letsencrypt"}, "homeassistant.maindomain.tld": {"CA_type": "letsencrypt", "validity": 53, "style": "success", "summary": "letsencrypt"}, "mqtt.maindomain.tld": {"CA_type": "letsencrypt", "validity": 53, "style": "success", "summary": "letsencrypt"}, "nextcloud.maindomain.tld": {"CA_type": "letsencrypt", "validity": 83, "style": "success", "summary": "letsencrypt"}, "nodered.maindomain.tld": {"CA_type": "letsencrypt", "validity": 74, "style": "success", "summary": "letsencrypt"}, "owntracks.maindomain.tld": {"CA_type": "letsencrypt", "validity": 52, "style": "success", "summary": "letsencrypt"}, "webmail.maindomain.tld": {"CA_type": "letsencrypt", "validity": 84, "style": "success", "summary": "letsencrypt"}, "wikijs.maindomain.tld": {"CA_type": "letsencrypt", "validity": 83, "style": "success", "summary": "letsencrypt"}, "domain3.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "homeassistant.domain3.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "wikijs.domain3.tld": {"CA_type": "letsencrypt", "validity": 88, "style": "success", "summary": "letsencrypt"}}}'
2023-03-31 09:28:00,516: DEBUG - ++ yunohost domain list --features xmpp --output-as json
2023-03-31 09:28:00,517: DEBUG - ++ jq -r '.domains[]'
2023-03-31 09:28:01,325: DEBUG - + xmpp_domain_list=
2023-03-31 09:28:01,327: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-31 09:28:01,327: DEBUG - ++ jq -r '.domains[]'
2023-03-31 09:28:02,187: DEBUG - + mail_domain_list='energy.domain2.tld
2023-03-31 09:28:02,188: DEBUG - firefly.domain2.tld
2023-03-31 09:28:02,189: DEBUG - home.domain2.tld
2023-03-31 09:28:02,189: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:02,189: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:02,190: DEBUG - webmail.domain2.tld
2023-03-31 09:28:02,190: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:02,191: DEBUG - energy.maindomain.tld
2023-03-31 09:28:02,191: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:02,192: DEBUG - home.maindomain.tld
2023-03-31 09:28:02,192: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:02,193: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:02,193: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:02,193: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:02,194: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:02,194: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:02,195: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:02,195: DEBUG - domain3.tld
2023-03-31 09:28:02,195: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:02,196: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:02,196: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:02,197: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d
2023-03-31 09:28:02,197: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d
2023-03-31 09:28:02,198: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail/
2023-03-31 09:28:02,199: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail/
2023-03-31 09:28:02,200: DEBUG - + export domain
2023-03-31 09:28:02,200: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:02,202: DEBUG - ++ jq '.certificates."domain2.tld".CA_type'
2023-03-31 09:28:02,203: DEBUG - ++ tr -d '"'
2023-03-31 09:28:02,282: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:02,282: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:02,284: DEBUG - + grep -q '^domain2.tld$'
2023-03-31 09:28:02,287: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:02,288: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:02,289: DEBUG - firefly.domain2.tld
2023-03-31 09:28:02,290: DEBUG - home.domain2.tld
2023-03-31 09:28:02,290: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:02,290: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:02,291: DEBUG - webmail.domain2.tld
2023-03-31 09:28:02,291: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:02,292: DEBUG - energy.maindomain.tld
2023-03-31 09:28:02,292: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:02,292: DEBUG - home.maindomain.tld
2023-03-31 09:28:02,293: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:02,293: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:02,294: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:02,294: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:02,295: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:02,295: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:02,295: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:02,296: DEBUG - domain3.tld
2023-03-31 09:28:02,296: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:02,297: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:02,297: DEBUG - + grep -q '^domain2.tld$'
2023-03-31 09:28:02,298: DEBUG - + export mail_enabled=False
2023-03-31 09:28:02,299: DEBUG - + mail_enabled=False
2023-03-31 09:28:02,299: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-03-31 09:28:02,299: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:02,300: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-03-31 09:28:02,300: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-03-31 09:28:02,301: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:02,301: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:02,302: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:02,302: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:02,500: DEBUG - + '[' False == True ']'
2023-03-31 09:28:02,501: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:02,503: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:02,504: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d
2023-03-31 09:28:02,505: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d
2023-03-31 09:28:02,508: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail/
2023-03-31 09:28:02,508: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail/
2023-03-31 09:28:02,512: DEBUG - + export domain
2023-03-31 09:28:02,514: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:02,516: DEBUG - ++ jq '.certificates."energy.domain2.tld".CA_type'
2023-03-31 09:28:02,517: DEBUG - ++ tr -d '"'
2023-03-31 09:28:02,604: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:02,604: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:02,606: DEBUG - + grep -q '^energy.domain2.tld$'
2023-03-31 09:28:02,609: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:02,610: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:02,612: DEBUG - firefly.domain2.tld
2023-03-31 09:28:02,612: DEBUG - home.domain2.tld
2023-03-31 09:28:02,613: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:02,613: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:02,614: DEBUG - webmail.domain2.tld
2023-03-31 09:28:02,614: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:02,614: DEBUG - energy.maindomain.tld
2023-03-31 09:28:02,615: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:02,615: DEBUG - home.maindomain.tld
2023-03-31 09:28:02,616: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:02,616: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:02,617: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:02,617: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:02,617: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:02,618: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:02,618: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:02,619: DEBUG - domain3.tld
2023-03-31 09:28:02,619: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:02,620: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:02,620: DEBUG - + grep -q '^energy.domain2.tld$'
2023-03-31 09:28:02,621: DEBUG - + export mail_enabled=True
2023-03-31 09:28:02,621: DEBUG - + mail_enabled=True
2023-03-31 09:28:02,621: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf
2023-03-31 09:28:02,622: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:02,622: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf
2023-03-31 09:28:02,623: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf
2023-03-31 09:28:02,623: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:02,624: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:02,624: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:02,625: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:02,824: DEBUG - + '[' True == True ']'
2023-03-31 09:28:02,825: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:02,826: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:02,826: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:02,827: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:02,828: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail
2023-03-31 09:28:02,832: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:02,833: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:02,833: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:03,016: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:03,018: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:03,019: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.d
2023-03-31 09:28:03,020: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.d
2023-03-31 09:28:03,022: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail/
2023-03-31 09:28:03,023: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail/
2023-03-31 09:28:03,026: DEBUG - + export domain
2023-03-31 09:28:03,029: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:03,031: DEBUG - ++ jq '.certificates."firefly.domain2.tld".CA_type'
2023-03-31 09:28:03,032: DEBUG - ++ tr -d '"'
2023-03-31 09:28:03,120: DEBUG - + export domain_cert_ca=selfsigned
2023-03-31 09:28:03,121: DEBUG - + domain_cert_ca=selfsigned
2023-03-31 09:28:03,122: DEBUG - + grep -q '^firefly.domain2.tld$'
2023-03-31 09:28:03,125: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:03,126: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:03,128: DEBUG - firefly.domain2.tld
2023-03-31 09:28:03,128: DEBUG - home.domain2.tld
2023-03-31 09:28:03,128: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:03,129: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:03,129: DEBUG - webmail.domain2.tld
2023-03-31 09:28:03,129: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:03,130: DEBUG - energy.maindomain.tld
2023-03-31 09:28:03,130: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:03,131: DEBUG - home.maindomain.tld
2023-03-31 09:28:03,131: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:03,132: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:03,132: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:03,132: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:03,133: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:03,133: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:03,134: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:03,134: DEBUG - domain3.tld
2023-03-31 09:28:03,134: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:03,135: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:03,135: DEBUG - + grep -q '^firefly.domain2.tld$'
2023-03-31 09:28:03,136: DEBUG - + export mail_enabled=True
2023-03-31 09:28:03,136: DEBUG - + mail_enabled=True
2023-03-31 09:28:03,137: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.conf
2023-03-31 09:28:03,138: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:03,138: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.conf
2023-03-31 09:28:03,139: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.conf
2023-03-31 09:28:03,139: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:03,140: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:03,140: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:03,141: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:03,341: DEBUG - + '[' True == True ']'
2023-03-31 09:28:03,341: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:03,342: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:03,342: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:03,343: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:03,345: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail
2023-03-31 09:28:03,348: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:03,349: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:03,349: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:03,531: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:03,534: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:03,535: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d
2023-03-31 09:28:03,535: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d
2023-03-31 09:28:03,538: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail/
2023-03-31 09:28:03,539: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail/
2023-03-31 09:28:03,542: DEBUG - + export domain
2023-03-31 09:28:03,545: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:03,547: DEBUG - ++ jq '.certificates."home.domain2.tld".CA_type'
2023-03-31 09:28:03,547: DEBUG - ++ tr -d '"'
2023-03-31 09:28:03,642: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:03,643: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:03,644: DEBUG - + grep -q '^home.domain2.tld$'
2023-03-31 09:28:03,647: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:03,648: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:03,649: DEBUG - firefly.domain2.tld
2023-03-31 09:28:03,650: DEBUG - home.domain2.tld
2023-03-31 09:28:03,650: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:03,651: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:03,651: DEBUG - webmail.domain2.tld
2023-03-31 09:28:03,651: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:03,652: DEBUG - energy.maindomain.tld
2023-03-31 09:28:03,652: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:03,653: DEBUG - home.maindomain.tld
2023-03-31 09:28:03,653: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:03,653: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:03,654: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:03,654: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:03,655: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:03,655: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:03,656: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:03,656: DEBUG - domain3.tld
2023-03-31 09:28:03,656: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:03,657: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:03,657: DEBUG - + grep -q '^home.domain2.tld$'
2023-03-31 09:28:03,658: DEBUG - + export mail_enabled=True
2023-03-31 09:28:03,658: DEBUG - + mail_enabled=True
2023-03-31 09:28:03,659: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf
2023-03-31 09:28:03,659: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:03,660: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf
2023-03-31 09:28:03,660: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf
2023-03-31 09:28:03,661: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:03,661: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:03,662: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:03,662: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:03,861: DEBUG - + '[' True == True ']'
2023-03-31 09:28:03,861: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:03,862: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:03,862: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:03,863: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:03,865: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail
2023-03-31 09:28:03,868: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:03,869: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:03,869: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:04,052: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:04,055: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:04,055: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d
2023-03-31 09:28:04,056: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d
2023-03-31 09:28:04,059: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/
2023-03-31 09:28:04,059: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/
2023-03-31 09:28:04,063: DEBUG - + export domain
2023-03-31 09:28:04,065: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:04,067: DEBUG - ++ jq '.certificates."homeassistant.domain2.tld".CA_type'
2023-03-31 09:28:04,068: DEBUG - ++ tr -d '"'
2023-03-31 09:28:04,151: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:04,152: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:04,153: DEBUG - + grep -q '^homeassistant.domain2.tld$'
2023-03-31 09:28:04,157: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:04,158: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:04,159: DEBUG - firefly.domain2.tld
2023-03-31 09:28:04,160: DEBUG - home.domain2.tld
2023-03-31 09:28:04,160: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:04,161: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:04,161: DEBUG - webmail.domain2.tld
2023-03-31 09:28:04,161: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:04,162: DEBUG - energy.maindomain.tld
2023-03-31 09:28:04,162: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:04,162: DEBUG - home.maindomain.tld
2023-03-31 09:28:04,163: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:04,164: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:04,164: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:04,164: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:04,165: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:04,165: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:04,165: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:04,166: DEBUG - domain3.tld
2023-03-31 09:28:04,166: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:04,167: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:04,167: DEBUG - + grep -q '^homeassistant.domain2.tld$'
2023-03-31 09:28:04,168: DEBUG - + export mail_enabled=True
2023-03-31 09:28:04,168: DEBUG - + mail_enabled=True
2023-03-31 09:28:04,168: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf
2023-03-31 09:28:04,169: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:04,169: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf
2023-03-31 09:28:04,170: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf
2023-03-31 09:28:04,170: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:04,171: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:04,171: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:04,172: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:04,378: DEBUG - + '[' True == True ']'
2023-03-31 09:28:04,379: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:04,381: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:04,383: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:04,384: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:04,385: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail
2023-03-31 09:28:04,386: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:04,388: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:04,388: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:04,600: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:04,603: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:04,604: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d
2023-03-31 09:28:04,604: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d
2023-03-31 09:28:04,607: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/
2023-03-31 09:28:04,608: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/
2023-03-31 09:28:04,612: DEBUG - + export domain
2023-03-31 09:28:04,614: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:04,617: DEBUG - ++ jq '.certificates."nextcloud.domain2.tld".CA_type'
2023-03-31 09:28:04,618: DEBUG - ++ tr -d '"'
2023-03-31 09:28:04,701: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:04,702: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:04,704: DEBUG - + grep -q '^nextcloud.domain2.tld$'
2023-03-31 09:28:04,707: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:04,708: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:04,709: DEBUG - firefly.domain2.tld
2023-03-31 09:28:04,710: DEBUG - home.domain2.tld
2023-03-31 09:28:04,710: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:04,711: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:04,711: DEBUG - webmail.domain2.tld
2023-03-31 09:28:04,711: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:04,712: DEBUG - energy.maindomain.tld
2023-03-31 09:28:04,712: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:04,713: DEBUG - home.maindomain.tld
2023-03-31 09:28:04,713: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:04,714: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:04,714: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:04,715: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:04,715: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:04,715: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:04,716: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:04,716: DEBUG - domain3.tld
2023-03-31 09:28:04,716: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:04,717: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:04,717: DEBUG - + grep -q '^nextcloud.domain2.tld$'
2023-03-31 09:28:04,718: DEBUG - + export mail_enabled=True
2023-03-31 09:28:04,718: DEBUG - + mail_enabled=True
2023-03-31 09:28:04,719: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf
2023-03-31 09:28:04,719: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:04,720: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf
2023-03-31 09:28:04,720: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf
2023-03-31 09:28:04,720: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:04,721: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:04,722: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:04,722: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:04,923: DEBUG - + '[' True == True ']'
2023-03-31 09:28:04,923: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:04,924: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:04,924: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:04,925: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:04,927: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail
2023-03-31 09:28:04,930: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:04,931: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:04,931: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:05,114: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:05,117: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:05,117: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.d
2023-03-31 09:28:05,118: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.d
2023-03-31 09:28:05,121: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail/
2023-03-31 09:28:05,121: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail/
2023-03-31 09:28:05,125: DEBUG - + export domain
2023-03-31 09:28:05,127: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:05,129: DEBUG - ++ jq '.certificates."webmail.domain2.tld".CA_type'
2023-03-31 09:28:05,130: DEBUG - ++ tr -d '"'
2023-03-31 09:28:05,211: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:05,212: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:05,213: DEBUG - + grep -q '^webmail.domain2.tld$'
2023-03-31 09:28:05,217: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:05,217: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:05,219: DEBUG - firefly.domain2.tld
2023-03-31 09:28:05,220: DEBUG - home.domain2.tld
2023-03-31 09:28:05,220: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:05,220: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:05,221: DEBUG - webmail.domain2.tld
2023-03-31 09:28:05,221: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:05,221: DEBUG - energy.maindomain.tld
2023-03-31 09:28:05,222: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:05,222: DEBUG - home.maindomain.tld
2023-03-31 09:28:05,223: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:05,223: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:05,224: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:05,224: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:05,225: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:05,225: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:05,225: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:05,226: DEBUG - domain3.tld
2023-03-31 09:28:05,226: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:05,227: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:05,227: DEBUG - + grep -q '^webmail.domain2.tld$'
2023-03-31 09:28:05,228: DEBUG - + export mail_enabled=True
2023-03-31 09:28:05,228: DEBUG - + mail_enabled=True
2023-03-31 09:28:05,229: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.conf
2023-03-31 09:28:05,229: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:05,229: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.conf
2023-03-31 09:28:05,230: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.conf
2023-03-31 09:28:05,230: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:05,231: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:05,231: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:05,232: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:05,434: DEBUG - + '[' True == True ']'
2023-03-31 09:28:05,435: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:05,435: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:05,436: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:05,436: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:05,438: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail
2023-03-31 09:28:05,442: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:05,442: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:05,443: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:05,628: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:05,630: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:05,631: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.d
2023-03-31 09:28:05,632: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.d
2023-03-31 09:28:05,634: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/
2023-03-31 09:28:05,635: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/
2023-03-31 09:28:05,639: DEBUG - + export domain
2023-03-31 09:28:05,642: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:05,644: DEBUG - ++ jq '.certificates."wikijs.domain2.tld".CA_type'
2023-03-31 09:28:05,644: DEBUG - ++ tr -d '"'
2023-03-31 09:28:05,751: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:05,752: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:05,753: DEBUG - + grep -q '^wikijs.domain2.tld$'
2023-03-31 09:28:05,757: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:05,758: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:05,759: DEBUG - firefly.domain2.tld
2023-03-31 09:28:05,760: DEBUG - home.domain2.tld
2023-03-31 09:28:05,760: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:05,760: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:05,761: DEBUG - webmail.domain2.tld
2023-03-31 09:28:05,761: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:05,761: DEBUG - energy.maindomain.tld
2023-03-31 09:28:05,762: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:05,762: DEBUG - home.maindomain.tld
2023-03-31 09:28:05,763: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:05,763: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:05,764: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:05,764: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:05,765: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:05,765: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:05,765: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:05,766: DEBUG - domain3.tld
2023-03-31 09:28:05,766: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:05,767: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:05,767: DEBUG - + grep -q '^wikijs.domain2.tld$'
2023-03-31 09:28:05,768: DEBUG - + export mail_enabled=True
2023-03-31 09:28:05,768: DEBUG - + mail_enabled=True
2023-03-31 09:28:05,769: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.conf
2023-03-31 09:28:05,769: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:05,769: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.conf
2023-03-31 09:28:05,770: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.conf
2023-03-31 09:28:05,770: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:05,771: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:05,772: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:05,773: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:05,974: DEBUG - + '[' True == True ']'
2023-03-31 09:28:05,975: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:05,975: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:05,976: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:05,976: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:05,978: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail
2023-03-31 09:28:05,982: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:05,982: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:05,983: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:06,165: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.d/yunohost_local.conf
2023-03-31 09:28:06,168: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:06,168: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-31 09:28:06,169: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-31 09:28:06,172: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-31 09:28:06,173: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-31 09:28:06,176: DEBUG - + export domain
2023-03-31 09:28:06,178: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:06,180: DEBUG - ++ jq '.certificates."maindomain.tld".CA_type'
2023-03-31 09:28:06,181: DEBUG - ++ tr -d '"'
2023-03-31 09:28:06,269: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:06,269: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:06,271: DEBUG - + grep -q '^maindomain.tld$'
2023-03-31 09:28:06,274: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:06,275: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:06,277: DEBUG - firefly.domain2.tld
2023-03-31 09:28:06,277: DEBUG - home.domain2.tld
2023-03-31 09:28:06,277: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:06,278: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:06,278: DEBUG - webmail.domain2.tld
2023-03-31 09:28:06,279: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:06,279: DEBUG - energy.maindomain.tld
2023-03-31 09:28:06,279: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:06,280: DEBUG - home.maindomain.tld
2023-03-31 09:28:06,280: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:06,281: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:06,281: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:06,282: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:06,282: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:06,283: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:06,283: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:06,283: DEBUG - domain3.tld
2023-03-31 09:28:06,284: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:06,284: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:06,285: DEBUG - + grep -q '^maindomain.tld$'
2023-03-31 09:28:06,285: DEBUG - + export mail_enabled=False
2023-03-31 09:28:06,286: DEBUG - + mail_enabled=False
2023-03-31 09:28:06,286: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-31 09:28:06,286: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:06,287: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-31 09:28:06,287: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-31 09:28:06,288: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:06,289: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:06,289: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:06,290: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:06,492: DEBUG - + '[' False == True ']'
2023-03-31 09:28:06,492: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:06,495: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:06,495: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d
2023-03-31 09:28:06,496: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d
2023-03-31 09:28:06,499: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:06,500: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:06,503: DEBUG - + export domain
2023-03-31 09:28:06,505: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:06,507: DEBUG - ++ jq '.certificates."energy.maindomain.tld".CA_type'
2023-03-31 09:28:06,508: DEBUG - ++ tr -d '"'
2023-03-31 09:28:06,595: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:06,596: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:06,597: DEBUG - + grep -q '^energy.maindomain.tld$'
2023-03-31 09:28:06,601: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:06,602: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:06,604: DEBUG - firefly.domain2.tld
2023-03-31 09:28:06,604: DEBUG - home.domain2.tld
2023-03-31 09:28:06,604: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:06,605: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:06,605: DEBUG - webmail.domain2.tld
2023-03-31 09:28:06,606: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:06,606: DEBUG - energy.maindomain.tld
2023-03-31 09:28:06,606: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:06,607: DEBUG - home.maindomain.tld
2023-03-31 09:28:06,607: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:06,608: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:06,609: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:06,609: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:06,609: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:06,610: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:06,610: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:06,611: DEBUG - domain3.tld
2023-03-31 09:28:06,611: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:06,612: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:06,612: DEBUG - + grep -q '^energy.maindomain.tld$'
2023-03-31 09:28:06,613: DEBUG - + export mail_enabled=True
2023-03-31 09:28:06,613: DEBUG - + mail_enabled=True
2023-03-31 09:28:06,613: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-03-31 09:28:06,614: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:06,615: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-03-31 09:28:06,616: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-03-31 09:28:06,616: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:06,616: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:06,617: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:06,618: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:06,821: DEBUG - + '[' True == True ']'
2023-03-31 09:28:06,822: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:06,822: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:06,823: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:06,823: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:06,825: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail
2023-03-31 09:28:06,828: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:06,829: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:06,830: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:07,015: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:07,019: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:07,020: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d
2023-03-31 09:28:07,020: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d
2023-03-31 09:28:07,024: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:07,025: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:07,029: DEBUG - + export domain
2023-03-31 09:28:07,033: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:07,036: DEBUG - ++ jq '.certificates."grocy.maindomain.tld".CA_type'
2023-03-31 09:28:07,037: DEBUG - ++ tr -d '"'
2023-03-31 09:28:07,147: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:07,147: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:07,149: DEBUG - + grep -q '^grocy.maindomain.tld$'
2023-03-31 09:28:07,152: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:07,153: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:07,154: DEBUG - firefly.domain2.tld
2023-03-31 09:28:07,155: DEBUG - home.domain2.tld
2023-03-31 09:28:07,155: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:07,156: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:07,156: DEBUG - webmail.domain2.tld
2023-03-31 09:28:07,156: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:07,157: DEBUG - energy.maindomain.tld
2023-03-31 09:28:07,157: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:07,157: DEBUG - home.maindomain.tld
2023-03-31 09:28:07,158: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:07,159: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:07,159: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:07,160: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:07,160: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:07,160: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:07,161: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:07,161: DEBUG - domain3.tld
2023-03-31 09:28:07,162: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:07,162: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:07,163: DEBUG - + grep -q '^grocy.maindomain.tld$'
2023-03-31 09:28:07,163: DEBUG - + export mail_enabled=True
2023-03-31 09:28:07,164: DEBUG - + mail_enabled=True
2023-03-31 09:28:07,164: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf
2023-03-31 09:28:07,165: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:07,165: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf
2023-03-31 09:28:07,165: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf
2023-03-31 09:28:07,166: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:07,167: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:07,167: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:07,167: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:07,374: DEBUG - + '[' True == True ']'
2023-03-31 09:28:07,374: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:07,375: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:07,376: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:07,376: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:07,378: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail
2023-03-31 09:28:07,381: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:07,382: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:07,383: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:07,576: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:07,579: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:07,579: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d
2023-03-31 09:28:07,580: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d
2023-03-31 09:28:07,582: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:07,583: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:07,586: DEBUG - + export domain
2023-03-31 09:28:07,589: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:07,591: DEBUG - ++ tr -d '"'
2023-03-31 09:28:07,592: DEBUG - ++ jq '.certificates."home.maindomain.tld".CA_type'
2023-03-31 09:28:07,699: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:07,700: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:07,701: DEBUG - + grep -q '^home.maindomain.tld$'
2023-03-31 09:28:07,705: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:07,705: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:07,707: DEBUG - firefly.domain2.tld
2023-03-31 09:28:07,707: DEBUG - home.domain2.tld
2023-03-31 09:28:07,708: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:07,708: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:07,709: DEBUG - webmail.domain2.tld
2023-03-31 09:28:07,709: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:07,709: DEBUG - energy.maindomain.tld
2023-03-31 09:28:07,710: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:07,710: DEBUG - home.maindomain.tld
2023-03-31 09:28:07,711: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:07,711: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:07,712: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:07,712: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:07,713: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:07,713: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:07,713: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:07,714: DEBUG - domain3.tld
2023-03-31 09:28:07,714: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:07,715: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:07,715: DEBUG - + grep -q '^home.maindomain.tld$'
2023-03-31 09:28:07,716: DEBUG - + export mail_enabled=True
2023-03-31 09:28:07,716: DEBUG - + mail_enabled=True
2023-03-31 09:28:07,716: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-03-31 09:28:07,717: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:07,717: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-03-31 09:28:07,718: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-03-31 09:28:07,719: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:07,719: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:07,720: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:07,720: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:07,928: DEBUG - + '[' True == True ']'
2023-03-31 09:28:07,928: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:07,929: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:07,929: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:07,930: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:07,932: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail
2023-03-31 09:28:07,935: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:07,936: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:07,937: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:08,121: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:08,124: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:08,126: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d
2023-03-31 09:28:08,126: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d
2023-03-31 09:28:08,129: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:08,129: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:08,133: DEBUG - + export domain
2023-03-31 09:28:08,135: DEBUG - ++ jq '.certificates."homeassistant.maindomain.tld".CA_type'
2023-03-31 09:28:08,136: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:08,138: DEBUG - ++ tr -d '"'
2023-03-31 09:28:08,261: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:08,262: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:08,264: DEBUG - + grep -q '^homeassistant.maindomain.tld$'
2023-03-31 09:28:08,266: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:08,267: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:08,269: DEBUG - firefly.domain2.tld
2023-03-31 09:28:08,270: DEBUG - home.domain2.tld
2023-03-31 09:28:08,271: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:08,271: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:08,272: DEBUG - webmail.domain2.tld
2023-03-31 09:28:08,273: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:08,273: DEBUG - energy.maindomain.tld
2023-03-31 09:28:08,274: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:08,275: DEBUG - home.maindomain.tld
2023-03-31 09:28:08,276: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:08,276: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:08,277: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:08,277: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:08,278: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:08,279: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:08,280: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:08,280: DEBUG - domain3.tld
2023-03-31 09:28:08,281: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:08,281: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:08,282: DEBUG - + grep -q '^homeassistant.maindomain.tld$'
2023-03-31 09:28:08,283: DEBUG - + export mail_enabled=True
2023-03-31 09:28:08,285: DEBUG - + mail_enabled=True
2023-03-31 09:28:08,286: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-03-31 09:28:08,287: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:08,287: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-03-31 09:28:08,288: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-03-31 09:28:08,288: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:08,289: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:08,290: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:08,290: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:08,534: DEBUG - + '[' True == True ']'
2023-03-31 09:28:08,535: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:08,536: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:08,536: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:08,536: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:08,538: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail
2023-03-31 09:28:08,542: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:08,542: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:08,543: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:08,725: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:08,728: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:08,729: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.d
2023-03-31 09:28:08,729: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.d
2023-03-31 09:28:08,732: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:08,733: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:08,736: DEBUG - + export domain
2023-03-31 09:28:08,739: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:08,742: DEBUG - ++ jq '.certificates."mqtt.maindomain.tld".CA_type'
2023-03-31 09:28:08,743: DEBUG - ++ tr -d '"'
2023-03-31 09:28:08,833: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:08,834: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:08,835: DEBUG - + grep -q '^mqtt.maindomain.tld$'
2023-03-31 09:28:08,838: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:08,839: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:08,841: DEBUG - firefly.domain2.tld
2023-03-31 09:28:08,841: DEBUG - home.domain2.tld
2023-03-31 09:28:08,842: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:08,842: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:08,843: DEBUG - webmail.domain2.tld
2023-03-31 09:28:08,843: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:08,844: DEBUG - energy.maindomain.tld
2023-03-31 09:28:08,844: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:08,845: DEBUG - home.maindomain.tld
2023-03-31 09:28:08,845: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:08,846: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:08,846: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:08,847: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:08,847: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:08,848: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:08,848: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:08,849: DEBUG - domain3.tld
2023-03-31 09:28:08,849: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:08,849: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:08,850: DEBUG - + grep -q '^mqtt.maindomain.tld$'
2023-03-31 09:28:08,850: DEBUG - + export mail_enabled=True
2023-03-31 09:28:08,851: DEBUG - + mail_enabled=True
2023-03-31 09:28:08,851: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.conf
2023-03-31 09:28:08,852: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:08,852: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.conf
2023-03-31 09:28:08,853: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.conf
2023-03-31 09:28:08,853: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:08,854: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:08,854: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:08,855: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:09,054: DEBUG - + '[' True == True ']'
2023-03-31 09:28:09,055: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:09,055: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:09,056: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:09,056: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:09,058: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail
2023-03-31 09:28:09,061: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:09,062: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:09,063: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:09,250: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:09,252: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:09,253: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d
2023-03-31 09:28:09,254: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d
2023-03-31 09:28:09,257: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:09,257: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:09,261: DEBUG - + export domain
2023-03-31 09:28:09,264: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:09,266: DEBUG - ++ jq '.certificates."nextcloud.maindomain.tld".CA_type'
2023-03-31 09:28:09,267: DEBUG - ++ tr -d '"'
2023-03-31 09:28:09,359: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:09,359: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:09,361: DEBUG - + grep -q '^nextcloud.maindomain.tld$'
2023-03-31 09:28:09,364: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:09,365: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:09,366: DEBUG - firefly.domain2.tld
2023-03-31 09:28:09,367: DEBUG - home.domain2.tld
2023-03-31 09:28:09,367: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:09,368: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:09,368: DEBUG - webmail.domain2.tld
2023-03-31 09:28:09,368: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:09,369: DEBUG - energy.maindomain.tld
2023-03-31 09:28:09,369: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:09,370: DEBUG - home.maindomain.tld
2023-03-31 09:28:09,370: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:09,371: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:09,371: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:09,372: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:09,373: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:09,373: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:09,374: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:09,374: DEBUG - domain3.tld
2023-03-31 09:28:09,375: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:09,376: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:09,376: DEBUG - + grep -q '^nextcloud.maindomain.tld$'
2023-03-31 09:28:09,377: DEBUG - + export mail_enabled=True
2023-03-31 09:28:09,378: DEBUG - + mail_enabled=True
2023-03-31 09:28:09,379: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-03-31 09:28:09,380: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:09,380: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-03-31 09:28:09,381: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-03-31 09:28:09,382: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:09,383: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:09,383: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:09,383: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:09,585: DEBUG - + '[' True == True ']'
2023-03-31 09:28:09,585: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:09,586: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:09,586: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:09,587: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:09,589: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail
2023-03-31 09:28:09,592: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:09,593: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:09,593: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:09,775: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:09,778: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:09,779: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d
2023-03-31 09:28:09,779: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d
2023-03-31 09:28:09,782: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:09,783: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:09,786: DEBUG - + export domain
2023-03-31 09:28:09,788: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:09,791: DEBUG - ++ jq '.certificates."nodered.maindomain.tld".CA_type'
2023-03-31 09:28:09,792: DEBUG - ++ tr -d '"'
2023-03-31 09:28:09,882: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:09,883: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:09,884: DEBUG - + grep -q '^nodered.maindomain.tld$'
2023-03-31 09:28:09,888: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:09,889: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:09,890: DEBUG - firefly.domain2.tld
2023-03-31 09:28:09,891: DEBUG - home.domain2.tld
2023-03-31 09:28:09,891: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:09,892: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:09,892: DEBUG - webmail.domain2.tld
2023-03-31 09:28:09,893: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:09,893: DEBUG - energy.maindomain.tld
2023-03-31 09:28:09,893: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:09,894: DEBUG - home.maindomain.tld
2023-03-31 09:28:09,894: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:09,895: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:09,897: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:09,897: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:09,898: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:09,898: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:09,898: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:09,899: DEBUG - domain3.tld
2023-03-31 09:28:09,900: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:09,900: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:09,900: DEBUG - + grep -q '^nodered.maindomain.tld$'
2023-03-31 09:28:09,901: DEBUG - + export mail_enabled=True
2023-03-31 09:28:09,901: DEBUG - + mail_enabled=True
2023-03-31 09:28:09,902: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf
2023-03-31 09:28:09,902: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:09,902: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf
2023-03-31 09:28:09,903: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf
2023-03-31 09:28:09,904: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:09,904: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:09,905: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:09,905: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:10,110: DEBUG - + '[' True == True ']'
2023-03-31 09:28:10,111: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:10,112: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:10,113: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:10,114: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:10,115: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail
2023-03-31 09:28:10,120: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:10,124: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:10,125: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:10,332: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:10,335: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:10,336: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d
2023-03-31 09:28:10,337: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d
2023-03-31 09:28:10,340: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:10,341: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:10,344: DEBUG - + export domain
2023-03-31 09:28:10,347: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:10,350: DEBUG - ++ jq '.certificates."owntracks.maindomain.tld".CA_type'
2023-03-31 09:28:10,350: DEBUG - ++ tr -d '"'
2023-03-31 09:28:10,451: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:10,452: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:10,453: DEBUG - + grep -q '^owntracks.maindomain.tld$'
2023-03-31 09:28:10,458: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:10,459: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:10,461: DEBUG - firefly.domain2.tld
2023-03-31 09:28:10,462: DEBUG - home.domain2.tld
2023-03-31 09:28:10,463: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:10,465: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:10,466: DEBUG - webmail.domain2.tld
2023-03-31 09:28:10,467: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:10,468: DEBUG - energy.maindomain.tld
2023-03-31 09:28:10,469: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:10,469: DEBUG - home.maindomain.tld
2023-03-31 09:28:10,470: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:10,470: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:10,471: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:10,472: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:10,472: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:10,472: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:10,473: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:10,473: DEBUG - domain3.tld
2023-03-31 09:28:10,474: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:10,475: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:10,476: DEBUG - + grep -q '^owntracks.maindomain.tld$'
2023-03-31 09:28:10,476: DEBUG - + export mail_enabled=True
2023-03-31 09:28:10,477: DEBUG - + mail_enabled=True
2023-03-31 09:28:10,477: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf
2023-03-31 09:28:10,478: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:10,478: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf
2023-03-31 09:28:10,479: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf
2023-03-31 09:28:10,479: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:10,480: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:10,480: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:10,481: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:10,681: DEBUG - + '[' True == True ']'
2023-03-31 09:28:10,681: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:10,682: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:10,683: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:10,683: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:10,685: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail
2023-03-31 09:28:10,689: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:10,689: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:10,690: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:10,874: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:10,877: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:10,878: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d
2023-03-31 09:28:10,878: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d
2023-03-31 09:28:10,881: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:10,882: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:10,885: DEBUG - + export domain
2023-03-31 09:28:10,888: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:10,890: DEBUG - ++ jq '.certificates."webmail.maindomain.tld".CA_type'
2023-03-31 09:28:10,890: DEBUG - ++ tr -d '"'
2023-03-31 09:28:10,981: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:10,982: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:10,982: DEBUG - + grep -q '^webmail.maindomain.tld$'
2023-03-31 09:28:10,986: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:10,987: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:10,988: DEBUG - firefly.domain2.tld
2023-03-31 09:28:10,988: DEBUG - home.domain2.tld
2023-03-31 09:28:10,989: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:10,989: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:10,990: DEBUG - webmail.domain2.tld
2023-03-31 09:28:10,990: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:10,992: DEBUG - energy.maindomain.tld
2023-03-31 09:28:10,992: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:10,993: DEBUG - home.maindomain.tld
2023-03-31 09:28:10,993: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:10,993: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:10,994: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:10,995: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:10,996: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:10,996: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:10,997: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:10,997: DEBUG - domain3.tld
2023-03-31 09:28:10,997: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:10,998: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:10,999: DEBUG - + grep -q '^webmail.maindomain.tld$'
2023-03-31 09:28:11,000: DEBUG - + export mail_enabled=True
2023-03-31 09:28:11,000: DEBUG - + mail_enabled=True
2023-03-31 09:28:11,001: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf
2023-03-31 09:28:11,001: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:11,001: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf
2023-03-31 09:28:11,002: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf
2023-03-31 09:28:11,002: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:11,003: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:11,003: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:11,003: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:11,203: DEBUG - + '[' True == True ']'
2023-03-31 09:28:11,203: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:11,204: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:11,204: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:11,205: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:11,207: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail
2023-03-31 09:28:11,210: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:11,211: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:11,211: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:11,394: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:11,396: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:11,397: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d
2023-03-31 09:28:11,398: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d
2023-03-31 09:28:11,400: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:11,401: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/
2023-03-31 09:28:11,404: DEBUG - + export domain
2023-03-31 09:28:11,406: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:11,408: DEBUG - ++ jq '.certificates."wikijs.maindomain.tld".CA_type'
2023-03-31 09:28:11,409: DEBUG - ++ tr -d '"'
2023-03-31 09:28:11,493: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:11,494: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:11,494: DEBUG - + grep -q '^wikijs.maindomain.tld$'
2023-03-31 09:28:11,498: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:11,499: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:11,500: DEBUG - firefly.domain2.tld
2023-03-31 09:28:11,501: DEBUG - home.domain2.tld
2023-03-31 09:28:11,501: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:11,501: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:11,502: DEBUG - webmail.domain2.tld
2023-03-31 09:28:11,503: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:11,504: DEBUG - energy.maindomain.tld
2023-03-31 09:28:11,504: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:11,505: DEBUG - home.maindomain.tld
2023-03-31 09:28:11,506: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:11,506: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:11,508: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:11,508: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:11,509: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:11,509: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:11,509: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:11,510: DEBUG - domain3.tld
2023-03-31 09:28:11,511: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:11,512: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:11,512: DEBUG - + grep -q '^wikijs.maindomain.tld$'
2023-03-31 09:28:11,513: DEBUG - + export mail_enabled=True
2023-03-31 09:28:11,513: DEBUG - + mail_enabled=True
2023-03-31 09:28:11,514: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-03-31 09:28:11,514: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:11,514: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-03-31 09:28:11,515: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-03-31 09:28:11,515: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:11,516: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:11,516: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:11,517: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:11,713: DEBUG - + '[' True == True ']'
2023-03-31 09:28:11,714: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:11,714: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:11,715: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:11,715: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:11,717: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail
2023-03-31 09:28:11,720: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:11,721: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:11,721: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:11,907: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d/yunohost_local.conf
2023-03-31 09:28:11,910: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:11,911: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.d
2023-03-31 09:28:11,911: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.d
2023-03-31 09:28:11,914: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail/
2023-03-31 09:28:11,915: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail/
2023-03-31 09:28:11,918: DEBUG - + export domain
2023-03-31 09:28:11,920: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:11,922: DEBUG - ++ jq '.certificates."domain3.tld".CA_type'
2023-03-31 09:28:11,922: DEBUG - ++ tr -d '"'
2023-03-31 09:28:12,013: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:12,014: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:12,015: DEBUG - + grep -q '^domain3.tld$'
2023-03-31 09:28:12,019: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:12,020: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:12,025: DEBUG - firefly.domain2.tld
2023-03-31 09:28:12,026: DEBUG - home.domain2.tld
2023-03-31 09:28:12,026: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:12,027: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:12,027: DEBUG - webmail.domain2.tld
2023-03-31 09:28:12,029: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:12,029: DEBUG - energy.maindomain.tld
2023-03-31 09:28:12,030: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:12,030: DEBUG - home.maindomain.tld
2023-03-31 09:28:12,031: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:12,031: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:12,033: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:12,033: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:12,033: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:12,034: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:12,034: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:12,035: DEBUG - domain3.tld
2023-03-31 09:28:12,035: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:12,036: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:12,036: DEBUG - + grep -q '^domain3.tld$'
2023-03-31 09:28:12,036: DEBUG - + export mail_enabled=True
2023-03-31 09:28:12,037: DEBUG - + mail_enabled=True
2023-03-31 09:28:12,037: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.conf
2023-03-31 09:28:12,037: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:12,038: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.conf
2023-03-31 09:28:12,038: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.conf
2023-03-31 09:28:12,039: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:12,039: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:12,040: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:12,040: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:12,234: DEBUG - + '[' True == True ']'
2023-03-31 09:28:12,235: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:12,235: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:12,235: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:12,236: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:12,238: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail
2023-03-31 09:28:12,241: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:12,242: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:12,242: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:12,424: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.d/yunohost_local.conf
2023-03-31 09:28:12,427: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:12,427: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.d
2023-03-31 09:28:12,428: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.d
2023-03-31 09:28:12,431: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/
2023-03-31 09:28:12,431: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/
2023-03-31 09:28:12,435: DEBUG - + export domain
2023-03-31 09:28:12,437: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:12,439: DEBUG - ++ jq '.certificates."homeassistant.domain3.tld".CA_type'
2023-03-31 09:28:12,440: DEBUG - ++ tr -d '"'
2023-03-31 09:28:12,523: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:12,523: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:12,525: DEBUG - + grep -q '^homeassistant.domain3.tld$'
2023-03-31 09:28:12,529: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:12,530: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:12,531: DEBUG - firefly.domain2.tld
2023-03-31 09:28:12,532: DEBUG - home.domain2.tld
2023-03-31 09:28:12,532: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:12,533: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:12,533: DEBUG - webmail.domain2.tld
2023-03-31 09:28:12,533: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:12,534: DEBUG - energy.maindomain.tld
2023-03-31 09:28:12,534: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:12,535: DEBUG - home.maindomain.tld
2023-03-31 09:28:12,535: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:12,536: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:12,536: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:12,536: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:12,537: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:12,537: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:12,538: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:12,538: DEBUG - domain3.tld
2023-03-31 09:28:12,539: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:12,539: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:12,540: DEBUG - + grep -q '^homeassistant.domain3.tld$'
2023-03-31 09:28:12,540: DEBUG - + export mail_enabled=True
2023-03-31 09:28:12,541: DEBUG - + mail_enabled=True
2023-03-31 09:28:12,541: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.conf
2023-03-31 09:28:12,542: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:12,542: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.conf
2023-03-31 09:28:12,543: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.conf
2023-03-31 09:28:12,543: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:12,544: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:12,544: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:12,544: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:12,743: DEBUG - + '[' True == True ']'
2023-03-31 09:28:12,744: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:12,744: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:12,745: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:12,745: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:12,747: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail
2023-03-31 09:28:12,751: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:12,752: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:12,752: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:12,935: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.d/yunohost_local.conf
2023-03-31 09:28:12,937: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:12,938: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.d
2023-03-31 09:28:12,939: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.d
2023-03-31 09:28:12,942: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/
2023-03-31 09:28:12,943: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/
2023-03-31 09:28:12,946: DEBUG - + export domain
2023-03-31 09:28:12,949: DEBUG - ++ echo '{"certificates":' '{"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"firefly.domain2.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3647, '"style":' '"warning",' '"summary":' '"selfsigned"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 57, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 53, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 74, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 52, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 84, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 83, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain3.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 88, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-31 09:28:12,951: DEBUG - ++ jq '.certificates."wikijs.domain3.tld".CA_type'
2023-03-31 09:28:12,952: DEBUG - ++ tr -d '"'
2023-03-31 09:28:13,043: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-31 09:28:13,044: DEBUG - + domain_cert_ca=letsencrypt
2023-03-31 09:28:13,045: DEBUG - + grep -q '^wikijs.domain3.tld$'
2023-03-31 09:28:13,048: DEBUG - + export xmpp_enabled=False
2023-03-31 09:28:13,048: DEBUG - + xmpp_enabled=False
2023-03-31 09:28:13,050: DEBUG - firefly.domain2.tld
2023-03-31 09:28:13,050: DEBUG - home.domain2.tld
2023-03-31 09:28:13,051: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:13,051: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:13,052: DEBUG - webmail.domain2.tld
2023-03-31 09:28:13,052: DEBUG - wikijs.domain2.tld
2023-03-31 09:28:13,052: DEBUG - energy.maindomain.tld
2023-03-31 09:28:13,053: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:13,053: DEBUG - home.maindomain.tld
2023-03-31 09:28:13,054: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:13,054: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:13,055: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:13,055: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:13,056: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:13,056: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:13,056: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:13,057: DEBUG - domain3.tld
2023-03-31 09:28:13,057: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:13,058: DEBUG - wikijs.domain3.tld'
2023-03-31 09:28:13,058: DEBUG - + grep -q '^wikijs.domain3.tld$'
2023-03-31 09:28:13,059: DEBUG - + export mail_enabled=True
2023-03-31 09:28:13,059: DEBUG - + mail_enabled=True
2023-03-31 09:28:13,060: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.conf
2023-03-31 09:28:13,060: DEBUG - + local template_path=server.tpl.conf
2023-03-31 09:28:13,061: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.conf
2023-03-31 09:28:13,061: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.conf
2023-03-31 09:28:13,062: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:13,062: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:13,063: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:13,063: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:13,260: DEBUG - + '[' True == True ']'
2023-03-31 09:28:13,261: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:13,262: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-31 09:28:13,262: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:13,263: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail//config-v1.1.xml
2023-03-31 09:28:13,264: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail
2023-03-31 09:28:13,268: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:13,268: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:13,269: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:13,454: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.d/yunohost_local.conf
2023-03-31 09:28:13,458: DEBUG - ++ yunohost settings get security.webadmin.webadmin_allowlist_enabled
2023-03-31 09:28:13,459: DEBUG - ++ int_to_bool
2023-03-31 09:28:13,460: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:28:14,113: DEBUG - + export webadmin_allowlist_enabled=False
2023-03-31 09:28:14,113: DEBUG - + webadmin_allowlist_enabled=False
2023-03-31 09:28:14,114: DEBUG - + '[' False == True ']'
2023-03-31 09:28:14,115: DEBUG - + ynh_render_template yunohost_admin.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-31 09:28:14,115: DEBUG - + local template_path=yunohost_admin.conf.inc
2023-03-31 09:28:14,115: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-31 09:28:14,116: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-31 09:28:14,118: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:14,121: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:14,122: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:14,122: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:14,309: DEBUG - + ynh_render_template yunohost_api.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-31 09:28:14,309: DEBUG - + local template_path=yunohost_api.conf.inc
2023-03-31 09:28:14,310: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-31 09:28:14,310: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-31 09:28:14,312: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:14,318: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:14,319: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:14,319: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:14,508: DEBUG - + ynh_render_template yunohost_admin.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-31 09:28:14,508: DEBUG - + local template_path=yunohost_admin.conf
2023-03-31 09:28:14,509: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-31 09:28:14,509: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-31 09:28:14,512: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-31 09:28:14,515: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:14,516: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:14,516: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:14,706: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/
2023-03-31 09:28:14,711: DEBUG - + cp redirect_to_admin.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/
2023-03-31 09:28:14,719: DEBUG - ++ ls -1 /etc/nginx/conf.d
2023-03-31 09:28:14,720: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*\.conf$/ { print $1 }'
2023-03-31 09:28:14,732: DEBUG - + conf_files='energy.maindomain.tld.conf
2023-03-31 09:28:14,733: DEBUG - energy.domain2.tld.conf
2023-03-31 09:28:14,734: DEBUG - firefly.domain2.tld.conf
2023-03-31 09:28:14,735: DEBUG - grocy.maindomain.tld.conf
2023-03-31 09:28:14,735: DEBUG - homeassistant.domain3.tld.conf
2023-03-31 09:28:14,736: DEBUG - homeassistant.maindomain.tld.conf
2023-03-31 09:28:14,737: DEBUG - homeassistant.domain2.tld.conf
2023-03-31 09:28:14,737: DEBUG - home.maindomain.tld.conf
2023-03-31 09:28:14,737: DEBUG - home.domain2.tld.conf
2023-03-31 09:28:14,738: DEBUG - domain3.tld.conf
2023-03-31 09:28:14,738: DEBUG - maindomain.tld.conf
2023-03-31 09:28:14,739: DEBUG - domain2.tld.conf
2023-03-31 09:28:14,739: DEBUG - mqtt.maindomain.tld.conf
2023-03-31 09:28:14,740: DEBUG - nextcloud.maindomain.tld.conf
2023-03-31 09:28:14,740: DEBUG - nextcloud.domain2.tld.conf
2023-03-31 09:28:14,741: DEBUG - nodered.maindomain.tld.conf
2023-03-31 09:28:14,741: DEBUG - owntracks.maindomain.tld.conf
2023-03-31 09:28:14,742: DEBUG - webmail.maindomain.tld.conf
2023-03-31 09:28:14,742: DEBUG - webmail.domain2.tld.conf
2023-03-31 09:28:14,743: DEBUG - wikijs.domain3.tld.conf
2023-03-31 09:28:14,743: DEBUG - wikijs.maindomain.tld.conf
2023-03-31 09:28:14,744: DEBUG - wikijs.domain2.tld.conf'
2023-03-31 09:28:14,744: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,745: DEBUG - + domain=energy.maindomain.tld
2023-03-31 09:28:14,745: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ energy.maindomain.tld ]]
2023-03-31 09:28:14,746: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,747: DEBUG - + domain=energy.domain2.tld
2023-03-31 09:28:14,747: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ energy.domain2.tld ]]
2023-03-31 09:28:14,748: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,748: DEBUG - + domain=firefly.domain2.tld
2023-03-31 09:28:14,749: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ firefly.domain2.tld ]]
2023-03-31 09:28:14,750: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,750: DEBUG - + domain=grocy.maindomain.tld
2023-03-31 09:28:14,750: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ grocy.maindomain.tld ]]
2023-03-31 09:28:14,751: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,752: DEBUG - + domain=homeassistant.domain3.tld
2023-03-31 09:28:14,752: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.domain3.tld ]]
2023-03-31 09:28:14,753: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,753: DEBUG - + domain=homeassistant.maindomain.tld
2023-03-31 09:28:14,754: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.maindomain.tld ]]
2023-03-31 09:28:14,755: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,755: DEBUG - + domain=homeassistant.domain2.tld
2023-03-31 09:28:14,756: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.domain2.tld ]]
2023-03-31 09:28:14,756: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,757: DEBUG - + domain=home.maindomain.tld
2023-03-31 09:28:14,757: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ home.maindomain.tld ]]
2023-03-31 09:28:14,758: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,758: DEBUG - + domain=home.domain2.tld
2023-03-31 09:28:14,759: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ home.domain2.tld ]]
2023-03-31 09:28:14,759: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,760: DEBUG - + domain=domain3.tld
2023-03-31 09:28:14,760: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ domain3.tld ]]
2023-03-31 09:28:14,761: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,761: DEBUG - + domain=maindomain.tld
2023-03-31 09:28:14,762: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ maindomain.tld ]]
2023-03-31 09:28:14,762: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,763: DEBUG - + domain=domain2.tld
2023-03-31 09:28:14,763: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ domain2.tld ]]
2023-03-31 09:28:14,764: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,765: DEBUG - + domain=mqtt.maindomain.tld
2023-03-31 09:28:14,765: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ mqtt.maindomain.tld ]]
2023-03-31 09:28:14,766: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,766: DEBUG - + domain=nextcloud.maindomain.tld
2023-03-31 09:28:14,767: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nextcloud.maindomain.tld ]]
2023-03-31 09:28:14,768: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,768: DEBUG - + domain=nextcloud.domain2.tld
2023-03-31 09:28:14,769: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nextcloud.domain2.tld ]]
2023-03-31 09:28:14,771: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,771: DEBUG - + domain=nodered.maindomain.tld
2023-03-31 09:28:14,772: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nodered.maindomain.tld ]]
2023-03-31 09:28:14,772: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,773: DEBUG - + domain=owntracks.maindomain.tld
2023-03-31 09:28:14,773: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ owntracks.maindomain.tld ]]
2023-03-31 09:28:14,774: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,774: DEBUG - + domain=webmail.maindomain.tld
2023-03-31 09:28:14,775: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ webmail.maindomain.tld ]]
2023-03-31 09:28:14,776: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,776: DEBUG - + domain=webmail.domain2.tld
2023-03-31 09:28:14,776: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ webmail.domain2.tld ]]
2023-03-31 09:28:14,777: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,777: DEBUG - + domain=wikijs.domain3.tld
2023-03-31 09:28:14,778: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.domain3.tld ]]
2023-03-31 09:28:14,779: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,779: DEBUG - + domain=wikijs.maindomain.tld
2023-03-31 09:28:14,780: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.maindomain.tld ]]
2023-03-31 09:28:14,780: DEBUG - + for file in $conf_files
2023-03-31 09:28:14,781: DEBUG - + domain=wikijs.domain2.tld
2023-03-31 09:28:14,781: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.domain2.tld ]]
2023-03-31 09:28:14,782: DEBUG - ++ ls -1 /var/www/.well-known/energy.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/energy.domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/firefly.domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/home.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/home.domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/domain3.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/webmail.domain2.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/config-v1.1.xml /var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,783: DEBUG - + autoconfig_files='/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,784: DEBUG - /var/www/.well-known/energy.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,784: DEBUG - /var/www/.well-known/firefly.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,785: DEBUG - /var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,785: DEBUG - /var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,786: DEBUG - /var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,786: DEBUG - /var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,787: DEBUG - /var/www/.well-known/home.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,787: DEBUG - /var/www/.well-known/home.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,787: DEBUG - /var/www/.well-known/domain3.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,788: DEBUG - /var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,788: DEBUG - /var/www/.well-known/domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,789: DEBUG - /var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,789: DEBUG - /var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,789: DEBUG - /var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,790: DEBUG - /var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,790: DEBUG - /var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,791: DEBUG - /var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,791: DEBUG - /var/www/.well-known/webmail.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,792: DEBUG - /var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,792: DEBUG - /var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,793: DEBUG - /var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:14,793: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,794: DEBUG - ++++ dirname /var/www/.well-known/energy.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,794: DEBUG - +++ readlink -f /var/www/.well-known/energy.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,795: DEBUG - ++ basename /var/www/.well-known/energy.maindomain.tld
2023-03-31 09:28:14,796: DEBUG - + domain=energy.maindomain.tld
2023-03-31 09:28:14,796: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ energy.maindomain.tld ]]
2023-03-31 09:28:14,796: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,797: DEBUG - ++++ dirname /var/www/.well-known/energy.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,797: DEBUG - +++ readlink -f /var/www/.well-known/energy.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,798: DEBUG - ++ basename /var/www/.well-known/energy.domain2.tld
2023-03-31 09:28:14,798: DEBUG - + domain=energy.domain2.tld
2023-03-31 09:28:14,799: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ energy.domain2.tld ]]
2023-03-31 09:28:14,799: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,800: DEBUG - ++++ dirname /var/www/.well-known/firefly.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,800: DEBUG - +++ readlink -f /var/www/.well-known/firefly.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,801: DEBUG - ++ basename /var/www/.well-known/firefly.domain2.tld
2023-03-31 09:28:14,801: DEBUG - + domain=firefly.domain2.tld
2023-03-31 09:28:14,801: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ firefly.domain2.tld ]]
2023-03-31 09:28:14,802: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,803: DEBUG - ++++ dirname /var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,803: DEBUG - +++ readlink -f /var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,804: DEBUG - ++ basename /var/www/.well-known/grocy.maindomain.tld
2023-03-31 09:28:14,804: DEBUG - + domain=grocy.maindomain.tld
2023-03-31 09:28:14,804: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ grocy.maindomain.tld ]]
2023-03-31 09:28:14,805: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,806: DEBUG - ++++ dirname /var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,806: DEBUG - +++ readlink -f /var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/../..
2023-03-31 09:28:14,807: DEBUG - ++ basename /var/www/.well-known/homeassistant.domain3.tld
2023-03-31 09:28:14,807: DEBUG - + domain=homeassistant.domain3.tld
2023-03-31 09:28:14,808: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.domain3.tld ]]
2023-03-31 09:28:14,808: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,809: DEBUG - ++++ dirname /var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,811: DEBUG - +++ readlink -f /var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,814: DEBUG - ++ basename /var/www/.well-known/homeassistant.maindomain.tld
2023-03-31 09:28:14,817: DEBUG - + domain=homeassistant.maindomain.tld
2023-03-31 09:28:14,818: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.maindomain.tld ]]
2023-03-31 09:28:14,819: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,820: DEBUG - ++++ dirname /var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,823: DEBUG - +++ readlink -f /var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,826: DEBUG - ++ basename /var/www/.well-known/homeassistant.domain2.tld
2023-03-31 09:28:14,829: DEBUG - + domain=homeassistant.domain2.tld
2023-03-31 09:28:14,830: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.domain2.tld ]]
2023-03-31 09:28:14,831: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,832: DEBUG - ++++ dirname /var/www/.well-known/home.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,835: DEBUG - +++ readlink -f /var/www/.well-known/home.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,838: DEBUG - ++ basename /var/www/.well-known/home.maindomain.tld
2023-03-31 09:28:14,842: DEBUG - + domain=home.maindomain.tld
2023-03-31 09:28:14,842: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ home.maindomain.tld ]]
2023-03-31 09:28:14,843: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,844: DEBUG - ++++ dirname /var/www/.well-known/home.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,848: DEBUG - +++ readlink -f /var/www/.well-known/home.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,850: DEBUG - ++ basename /var/www/.well-known/home.domain2.tld
2023-03-31 09:28:14,854: DEBUG - + domain=home.domain2.tld
2023-03-31 09:28:14,855: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ home.domain2.tld ]]
2023-03-31 09:28:14,856: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,857: DEBUG - ++++ dirname /var/www/.well-known/domain3.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,860: DEBUG - +++ readlink -f /var/www/.well-known/domain3.tld/autoconfig/mail/../..
2023-03-31 09:28:14,862: DEBUG - ++ basename /var/www/.well-known/domain3.tld
2023-03-31 09:28:14,866: DEBUG - + domain=domain3.tld
2023-03-31 09:28:14,867: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ domain3.tld ]]
2023-03-31 09:28:14,868: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,869: DEBUG - ++++ dirname /var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,872: DEBUG - +++ readlink -f /var/www/.well-known/maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,874: DEBUG - ++ basename /var/www/.well-known/maindomain.tld
2023-03-31 09:28:14,878: DEBUG - + domain=maindomain.tld
2023-03-31 09:28:14,879: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ maindomain.tld ]]
2023-03-31 09:28:14,880: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,881: DEBUG - ++++ dirname /var/www/.well-known/domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,884: DEBUG - +++ readlink -f /var/www/.well-known/domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,887: DEBUG - ++ basename /var/www/.well-known/domain2.tld
2023-03-31 09:28:14,889: DEBUG - + domain=domain2.tld
2023-03-31 09:28:14,890: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ domain2.tld ]]
2023-03-31 09:28:14,891: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,893: DEBUG - ++++ dirname /var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,896: DEBUG - +++ readlink -f /var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,899: DEBUG - ++ basename /var/www/.well-known/mqtt.maindomain.tld
2023-03-31 09:28:14,901: DEBUG - + domain=mqtt.maindomain.tld
2023-03-31 09:28:14,902: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ mqtt.maindomain.tld ]]
2023-03-31 09:28:14,903: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,905: DEBUG - ++++ dirname /var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,908: DEBUG - +++ readlink -f /var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,910: DEBUG - ++ basename /var/www/.well-known/nextcloud.maindomain.tld
2023-03-31 09:28:14,913: DEBUG - + domain=nextcloud.maindomain.tld
2023-03-31 09:28:14,914: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nextcloud.maindomain.tld ]]
2023-03-31 09:28:14,915: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,917: DEBUG - ++++ dirname /var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,919: DEBUG - +++ readlink -f /var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,922: DEBUG - ++ basename /var/www/.well-known/nextcloud.domain2.tld
2023-03-31 09:28:14,925: DEBUG - + domain=nextcloud.domain2.tld
2023-03-31 09:28:14,926: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nextcloud.domain2.tld ]]
2023-03-31 09:28:14,926: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,929: DEBUG - ++++ dirname /var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,931: DEBUG - +++ readlink -f /var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,934: DEBUG - ++ basename /var/www/.well-known/nodered.maindomain.tld
2023-03-31 09:28:14,937: DEBUG - + domain=nodered.maindomain.tld
2023-03-31 09:28:14,937: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nodered.maindomain.tld ]]
2023-03-31 09:28:14,938: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,940: DEBUG - ++++ dirname /var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,943: DEBUG - +++ readlink -f /var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,946: DEBUG - ++ basename /var/www/.well-known/owntracks.maindomain.tld
2023-03-31 09:28:14,949: DEBUG - + domain=owntracks.maindomain.tld
2023-03-31 09:28:14,949: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ owntracks.maindomain.tld ]]
2023-03-31 09:28:14,950: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,952: DEBUG - ++++ dirname /var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,955: DEBUG - +++ readlink -f /var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,958: DEBUG - ++ basename /var/www/.well-known/webmail.maindomain.tld
2023-03-31 09:28:14,960: DEBUG - + domain=webmail.maindomain.tld
2023-03-31 09:28:14,961: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ webmail.maindomain.tld ]]
2023-03-31 09:28:14,962: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,964: DEBUG - ++++ dirname /var/www/.well-known/webmail.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,967: DEBUG - +++ readlink -f /var/www/.well-known/webmail.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:14,970: DEBUG - ++ basename /var/www/.well-known/webmail.domain2.tld
2023-03-31 09:28:14,972: DEBUG - + domain=webmail.domain2.tld
2023-03-31 09:28:14,973: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ webmail.domain2.tld ]]
2023-03-31 09:28:14,974: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,976: DEBUG - ++++ dirname /var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,979: DEBUG - +++ readlink -f /var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/../..
2023-03-31 09:28:14,982: DEBUG - ++ basename /var/www/.well-known/wikijs.domain3.tld
2023-03-31 09:28:14,984: DEBUG - + domain=wikijs.domain3.tld
2023-03-31 09:28:14,985: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.domain3.tld ]]
2023-03-31 09:28:14,986: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:14,988: DEBUG - ++++ dirname /var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:14,991: DEBUG - +++ readlink -f /var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/../..
2023-03-31 09:28:14,994: DEBUG - ++ basename /var/www/.well-known/wikijs.maindomain.tld
2023-03-31 09:28:14,996: DEBUG - + domain=wikijs.maindomain.tld
2023-03-31 09:28:14,997: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.maindomain.tld ]]
2023-03-31 09:28:14,998: DEBUG - + for file in $autoconfig_files
2023-03-31 09:28:15,000: DEBUG - ++++ dirname /var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/config-v1.1.xml
2023-03-31 09:28:15,003: DEBUG - +++ readlink -f /var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/../..
2023-03-31 09:28:15,005: DEBUG - ++ basename /var/www/.well-known/wikijs.domain2.tld
2023-03-31 09:28:15,008: DEBUG - + domain=wikijs.domain2.tld
2023-03-31 09:28:15,009: DEBUG - + [[ domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.domain2.tld ]]
2023-03-31 09:28:15,010: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled
2023-03-31 09:28:15,012: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled/default
2023-03-31 09:28:16,016: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./19-postfix" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/postfix 7>&1']'
2023-03-31 09:28:16,034: DEBUG - + set -e
2023-03-31 09:28:16,035: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:16,036: DEBUG - +++ set +o
2023-03-31 09:28:16,036: DEBUG - +++ grep xtrace
2023-03-31 09:28:16,040: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:16,040: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:16,081: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/postfix
2023-03-31 09:28:16,082: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/postfix
2023-03-31 09:28:16,082: DEBUG - + cd /usr/share/yunohost/conf/postfix
2023-03-31 09:28:16,083: DEBUG - + postfix_dir=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-31 09:28:16,083: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-31 09:28:16,085: DEBUG - + default_dir=/var/cache/yunohost/regenconf/pending/postfix/etc/default/
2023-03-31 09:28:16,086: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/default/
2023-03-31 09:28:16,089: DEBUG - + cp plain/header_checks plain/ldap-accounts.cf plain/ldap-aliases.cf plain/ldap-domains.cf plain/ldap-groups.cf plain/master.cf plain/sender_canonical plain/smtp_reply_filter /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-31 09:28:16,095: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-31 09:28:16,097: DEBUG - + main_domain=maindomain.tld
2023-03-31 09:28:16,098: DEBUG - ++ yunohost settings get security.postfix.postfix_compatibility
2023-03-31 09:28:16,749: DEBUG - + export compatibility=intermediate
2023-03-31 09:28:16,750: DEBUG - + compatibility=intermediate
2023-03-31 09:28:16,750: DEBUG - + export relay_port=
2023-03-31 09:28:16,751: DEBUG - + relay_port=
2023-03-31 09:28:16,752: DEBUG - + export relay_user=
2023-03-31 09:28:16,752: DEBUG - + relay_user=
2023-03-31 09:28:16,753: DEBUG - + export relay_host=
2023-03-31 09:28:16,754: DEBUG - + relay_host=
2023-03-31 09:28:16,754: DEBUG - ++ yunohost settings get email.smtp.smtp_relay_enabled
2023-03-31 09:28:16,755: DEBUG - ++ int_to_bool
2023-03-31 09:28:16,756: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:28:17,441: DEBUG - + export relay_enabled=True
2023-03-31 09:28:17,442: DEBUG - + relay_enabled=True
2023-03-31 09:28:17,443: DEBUG - + '[' True == True ']'
2023-03-31 09:28:17,443: DEBUG - ++ yunohost settings get email.smtp.smtp_relay_host
2023-03-31 09:28:18,107: DEBUG - + relay_host=smtp-relay.sendinblue.com
2023-03-31 09:28:18,109: DEBUG - ++ yunohost settings get email.smtp.smtp_relay_port
2023-03-31 09:28:18,766: DEBUG - + relay_port=587
2023-03-31 09:28:18,767: DEBUG - ++ yunohost settings get email.smtp.smtp_relay_user
2023-03-31 09:28:19,417: DEBUG - + relay_user=rehn.kirk@gmail.com
2023-03-31 09:28:19,418: DEBUG - ++ yunohost settings get email.smtp.smtp_relay_password
2023-03-31 09:28:20,071: DEBUG - + relay_password=**********
2023-03-31 09:28:20,071: DEBUG - + touch /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sasl_passwd
2023-03-31 09:28:20,073: DEBUG - + chmod 750 /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sasl_passwd
2023-03-31 09:28:20,076: DEBUG - + chown postfix /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-31 09:28:20,084: DEBUG - + chown postfix /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sasl_passwd
2023-03-31 09:28:20,087: DEBUG - + cat
2023-03-31 09:28:20,090: DEBUG - + export main_domain
2023-03-31 09:28:20,092: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-31 09:28:20,093: DEBUG - ++ jq -r '.domains[]'
2023-03-31 09:28:20,094: DEBUG - ++ tr '\n' ' '
2023-03-31 09:28:20,906: DEBUG - + export 'domain_list=energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld '
2023-03-31 09:28:20,907: DEBUG - + domain_list='energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld '
2023-03-31 09:28:20,908: DEBUG - + ynh_render_template main.cf /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-31 09:28:20,909: DEBUG - + local template_path=main.cf
2023-03-31 09:28:20,909: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-31 09:28:20,909: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-31 09:28:20,910: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-31 09:28:20,914: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:20,914: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:20,915: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:21,105: DEBUG - + ynh_render_template sni /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-31 09:28:21,106: DEBUG - + local template_path=sni
2023-03-31 09:28:21,106: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-31 09:28:21,107: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-31 09:28:21,109: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-31 09:28:21,112: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:21,113: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:21,114: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:21,296: DEBUG - + cat postsrsd
2023-03-31 09:28:21,297: DEBUG - + sed 's/{{ main_domain }}/maindomain.tld/g'
2023-03-31 09:28:21,298: DEBUG - + sed 's/{{ domain_list }}/energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld /g'
2023-03-31 09:28:21,303: DEBUG - ++ yunohost settings get email.smtp.smtp_allow_ipv6
2023-03-31 09:28:21,304: DEBUG - ++ int_to_bool
2023-03-31 09:28:21,305: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:28:21,959: DEBUG - + ipv6=True
2023-03-31 09:28:21,960: DEBUG - + '[' True == False ']'
2023-03-31 09:28:21,960: DEBUG - + '[' '!' -f /proc/net/if_inet6 ']'
2023-03-31 09:28:22,964: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./25-dovecot" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/dovecot 7>&1']'
2023-03-31 09:28:22,981: DEBUG - + set -e
2023-03-31 09:28:22,982: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:22,984: DEBUG - +++ set +o
2023-03-31 09:28:22,985: DEBUG - +++ grep xtrace
2023-03-31 09:28:22,988: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:22,988: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:23,029: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/dovecot
2023-03-31 09:28:23,029: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/dovecot
2023-03-31 09:28:23,030: DEBUG - + cd /usr/share/yunohost/conf/dovecot
2023-03-31 09:28:23,031: DEBUG - + dovecot_dir=/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot
2023-03-31 09:28:23,031: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/global_script
2023-03-31 09:28:23,033: DEBUG - + cp dovecot-ldap.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot-ldap.conf
2023-03-31 09:28:23,037: DEBUG - + cp dovecot.sieve /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/global_script/dovecot.sieve
2023-03-31 09:28:23,043: DEBUG - ++ yunohost settings get email.pop3.pop3_enabled
2023-03-31 09:28:23,044: DEBUG - ++ int_to_bool
2023-03-31 09:28:23,045: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-31 09:28:23,698: DEBUG - + export pop3_enabled=False
2023-03-31 09:28:23,699: DEBUG - + pop3_enabled=False
2023-03-31 09:28:23,699: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-31 09:28:23,702: DEBUG - + export main_domain=maindomain.tld
2023-03-31 09:28:23,703: DEBUG - + main_domain=maindomain.tld
2023-03-31 09:28:23,705: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-31 09:28:23,705: DEBUG - ++ tr '\n' ' '
2023-03-31 09:28:23,706: DEBUG - ++ jq -r '.domains[]'
2023-03-31 09:28:24,516: DEBUG - + export 'domain_list=energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld '
2023-03-31 09:28:24,517: DEBUG - + domain_list='energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld '
2023-03-31 09:28:24,517: DEBUG - + ynh_render_template dovecot.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf
2023-03-31 09:28:24,518: DEBUG - + local template_path=dovecot.conf
2023-03-31 09:28:24,518: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf
2023-03-31 09:28:24,519: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf
2023-03-31 09:28:24,519: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot
2023-03-31 09:28:24,523: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:24,523: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:24,524: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:24,717: DEBUG - + '[' '!' -f /proc/net/if_inet6 ']'
2023-03-31 09:28:24,718: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d
2023-03-31 09:28:24,721: DEBUG - + cp pre-ext.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d
2023-03-31 09:28:24,725: DEBUG - + cp post-ext.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d
2023-03-31 09:28:25,729: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./31-rspamd" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/rspamd 7>&1']'
2023-03-31 09:28:25,746: DEBUG - + set -e
2023-03-31 09:28:25,747: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/rspamd
2023-03-31 09:28:25,747: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/rspamd
2023-03-31 09:28:25,748: DEBUG - + cd /usr/share/yunohost/conf/rspamd
2023-03-31 09:28:25,748: DEBUG - + install -D -m 644 metrics.local.conf /var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/metrics.conf
2023-03-31 09:28:25,752: DEBUG - + install -D -m 644 dkim_signing.conf /var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/dkim_signing.conf
2023-03-31 09:28:25,756: DEBUG - + install -D -m 644 rspamd.sieve /var/cache/yunohost/regenconf/pending/rspamd/etc/dovecot/global_script/rspamd.sieve
2023-03-31 09:28:26,760: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./34-mysql" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/mysql 7>&1']'
2023-03-31 09:28:26,781: DEBUG - + set -e
2023-03-31 09:28:26,782: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:26,784: DEBUG - +++ set +o
2023-03-31 09:28:26,784: DEBUG - +++ grep xtrace
2023-03-31 09:28:26,788: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:26,789: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:26,830: DEBUG - + dpkg --list
2023-03-31 09:28:26,831: DEBUG - + grep -q 'ii *mariadb-server '
2023-03-31 09:28:26,871: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/mysql
2023-03-31 09:28:26,872: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/mysql
2023-03-31 09:28:27,880: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./35-postgresql" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/postgresql 7>&1']'
2023-03-31 09:28:27,917: DEBUG - + set -e
2023-03-31 09:28:27,919: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:27,921: DEBUG - +++ set +o
2023-03-31 09:28:27,922: DEBUG - +++ grep xtrace
2023-03-31 09:28:27,927: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:27,929: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:28,005: DEBUG - + dpkg --list
2023-03-31 09:28:28,006: DEBUG - + grep -q 'ii *postgresql-13 '
2023-03-31 09:28:28,048: DEBUG - + '[' '!' -e /etc/postgresql/13 ']'
2023-03-31 09:28:28,049: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/postgresql
2023-03-31 09:28:28,049: DEBUG - + return 0
2023-03-31 09:28:29,053: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./36-redis" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/redis 7>&1']'
2023-03-31 09:28:29,073: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/redis
2023-03-31 09:28:29,074: DEBUG - + :
2023-03-31 09:28:30,077: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./37-mdns" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/mdns 7>&1']'
2023-03-31 09:28:30,097: DEBUG - + set -e
2023-03-31 09:28:30,099: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/mdns
2023-03-31 09:28:30,099: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/mdns
2023-03-31 09:28:30,100: DEBUG - + cd /usr/share/yunohost/conf/mdns
2023-03-31 09:28:30,100: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/mdns/etc/systemd/system/
2023-03-31 09:28:30,105: DEBUG - + cp yunomdns.service /var/cache/yunohost/regenconf/pending/mdns/etc/systemd/system/
2023-03-31 09:28:30,113: DEBUG - + getent passwd mdns
2023-03-31 09:28:30,121: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/mdns/etc/yunohost
2023-03-31 09:28:30,124: DEBUG - + _generate_config
2023-03-31 09:28:30,125: DEBUG - + echo domains:
2023-03-31 09:28:30,127: DEBUG - + tr ' ' '\n'
2023-03-31 09:28:30,128: DEBUG - + grep -q --line-regexp yunohost.local
2023-03-31 09:28:30,131: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,131: DEBUG - + [[ domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,132: DEBUG - + [[ domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,132: DEBUG - + continue
2023-03-31 09:28:30,133: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,134: DEBUG - + [[ energy.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,134: DEBUG - + [[ energy.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,135: DEBUG - + continue
2023-03-31 09:28:30,135: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,136: DEBUG - + [[ firefly.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,136: DEBUG - + [[ firefly.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,137: DEBUG - + continue
2023-03-31 09:28:30,137: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,138: DEBUG - + [[ home.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,138: DEBUG - + [[ home.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,139: DEBUG - + continue
2023-03-31 09:28:30,139: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,140: DEBUG - + [[ homeassistant.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,140: DEBUG - + [[ homeassistant.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,141: DEBUG - + continue
2023-03-31 09:28:30,141: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,141: DEBUG - + [[ nextcloud.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,142: DEBUG - + [[ nextcloud.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,142: DEBUG - + continue
2023-03-31 09:28:30,142: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,143: DEBUG - + [[ webmail.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,143: DEBUG - + [[ webmail.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,143: DEBUG - + continue
2023-03-31 09:28:30,143: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,144: DEBUG - + [[ wikijs.domain2.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,144: DEBUG - + [[ wikijs.domain2.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,144: DEBUG - + continue
2023-03-31 09:28:30,144: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,145: DEBUG - + [[ maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,145: DEBUG - + [[ maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,145: DEBUG - + continue
2023-03-31 09:28:30,146: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,146: DEBUG - + [[ energy.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,146: DEBUG - + [[ energy.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,146: DEBUG - + continue
2023-03-31 09:28:30,147: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,147: DEBUG - + [[ grocy.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,147: DEBUG - + [[ grocy.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,147: DEBUG - + continue
2023-03-31 09:28:30,148: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,148: DEBUG - + [[ home.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,148: DEBUG - + [[ home.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,148: DEBUG - + continue
2023-03-31 09:28:30,149: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,149: DEBUG - + [[ homeassistant.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,149: DEBUG - + [[ homeassistant.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,150: DEBUG - + continue
2023-03-31 09:28:30,150: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,150: DEBUG - + [[ mqtt.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,150: DEBUG - + [[ mqtt.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,151: DEBUG - + continue
2023-03-31 09:28:30,151: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,151: DEBUG - + [[ nextcloud.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,151: DEBUG - + [[ nextcloud.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,152: DEBUG - + continue
2023-03-31 09:28:30,152: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,152: DEBUG - + [[ nodered.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,152: DEBUG - + [[ nodered.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,153: DEBUG - + continue
2023-03-31 09:28:30,153: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,153: DEBUG - + [[ owntracks.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,154: DEBUG - + [[ owntracks.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,154: DEBUG - + continue
2023-03-31 09:28:30,154: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,154: DEBUG - + [[ webmail.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,155: DEBUG - + [[ webmail.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,155: DEBUG - + continue
2023-03-31 09:28:30,155: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,155: DEBUG - + [[ wikijs.maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,156: DEBUG - + [[ wikijs.maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,156: DEBUG - + continue
2023-03-31 09:28:30,156: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,156: DEBUG - + [[ domain3.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,157: DEBUG - + [[ domain3.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,157: DEBUG - + continue
2023-03-31 09:28:30,157: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,157: DEBUG - + [[ homeassistant.domain3.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,158: DEBUG - + [[ homeassistant.domain3.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,158: DEBUG - + continue
2023-03-31 09:28:30,158: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:30,158: DEBUG - + [[ wikijs.domain3.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-31 09:28:30,159: DEBUG - + [[ wikijs.domain3.tld =~ ^[^.]+\.local$ ]]
2023-03-31 09:28:30,159: DEBUG - + continue
2023-03-31 09:28:30,159: DEBUG - + [[ -e /etc/yunohost/mdns.aliases ]]
2023-03-31 09:28:31,163: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./43-dnsmasq" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/dnsmasq 7>&1']'
2023-03-31 09:28:31,183: DEBUG - + set -e
2023-03-31 09:28:31,184: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:31,186: DEBUG - +++ set +o
2023-03-31 09:28:31,186: DEBUG - +++ grep xtrace
2023-03-31 09:28:31,190: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:31,191: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:31,232: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/dnsmasq
2023-03-31 09:28:31,232: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/dnsmasq
2023-03-31 09:28:31,233: DEBUG - + cd /usr/share/yunohost/conf/dnsmasq
2023-03-31 09:28:31,233: DEBUG - + dnsmasq_dir=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:31,234: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:31,236: DEBUG - + etcdefault_dir=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/default
2023-03-31 09:28:31,237: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/default
2023-03-31 09:28:31,240: DEBUG - + cp plain/etcdefault /var/cache/yunohost/regenconf/pending/dnsmasq/etc/default/dnsmasq
2023-03-31 09:28:31,248: DEBUG - + cat plain/resolv.dnsmasq.conf
2023-03-31 09:28:31,249: DEBUG - + shuf
2023-03-31 09:28:31,250: DEBUG - + grep '^nameserver'
2023-03-31 09:28:31,255: DEBUG - ++ curl --max-time 10 -s -4 https://ip.yunohost.org
2023-03-31 09:28:32,259: DEBUG - + ipv4=xx.xx.xx.xx
2023-03-31 09:28:32,260: DEBUG - + ynh_validate_ip4 xx.xx.xx.xx
2023-03-31 09:28:32,285: DEBUG - + ynh_validate_ip --family=4 --ip_address=xx.xx.xx.xx
2023-03-31 09:28:32,356: DEBUG - + '[' 4 == 4 ']'
2023-03-31 09:28:32,357: DEBUG - + python3 /dev/stdin
2023-03-31 09:28:32,446: DEBUG - ++ curl --max-time 10 -s -6 https://ip6.yunohost.org
2023-03-31 09:28:32,665: DEBUG - ++ true
2023-03-31 09:28:32,666: DEBUG - + ipv6=
2023-03-31 09:28:32,666: DEBUG - + ynh_validate_ip6 ''
2023-03-31 09:28:32,690: DEBUG - + ynh_validate_ip --family=6 --ip_address=
2023-03-31 09:28:32,759: DEBUG - + '[' 6 == 4 ']'
2023-03-31 09:28:32,760: DEBUG - + '[' 6 == 6 ']'
2023-03-31 09:28:32,760: DEBUG - + python3 /dev/stdin
2023-03-31 09:28:32,848: DEBUG - + ipv6=
2023-03-31 09:28:32,851: DEBUG - ++ ip -j addr show
2023-03-31 09:28:32,852: DEBUG - ++ jq -r '[.[].ifname]|join(" ")'
2023-03-31 09:28:32,948: DEBUG - + interfaces='lo eth0 wlan0'
2023-03-31 09:28:32,955: DEBUG - + wireless_interfaces=lo
2023-03-31 09:28:32,956: DEBUG - ++ ls /sys/class/net
2023-03-31 09:28:32,956: DEBUG - + for dev in $(ls /sys/class/net)
2023-03-31 09:28:32,957: DEBUG - + '[' -d /sys/class/net/eth0/wireless ']'
2023-03-31 09:28:32,957: DEBUG - + for dev in $(ls /sys/class/net)
2023-03-31 09:28:32,958: DEBUG - + '[' -d /sys/class/net/lo/wireless ']'
2023-03-31 09:28:32,958: DEBUG - + for dev in $(ls /sys/class/net)
2023-03-31 09:28:32,959: DEBUG - + '[' -d /sys/class/net/wlan0/wireless ']'
2023-03-31 09:28:32,959: DEBUG - + grep -q up /sys/class/net/wlan0/operstate
2023-03-31 09:28:32,960: DEBUG - + export wireless_interfaces
2023-03-31 09:28:32,960: DEBUG - + ynh_render_template dnsmasq.conf.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf
2023-03-31 09:28:32,961: DEBUG - + local template_path=dnsmasq.conf.tpl
2023-03-31 09:28:32,962: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf
2023-03-31 09:28:32,962: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf
2023-03-31 09:28:32,963: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc
2023-03-31 09:28:32,966: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:32,967: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:32,967: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:33,213: DEBUG - + export interfaces
2023-03-31 09:28:33,214: DEBUG - + export ipv4
2023-03-31 09:28:33,214: DEBUG - + export ipv6
2023-03-31 09:28:33,215: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:33,215: DEBUG - + [[ ! domain2.tld =~ \.local$ ]]
2023-03-31 09:28:33,216: DEBUG - + export domain
2023-03-31 09:28:33,216: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain2.tld
2023-03-31 09:28:33,216: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:33,217: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain2.tld
2023-03-31 09:28:33,217: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain2.tld
2023-03-31 09:28:33,218: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:33,221: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:33,222: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:33,222: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:33,417: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:33,418: DEBUG - + [[ ! energy.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:33,418: DEBUG - + export domain
2023-03-31 09:28:33,419: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.domain2.tld
2023-03-31 09:28:33,419: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:33,420: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.domain2.tld
2023-03-31 09:28:33,420: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.domain2.tld
2023-03-31 09:28:33,421: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:33,425: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:33,425: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:33,426: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:33,622: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:33,622: DEBUG - + [[ ! firefly.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:33,623: DEBUG - + export domain
2023-03-31 09:28:33,624: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/firefly.domain2.tld
2023-03-31 09:28:33,624: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:33,624: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/firefly.domain2.tld
2023-03-31 09:28:33,625: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/firefly.domain2.tld
2023-03-31 09:28:33,626: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:33,630: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:33,630: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:33,631: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:33,821: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:33,822: DEBUG - + [[ ! home.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:33,822: DEBUG - + export domain
2023-03-31 09:28:33,823: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.domain2.tld
2023-03-31 09:28:33,823: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:33,824: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.domain2.tld
2023-03-31 09:28:33,824: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.domain2.tld
2023-03-31 09:28:33,826: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:33,829: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:33,830: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:33,831: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:34,020: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:34,021: DEBUG - + [[ ! homeassistant.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:34,021: DEBUG - + export domain
2023-03-31 09:28:34,021: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain2.tld
2023-03-31 09:28:34,022: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:34,022: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain2.tld
2023-03-31 09:28:34,023: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain2.tld
2023-03-31 09:28:34,024: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:34,028: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:34,029: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:34,029: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:34,221: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:34,222: DEBUG - + [[ ! nextcloud.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:34,223: DEBUG - + export domain
2023-03-31 09:28:34,223: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.domain2.tld
2023-03-31 09:28:34,224: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:34,224: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.domain2.tld
2023-03-31 09:28:34,224: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.domain2.tld
2023-03-31 09:28:34,226: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:34,230: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:34,230: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:34,231: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:34,423: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:34,423: DEBUG - + [[ ! webmail.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:34,424: DEBUG - + export domain
2023-03-31 09:28:34,424: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.domain2.tld
2023-03-31 09:28:34,425: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:34,425: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.domain2.tld
2023-03-31 09:28:34,426: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.domain2.tld
2023-03-31 09:28:34,427: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:34,431: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:34,432: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:34,432: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:34,653: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:34,655: DEBUG - + [[ ! wikijs.domain2.tld =~ \.local$ ]]
2023-03-31 09:28:34,656: DEBUG - + export domain
2023-03-31 09:28:34,657: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain2.tld
2023-03-31 09:28:34,658: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:34,658: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain2.tld
2023-03-31 09:28:34,659: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain2.tld
2023-03-31 09:28:34,660: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:34,662: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:34,663: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:34,664: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:34,854: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:34,855: DEBUG - + [[ ! maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:34,855: DEBUG - + export domain
2023-03-31 09:28:34,855: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld
2023-03-31 09:28:34,856: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:34,856: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld
2023-03-31 09:28:34,857: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld
2023-03-31 09:28:34,861: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:34,864: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:34,865: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:34,865: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:35,055: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:35,056: DEBUG - + [[ ! energy.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:35,056: DEBUG - + export domain
2023-03-31 09:28:35,056: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.maindomain.tld
2023-03-31 09:28:35,057: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:35,057: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.maindomain.tld
2023-03-31 09:28:35,058: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.maindomain.tld
2023-03-31 09:28:35,058: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:35,062: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:35,062: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:35,063: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:35,251: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:35,252: DEBUG - + [[ ! grocy.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:35,253: DEBUG - + export domain
2023-03-31 09:28:35,253: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/grocy.maindomain.tld
2023-03-31 09:28:35,254: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:35,254: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/grocy.maindomain.tld
2023-03-31 09:28:35,254: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/grocy.maindomain.tld
2023-03-31 09:28:35,256: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:35,259: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:35,260: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:35,260: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:35,451: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:35,452: DEBUG - + [[ ! home.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:35,453: DEBUG - + export domain
2023-03-31 09:28:35,453: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.maindomain.tld
2023-03-31 09:28:35,454: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:35,454: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.maindomain.tld
2023-03-31 09:28:35,455: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.maindomain.tld
2023-03-31 09:28:35,456: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:35,459: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:35,460: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:35,460: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:35,654: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:35,655: DEBUG - + [[ ! homeassistant.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:35,656: DEBUG - + export domain
2023-03-31 09:28:35,657: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.maindomain.tld
2023-03-31 09:28:35,658: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:35,658: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.maindomain.tld
2023-03-31 09:28:35,659: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.maindomain.tld
2023-03-31 09:28:35,660: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:35,663: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:35,664: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:35,664: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:35,861: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:35,862: DEBUG - + [[ ! mqtt.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:35,862: DEBUG - + export domain
2023-03-31 09:28:35,863: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/mqtt.maindomain.tld
2023-03-31 09:28:35,863: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:35,864: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/mqtt.maindomain.tld
2023-03-31 09:28:35,864: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/mqtt.maindomain.tld
2023-03-31 09:28:35,865: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:35,869: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:35,869: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:35,870: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:36,065: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:36,066: DEBUG - + [[ ! nextcloud.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:36,066: DEBUG - + export domain
2023-03-31 09:28:36,067: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.maindomain.tld
2023-03-31 09:28:36,067: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:36,068: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.maindomain.tld
2023-03-31 09:28:36,068: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.maindomain.tld
2023-03-31 09:28:36,069: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:36,073: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:36,074: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:36,074: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:36,262: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:36,263: DEBUG - + [[ ! nodered.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:36,263: DEBUG - + export domain
2023-03-31 09:28:36,264: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nodered.maindomain.tld
2023-03-31 09:28:36,264: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:36,265: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nodered.maindomain.tld
2023-03-31 09:28:36,265: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nodered.maindomain.tld
2023-03-31 09:28:36,266: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:36,270: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:36,270: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:36,271: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:36,462: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:36,463: DEBUG - + [[ ! owntracks.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:36,463: DEBUG - + export domain
2023-03-31 09:28:36,464: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/owntracks.maindomain.tld
2023-03-31 09:28:36,464: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:36,464: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/owntracks.maindomain.tld
2023-03-31 09:28:36,465: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/owntracks.maindomain.tld
2023-03-31 09:28:36,466: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:36,470: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:36,471: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:36,471: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:36,664: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:36,665: DEBUG - + [[ ! webmail.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:36,666: DEBUG - + export domain
2023-03-31 09:28:36,666: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.maindomain.tld
2023-03-31 09:28:36,666: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:36,667: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.maindomain.tld
2023-03-31 09:28:36,667: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.maindomain.tld
2023-03-31 09:28:36,668: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:36,672: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:36,673: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:36,673: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:36,862: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:36,863: DEBUG - + [[ ! wikijs.maindomain.tld =~ \.local$ ]]
2023-03-31 09:28:36,863: DEBUG - + export domain
2023-03-31 09:28:36,864: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.maindomain.tld
2023-03-31 09:28:36,864: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:36,865: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.maindomain.tld
2023-03-31 09:28:36,865: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.maindomain.tld
2023-03-31 09:28:36,866: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:36,870: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:36,871: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:36,871: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:37,060: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:37,060: DEBUG - + [[ ! domain3.tld =~ \.local$ ]]
2023-03-31 09:28:37,061: DEBUG - + export domain
2023-03-31 09:28:37,061: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain3.tld
2023-03-31 09:28:37,062: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:37,062: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain3.tld
2023-03-31 09:28:37,063: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain3.tld
2023-03-31 09:28:37,064: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:37,068: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:37,068: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:37,069: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:37,258: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:37,259: DEBUG - + [[ ! homeassistant.domain3.tld =~ \.local$ ]]
2023-03-31 09:28:37,259: DEBUG - + export domain
2023-03-31 09:28:37,260: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain3.tld
2023-03-31 09:28:37,260: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:37,261: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain3.tld
2023-03-31 09:28:37,261: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain3.tld
2023-03-31 09:28:37,262: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:37,266: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:37,266: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:37,267: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:37,458: DEBUG - + for domain in $YNH_DOMAINS
2023-03-31 09:28:37,459: DEBUG - + [[ ! wikijs.domain3.tld =~ \.local$ ]]
2023-03-31 09:28:37,459: DEBUG - + export domain
2023-03-31 09:28:37,460: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain3.tld
2023-03-31 09:28:37,460: DEBUG - + local template_path=domain.tpl
2023-03-31 09:28:37,461: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain3.tld
2023-03-31 09:28:37,461: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain3.tld
2023-03-31 09:28:37,462: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-31 09:28:37,466: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:37,467: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:37,467: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:37,679: DEBUG - ++ ls -1 /etc/dnsmasq.d
2023-03-31 09:28:37,680: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*$/ { print $1 }'
2023-03-31 09:28:37,687: DEBUG - + conf_files='energy.maindomain.tld
2023-03-31 09:28:37,688: DEBUG - energy.domain2.tld
2023-03-31 09:28:37,689: DEBUG - firefly.domain2.tld
2023-03-31 09:28:37,689: DEBUG - grocy.maindomain.tld
2023-03-31 09:28:37,690: DEBUG - homeassistant.domain3.tld
2023-03-31 09:28:37,690: DEBUG - homeassistant.maindomain.tld
2023-03-31 09:28:37,691: DEBUG - homeassistant.domain2.tld
2023-03-31 09:28:37,691: DEBUG - home.maindomain.tld
2023-03-31 09:28:37,691: DEBUG - home.domain2.tld
2023-03-31 09:28:37,691: DEBUG - domain3.tld
2023-03-31 09:28:37,692: DEBUG - maindomain.tld
2023-03-31 09:28:37,692: DEBUG - domain2.tld
2023-03-31 09:28:37,692: DEBUG - mqtt.maindomain.tld
2023-03-31 09:28:37,692: DEBUG - nextcloud.maindomain.tld
2023-03-31 09:28:37,693: DEBUG - nextcloud.domain2.tld
2023-03-31 09:28:37,693: DEBUG - nodered.maindomain.tld
2023-03-31 09:28:37,693: DEBUG - owntracks.maindomain.tld
2023-03-31 09:28:37,693: DEBUG - webmail.maindomain.tld
2023-03-31 09:28:37,694: DEBUG - webmail.domain2.tld
2023-03-31 09:28:37,694: DEBUG - wikijs.domain3.tld
2023-03-31 09:28:37,694: DEBUG - wikijs.maindomain.tld
2023-03-31 09:28:37,695: DEBUG - wikijs.domain2.tld'
2023-03-31 09:28:37,695: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,695: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ energy.maindomain.tld ]]
2023-03-31 09:28:37,696: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,696: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ energy.domain2.tld ]]
2023-03-31 09:28:37,697: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,697: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ firefly.domain2.tld ]]
2023-03-31 09:28:37,697: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,698: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ grocy.maindomain.tld ]]
2023-03-31 09:28:37,698: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,698: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.domain3.tld ]]
2023-03-31 09:28:37,699: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,699: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.maindomain.tld ]]
2023-03-31 09:28:37,700: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,700: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ homeassistant.domain2.tld ]]
2023-03-31 09:28:37,700: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,701: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ home.maindomain.tld ]]
2023-03-31 09:28:37,701: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,701: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ home.domain2.tld ]]
2023-03-31 09:28:37,702: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,702: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ domain3.tld ]]
2023-03-31 09:28:37,703: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,703: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ maindomain.tld ]]
2023-03-31 09:28:37,703: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,704: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ domain2.tld ]]
2023-03-31 09:28:37,704: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,704: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ mqtt.maindomain.tld ]]
2023-03-31 09:28:37,705: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,705: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nextcloud.maindomain.tld ]]
2023-03-31 09:28:37,706: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,706: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nextcloud.domain2.tld ]]
2023-03-31 09:28:37,706: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,707: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ nodered.maindomain.tld ]]
2023-03-31 09:28:37,707: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,707: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ owntracks.maindomain.tld ]]
2023-03-31 09:28:37,708: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,708: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ webmail.maindomain.tld ]]
2023-03-31 09:28:37,709: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,709: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ webmail.domain2.tld ]]
2023-03-31 09:28:37,709: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,710: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.domain3.tld ]]
2023-03-31 09:28:37,710: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,711: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.maindomain.tld ]]
2023-03-31 09:28:37,711: DEBUG - + for domain in $conf_files
2023-03-31 09:28:37,711: DEBUG - + [[ ! domain2.tld energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld maindomain.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld =~ wikijs.domain2.tld ]]
2023-03-31 09:28:38,715: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./46-nsswitch" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nsswitch 7>&1']'
2023-03-31 09:28:38,735: DEBUG - + set -e
2023-03-31 09:28:38,736: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nsswitch
2023-03-31 09:28:38,737: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nsswitch
2023-03-31 09:28:38,737: DEBUG - + cd /usr/share/yunohost/conf/nsswitch
2023-03-31 09:28:38,738: DEBUG - + install -D -m 644 nsswitch.conf /var/cache/yunohost/regenconf/pending/nsswitch/etc/nsswitch.conf
2023-03-31 09:28:39,742: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./52-fail2ban" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/fail2ban 7>&1']'
2023-03-31 09:28:39,761: DEBUG - + set -e
2023-03-31 09:28:39,763: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:39,764: DEBUG - +++ set +o
2023-03-31 09:28:39,764: DEBUG - +++ grep xtrace
2023-03-31 09:28:39,768: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:39,769: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:39,809: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/fail2ban
2023-03-31 09:28:39,810: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/fail2ban
2023-03-31 09:28:39,810: DEBUG - + cd /usr/share/yunohost/conf/fail2ban
2023-03-31 09:28:39,811: DEBUG - + fail2ban_dir=/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban
2023-03-31 09:28:39,811: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d
2023-03-31 09:28:39,813: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d
2023-03-31 09:28:39,817: DEBUG - + cp yunohost.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d/yunohost.conf
2023-03-31 09:28:39,825: DEBUG - + cp postfix-sasl.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d/postfix-sasl.conf
2023-03-31 09:28:39,829: DEBUG - + cp jail.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.conf
2023-03-31 09:28:39,836: DEBUG - ++ yunohost settings get security.ssh.ssh_port
2023-03-31 09:28:40,483: DEBUG - + export ssh_port=22
2023-03-31 09:28:40,484: DEBUG - + ssh_port=22
2023-03-31 09:28:40,485: DEBUG - + ynh_render_template yunohost-jails.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-31 09:28:40,485: DEBUG - + local template_path=yunohost-jails.conf
2023-03-31 09:28:40,486: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-31 09:28:40,486: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-31 09:28:40,488: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d
2023-03-31 09:28:40,491: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-31 09:28:40,492: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-31 09:28:40,492: DEBUG -                     ).render(os.environ));'
2023-03-31 09:28:41,506: DEBUG - Checking pending configuration which would have been applied for category 'yunohost'...
2023-03-31 09:28:41,567: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/yunohost-dyndns' to system conf '/etc/cron.d/yunohost-dyndns'
2023-03-31 09:28:41,568: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,569: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/yunohost-diagnosis' to system conf '/etc/cron.d/yunohost-diagnosis'
2023-03-31 09:28:41,569: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,570: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.daily/yunohost-fetch-apps-catalog' to system conf '/etc/cron.daily/yunohost-fetch-apps-catalog'
2023-03-31 09:28:41,570: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,571: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.daily/yunohost-certificate-renew' to system conf '/etc/cron.daily/yunohost-certificate-renew'
2023-03-31 09:28:41,571: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,572: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/dpkg/origins/yunohost' to system conf '/etc/dpkg/origins/yunohost'
2023-03-31 09:28:41,572: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,573: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/logind.conf.d/ynh-override.conf' to system conf '/etc/systemd/logind.conf.d/ynh-override.conf'
2023-03-31 09:28:41,573: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,574: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunoprompt.service' to system conf '/etc/systemd/system/yunoprompt.service'
2023-03-31 09:28:41,575: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,575: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-api.service' to system conf '/etc/systemd/system/yunohost-api.service'
2023-03-31 09:28:41,576: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,576: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-firewall.service' to system conf '/etc/systemd/system/yunohost-firewall.service'
2023-03-31 09:28:41,576: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,577: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/proc-hidepid.service' to system conf '/etc/systemd/system/proc-hidepid.service'
2023-03-31 09:28:41,577: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,578: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/ntp.service.d/ynh-override.conf' to system conf '/etc/systemd/system/ntp.service.d/ynh-override.conf'
2023-03-31 09:28:41,578: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,579: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/nftables.service.d/ynh-override.conf' to system conf '/etc/systemd/system/nftables.service.d/ynh-override.conf'
2023-03-31 09:28:41,579: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,580: DEBUG - The configuration is already up-to-date for category 'yunohost'
2023-03-31 09:28:41,580: DEBUG - Checking pending configuration which would have been applied for category 'ssl'...
2023-03-31 09:28:41,640: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/ssl/usr/share/yunohost/ssl/openssl.cnf' to system conf '/usr/share/yunohost/ssl/openssl.cnf'
2023-03-31 09:28:41,641: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,641: DEBUG - The configuration is already up-to-date for category 'ssl'
2023-03-31 09:28:41,642: DEBUG - Checking pending configuration which would have been applied for category 'ssh'...
2023-03-31 09:28:41,702: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config' to system conf '/etc/ssh/sshd_config'
2023-03-31 09:28:41,703: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,704: DEBUG - The configuration is already up-to-date for category 'ssh'
2023-03-31 09:28:41,704: DEBUG - Checking pending configuration which would have been applied for category 'slapd'...
2023-03-31 09:28:41,763: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/ldap.conf' to system conf '/etc/ldap/ldap.conf'
2023-03-31 09:28:41,764: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,765: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema/mailserver.ldif' to system conf '/etc/ldap/schema/mailserver.ldif'
2023-03-31 09:28:41,765: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,766: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema/sudo.ldif' to system conf '/etc/ldap/schema/sudo.ldif'
2023-03-31 09:28:41,766: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,767: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema/permission.ldif' to system conf '/etc/ldap/schema/permission.ldif'
2023-03-31 09:28:41,767: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,768: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/default/slapd' to system conf '/etc/default/slapd'
2023-03-31 09:28:41,768: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,769: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/systemd/system/slapd.service.d/ynh-override.conf' to system conf '/etc/systemd/system/slapd.service.d/ynh-override.conf'
2023-03-31 09:28:41,769: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,770: DEBUG - The configuration is already up-to-date for category 'slapd'
2023-03-31 09:28:41,770: DEBUG - Checking pending configuration which would have been applied for category 'nslcd'...
2023-03-31 09:28:41,830: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nslcd/etc/nslcd.conf' to system conf '/etc/nslcd.conf'
2023-03-31 09:28:41,831: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,831: DEBUG - The configuration is already up-to-date for category 'nslcd'
2023-03-31 09:28:41,832: DEBUG - Checking pending configuration which would have been applied for category 'apt'...
2023-03-31 09:28:41,891: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/apt/etc/apt/sources.list.d/extra_php_version.list' to system conf '/etc/apt/sources.list.d/extra_php_version.list'
2023-03-31 09:28:41,892: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,893: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/apt/etc/apt/preferences.d/extra_php_version' to system conf '/etc/apt/preferences.d/extra_php_version'
2023-03-31 09:28:41,893: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,894: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/apt/etc/apt/preferences.d/ban_packages' to system conf '/etc/apt/preferences.d/ban_packages'
2023-03-31 09:28:41,894: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,895: DEBUG - The configuration is already up-to-date for category 'apt'
2023-03-31 09:28:41,895: DEBUG - Checking pending configuration which would have been applied for category 'metronome'...
2023-03-31 09:28:41,955: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/metronome.cfg.lua' to system conf '/etc/metronome/metronome.cfg.lua'
2023-03-31 09:28:41,956: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:41,956: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/home.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/home.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,957: DEBUG - > system conf is already removed
2023-03-31 09:28:41,957: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/nodered.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/nodered.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,958: DEBUG - > system conf is already removed
2023-03-31 09:28:41,958: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/nextcloud.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/nextcloud.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,958: DEBUG - > system conf is already removed
2023-03-31 09:28:41,959: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/homeassistant.domain3.tld.cfg.lua' to system conf '/etc/metronome/conf.d/homeassistant.domain3.tld.cfg.lua'
2023-03-31 09:28:41,959: DEBUG - > system conf is already removed
2023-03-31 09:28:41,959: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/wikijs.domain3.tld.cfg.lua' to system conf '/etc/metronome/conf.d/wikijs.domain3.tld.cfg.lua'
2023-03-31 09:28:41,960: DEBUG - > system conf is already removed
2023-03-31 09:28:41,960: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/home.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/home.domain2.tld.cfg.lua'
2023-03-31 09:28:41,960: DEBUG - > system conf is already removed
2023-03-31 09:28:41,961: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/owntracks.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/owntracks.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,961: DEBUG - > system conf is already removed
2023-03-31 09:28:41,961: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/wikijs.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/wikijs.domain2.tld.cfg.lua'
2023-03-31 09:28:41,962: DEBUG - > system conf is already removed
2023-03-31 09:28:41,962: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/wikijs.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/wikijs.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,963: DEBUG - > system conf is already removed
2023-03-31 09:28:41,963: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/domain3.tld.cfg.lua' to system conf '/etc/metronome/conf.d/domain3.tld.cfg.lua'
2023-03-31 09:28:41,963: DEBUG - > system conf is already removed
2023-03-31 09:28:41,964: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/homeassistant.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/homeassistant.domain2.tld.cfg.lua'
2023-03-31 09:28:41,964: DEBUG - > system conf is already removed
2023-03-31 09:28:41,964: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/grocy.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/grocy.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,965: DEBUG - > system conf is already removed
2023-03-31 09:28:41,965: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/nextcloud.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/nextcloud.domain2.tld.cfg.lua'
2023-03-31 09:28:41,965: DEBUG - > system conf is already removed
2023-03-31 09:28:41,966: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/maindomain.tld.cfg.lua'
2023-03-31 09:28:41,966: DEBUG - > system conf is already removed
2023-03-31 09:28:41,966: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/webmail.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/webmail.domain2.tld.cfg.lua'
2023-03-31 09:28:41,967: DEBUG - > system conf is already removed
2023-03-31 09:28:41,967: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/webmail.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/webmail.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,967: DEBUG - > system conf is already removed
2023-03-31 09:28:41,968: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/energy.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/energy.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,968: DEBUG - > system conf is already removed
2023-03-31 09:28:41,968: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/mqtt.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/mqtt.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,969: DEBUG - > system conf is already removed
2023-03-31 09:28:41,969: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/firefly.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/firefly.domain2.tld.cfg.lua'
2023-03-31 09:28:41,969: DEBUG - > system conf is already removed
2023-03-31 09:28:41,970: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/homeassistant.maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/homeassistant.maindomain.tld.cfg.lua'
2023-03-31 09:28:41,970: DEBUG - > system conf is already removed
2023-03-31 09:28:41,970: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/domain2.tld.cfg.lua'
2023-03-31 09:28:41,971: DEBUG - > system conf is already removed
2023-03-31 09:28:41,971: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/energy.domain2.tld.cfg.lua' to system conf '/etc/metronome/conf.d/energy.domain2.tld.cfg.lua'
2023-03-31 09:28:41,972: DEBUG - > system conf is already removed
2023-03-31 09:28:41,972: DEBUG - The configuration is already up-to-date for category 'metronome'
2023-03-31 09:28:41,972: DEBUG - Checking pending configuration which would have been applied for category 'nginx'...
2023-03-31 09:28:42,032: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled/default' to system conf '/etc/nginx/sites-enabled/default'
2023-03-31 09:28:42,033: DEBUG - > system conf is already removed
2023-03-31 09:28:42,033: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc' to system conf '/etc/nginx/conf.d/security.conf.inc'
2023-03-31 09:28:42,034: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,034: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/webmail.maindomain.tld.conf'
2023-03-31 09:28:42,035: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,035: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/homeassistant.maindomain.tld.conf'
2023-03-31 09:28:42,036: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,036: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf' to system conf '/etc/nginx/conf.d/home.domain2.tld.conf'
2023-03-31 09:28:42,037: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,037: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf' to system conf '/etc/nginx/conf.d/energy.domain2.tld.conf'
2023-03-31 09:28:42,038: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,038: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.conf' to system conf '/etc/nginx/conf.d/homeassistant.domain3.tld.conf'
2023-03-31 09:28:42,039: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,039: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/wikijs.maindomain.tld.conf'
2023-03-31 09:28:42,040: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,040: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/owntracks.maindomain.tld.conf'
2023-03-31 09:28:42,041: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,041: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_admin.conf.inc'
2023-03-31 09:28:42,042: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,042: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/nextcloud.maindomain.tld.conf'
2023-03-31 09:28:42,043: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,043: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_api.conf.inc'
2023-03-31 09:28:42,044: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,044: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.conf' to system conf '/etc/nginx/conf.d/domain3.tld.conf'
2023-03-31 09:28:42,045: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,045: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf' to system conf '/etc/nginx/conf.d/nextcloud.domain2.tld.conf'
2023-03-31 09:28:42,046: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,046: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/grocy.maindomain.tld.conf'
2023-03-31 09:28:42,047: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,047: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf' to system conf '/etc/nginx/conf.d/yunohost_admin.conf'
2023-03-31 09:28:42,048: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,048: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/mqtt.maindomain.tld.conf'
2023-03-31 09:28:42,049: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,049: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.conf' to system conf '/etc/nginx/conf.d/firefly.domain2.tld.conf'
2023-03-31 09:28:42,050: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,050: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.conf' to system conf '/etc/nginx/conf.d/wikijs.domain3.tld.conf'
2023-03-31 09:28:42,051: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,051: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_http_errors.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_http_errors.conf.inc'
2023-03-31 09:28:42,052: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,052: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_panel.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_panel.conf.inc'
2023-03-31 09:28:42,053: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,053: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/energy.maindomain.tld.conf'
2023-03-31 09:28:42,053: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,054: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/nodered.maindomain.tld.conf'
2023-03-31 09:28:42,054: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,055: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf' to system conf '/etc/nginx/conf.d/home.maindomain.tld.conf'
2023-03-31 09:28:42,056: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,056: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf' to system conf '/etc/nginx/conf.d/maindomain.tld.conf'
2023-03-31 09:28:42,056: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,057: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.conf' to system conf '/etc/nginx/conf.d/wikijs.domain2.tld.conf'
2023-03-31 09:28:42,057: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,058: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/ssowat.conf' to system conf '/etc/nginx/conf.d/ssowat.conf'
2023-03-31 09:28:42,058: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,059: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.conf' to system conf '/etc/nginx/conf.d/webmail.domain2.tld.conf'
2023-03-31 09:28:42,060: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,060: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/acme-challenge.conf.inc' to system conf '/etc/nginx/conf.d/acme-challenge.conf.inc'
2023-03-31 09:28:42,061: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,061: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/global.conf' to system conf '/etc/nginx/conf.d/global.conf'
2023-03-31 09:28:42,061: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,062: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf' to system conf '/etc/nginx/conf.d/homeassistant.domain2.tld.conf'
2023-03-31 09:28:42,062: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,063: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_sso.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_sso.conf.inc'
2023-03-31 09:28:42,063: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,064: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf' to system conf '/etc/nginx/conf.d/domain2.tld.conf'
2023-03-31 09:28:42,064: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,065: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/redirect_to_admin.conf' to system conf '/etc/nginx/conf.d/default.d/redirect_to_admin.conf'
2023-03-31 09:28:42,065: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,066: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/owntracks.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,066: DEBUG - > system conf is already removed
2023-03-31 09:28:42,067: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/energy.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,067: DEBUG - > system conf is already removed
2023-03-31 09:28:42,067: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/energy.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,068: DEBUG - > system conf is already removed
2023-03-31 09:28:42,068: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,069: DEBUG - > system conf is already removed
2023-03-31 09:28:42,069: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain3.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/homeassistant.domain3.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,069: DEBUG - > system conf is already removed
2023-03-31 09:28:42,070: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain3.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/wikijs.domain3.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,070: DEBUG - > system conf is already removed
2023-03-31 09:28:42,070: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/wikijs.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,071: DEBUG - > system conf is already removed
2023-03-31 09:28:42,071: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/nextcloud.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,071: DEBUG - > system conf is already removed
2023-03-31 09:28:42,072: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/home.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,072: DEBUG - > system conf is already removed
2023-03-31 09:28:42,073: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/home.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,073: DEBUG - > system conf is already removed
2023-03-31 09:28:42,073: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/homeassistant.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,074: DEBUG - > system conf is already removed
2023-03-31 09:28:42,074: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/homeassistant.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,074: DEBUG - > system conf is already removed
2023-03-31 09:28:42,075: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/webmail.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,075: DEBUG - > system conf is already removed
2023-03-31 09:28:42,075: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/firefly.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/firefly.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,076: DEBUG - > system conf is already removed
2023-03-31 09:28:42,076: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain3.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/domain3.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,076: DEBUG - > system conf is already removed
2023-03-31 09:28:42,077: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/mqtt.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,077: DEBUG - > system conf is already removed
2023-03-31 09:28:42,078: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/grocy.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,078: DEBUG - > system conf is already removed
2023-03-31 09:28:42,078: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/nodered.maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,079: DEBUG - > system conf is already removed
2023-03-31 09:28:42,079: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/nextcloud.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,080: DEBUG - > system conf is already removed
2023-03-31 09:28:42,080: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/webmail.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,080: DEBUG - > system conf is already removed
2023-03-31 09:28:42,081: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.domain2.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/wikijs.domain2.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,081: DEBUG - > system conf is already removed
2023-03-31 09:28:42,081: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf'
2023-03-31 09:28:42,082: DEBUG - > system conf is already removed
2023-03-31 09:28:42,082: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/webmail.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,083: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,083: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/energy.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,084: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,084: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/home.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,085: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,085: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,086: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,086: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,087: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,087: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,088: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,088: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,089: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,089: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,090: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,090: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,091: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,091: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/home.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,092: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,092: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,093: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,093: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,094: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,094: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,095: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,095: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,096: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,096: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,097: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,097: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/firefly.domain2.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/firefly.domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,097: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,098: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,098: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,099: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,099: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,100: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,100: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,101: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain3.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/domain3.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,101: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,102: DEBUG - processing pending conf 'None' to system conf '/var/www/.well-known/domain2.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,102: WARNING - The configuration file '/var/www/.well-known/domain2.tld/autoconfig/mail/config-v1.1.xml' has been manually modified and will not be updated
2023-03-31 09:28:42,104: DEBUG - processing pending conf 'None' to system conf '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-31 09:28:42,104: WARNING - The configuration file '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml' has been manually modified and will not be updated
2023-03-31 09:28:42,106: DEBUG - updating conf hashes for 'nginx' with: {'/etc/nginx/conf.d/acme-challenge.conf.inc': '6e532401262f7daf627c6482d6367f5d', '/etc/nginx/conf.d/default.d/redirect_to_admin.conf': '69b9d60d4f87f404e4d376458d9de4e1', '/etc/nginx/conf.d/energy.maindomain.tld.conf': '96f165532c492542146f78c8e82f110d', '/etc/nginx/conf.d/energy.domain2.tld.conf': '1bb8377461a591e61d56f28c48687a29', '/etc/nginx/conf.d/firefly.domain2.tld.conf': '4848787a4eb782d02b59786f461f6eb4', '/etc/nginx/conf.d/global.conf': 'f8c8721f10d718546b2735080770d307', '/etc/nginx/conf.d/grocy.maindomain.tld.conf': '5e58e0192716cf02d731eb824571be54', '/etc/nginx/conf.d/home.maindomain.tld.conf': '68343514fd072f5b2f577c7b2013d2d0', '/etc/nginx/conf.d/home.domain2.tld.conf': '343935fa411049bb4939e1b0e2f81022', '/etc/nginx/conf.d/homeassistant.domain3.tld.conf': '190279b83d001d98a89959b797dce787', '/etc/nginx/conf.d/homeassistant.maindomain.tld.conf': 'ee908e65fd895dbd48e47e4a8df9a780', '/etc/nginx/conf.d/homeassistant.domain2.tld.conf': '39f50e49becb3a2a48a37e6bf9edf17d', '/etc/nginx/conf.d/domain3.tld.conf': '3b3baa698eb93fc9674161fb43dc1be0', '/etc/nginx/conf.d/maindomain.tld.conf': '70ca02c4116634fcc7948a2b83ef1328', '/etc/nginx/conf.d/domain2.tld.conf': 'ed9e9a0fa205d666f7894093b9c197d2', '/etc/nginx/conf.d/mqtt.maindomain.tld.conf': '969266778c15d83fb6cbe335b856bfd0', '/etc/nginx/conf.d/nextcloud.maindomain.tld.conf': '2db6aa216ac8a461470489988cbdf525', '/etc/nginx/conf.d/nextcloud.domain2.tld.conf': '738e6c3a29de161eb5624ebf070fb263', '/etc/nginx/conf.d/nodered.maindomain.tld.conf': '48faac0350ed3291ef9619b877d7fd15', '/etc/nginx/conf.d/owntracks.maindomain.tld.conf': 'e91c9807ece13af7841bea8d4e57d342', '/etc/nginx/conf.d/security.conf.inc': '2ceb56ca697e974c9021a47b7c415eb7', '/etc/nginx/conf.d/ssowat.conf': '88f0941db4a897c214f34a0661db890d', '/etc/nginx/conf.d/webmail.maindomain.tld.conf': '09f4c0e25e7fa32a7420745f8e629dc2', '/etc/nginx/conf.d/webmail.domain2.tld.conf': '32a14a22c5d99da4cfffe7db7e845cdc', '/etc/nginx/conf.d/wikijs.domain3.tld.conf': '4df4edcf05b85fb09c942dc95fe42a71', '/etc/nginx/conf.d/wikijs.maindomain.tld.conf': '76f1cd764850a48f734b5377aa0353e0', '/etc/nginx/conf.d/wikijs.domain2.tld.conf': 'cc865ae4eee75d85125cf529983c40fc', '/etc/nginx/conf.d/yunohost_admin.conf': '4f23bfc63fa5614e5b6997efcd83706c', '/etc/nginx/conf.d/yunohost_admin.conf.inc': 'e50af8d763f22816f75e6d2f5955f14c', '/etc/nginx/conf.d/yunohost_api.conf.inc': '71e89f68f5af5d83d161c54ade8d192f', '/etc/nginx/conf.d/yunohost_http_errors.conf.inc': '7bd05c30c115a0101d1fd37e66fca33d', '/etc/nginx/conf.d/yunohost_panel.conf.inc': '3de64e15d9874e6e17ab29cb6e48f188', '/etc/nginx/conf.d/yunohost_sso.conf.inc': '2230d8402c1167bea5db3f06f327e8fa', '/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/config-v1.1.xml': 'f25900ff34f45cff9a40ee0075be103c', '/var/www/.well-known/energy.domain2.tld/autoconfig/mail/config-v1.1.xml': 'c52db13c77b49191d4991f54198d9611', '/var/www/.well-known/firefly.domain2.tld/autoconfig/mail/config-v1.1.xml': '07748c36a8ad8bc8622534535443dac3', '/var/www/.well-known/grocy.maindomain.tld/autoconfig/mail/config-v1.1.xml': '09fa922d08ff198397b74d75c1caeaa9', '/var/www/.well-known/home.maindomain.tld/autoconfig/mail/config-v1.1.xml': 'b209b2a9983826b11090853ee9135d53', '/var/www/.well-known/home.domain2.tld/autoconfig/mail/config-v1.1.xml': '1c19c2e0a6d2dc053b9211c25aeb631a', '/var/www/.well-known/homeassistant.domain3.tld/autoconfig/mail/config-v1.1.xml': '4ef9eee50d7b2fba481d49b3e8303cd1', '/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/config-v1.1.xml': 'e939e5d33ea1b25b8d62cb723b794167', '/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/config-v1.1.xml': '9468117cd0073facc3d2567c1e4ede47', '/var/www/.well-known/domain3.tld/autoconfig/mail/config-v1.1.xml': 'cbf3b04587de328ab31614a7f7952e69', '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml': '5a6ed21fd8a9edbfb216ad9a00593dec', '/var/www/.well-known/domain2.tld/autoconfig/mail/config-v1.1.xml': '0b4c5a1bd508077203ca3cf541347e86', '/var/www/.well-known/mqtt.maindomain.tld/autoconfig/mail/config-v1.1.xml': '249c1ada1339f2f71d6ab19f1307fb7c', '/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/config-v1.1.xml': '207c95c2bcaf8c0b640a448594fdd7bb', '/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/config-v1.1.xml': '81e8c0d9d03348ada4dc183c22a6ae3e', '/var/www/.well-known/nodered.maindomain.tld/autoconfig/mail/config-v1.1.xml': '31a0bb440becf91e0a201add403ae8a7', '/var/www/.well-known/owntracks.maindomain.tld/autoconfig/mail/config-v1.1.xml': 'f8f610675e691a0897f8b363f2846e3d', '/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/config-v1.1.xml': 'efc809c8c0ce2fb6b35c2258f1e3eb8a', '/var/www/.well-known/webmail.domain2.tld/autoconfig/mail/config-v1.1.xml': 'c0cc4f49e3aee5b651073626143d174a', '/var/www/.well-known/wikijs.domain3.tld/autoconfig/mail/config-v1.1.xml': '88d9ba736a9e86bf937ec449d6d866a8', '/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/config-v1.1.xml': '6502a23d1ad873063d7562e572588d28', '/var/www/.well-known/wikijs.domain2.tld/autoconfig/mail/config-v1.1.xml': 'fb7fa49d28fe089faf5fab3a50e9793d', '/etc/nginx/sites-enabled/default': None, '/etc/nginx/conf.d/owntracks.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/energy.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/energy.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/homeassistant.domain3.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/wikijs.domain3.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/wikijs.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/nextcloud.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/home.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/home.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/homeassistant.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/homeassistant.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/webmail.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/firefly.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/domain3.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/mqtt.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/grocy.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/nodered.maindomain.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/nextcloud.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/webmail.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/wikijs.domain2.tld.d/yunohost_local.conf': None, '/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf': None}
2023-03-31 09:28:42,211: DEBUG - Checking pending configuration which would have been applied for category 'postfix'...
2023-03-31 09:28:42,271: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-domains.cf' to system conf '/etc/postfix/ldap-domains.cf'
2023-03-31 09:28:42,272: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,272: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sasl_passwd' to system conf '/etc/postfix/sasl_passwd'
2023-03-31 09:28:42,273: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,273: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/header_checks' to system conf '/etc/postfix/header_checks'
2023-03-31 09:28:42,274: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,274: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sender_canonical' to system conf '/etc/postfix/sender_canonical'
2023-03-31 09:28:42,275: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,275: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-aliases.cf' to system conf '/etc/postfix/ldap-aliases.cf'
2023-03-31 09:28:42,276: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,276: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/master.cf' to system conf '/etc/postfix/master.cf'
2023-03-31 09:28:42,277: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,277: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf' to system conf '/etc/postfix/main.cf'
2023-03-31 09:28:42,279: DEBUG - Configuration file '/etc/postfix/main.cf' backed up to '/var/cache/yunohost/regenconf/backup/etc/postfix/main.cf-20230331.082842'
2023-03-31 09:28:42,280: DEBUG - Configuration file '/etc/postfix/main.cf' updated
2023-03-31 09:28:42,280: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-accounts.cf' to system conf '/etc/postfix/ldap-accounts.cf'
2023-03-31 09:28:42,281: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,281: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni' to system conf '/etc/postfix/sni'
2023-03-31 09:28:42,282: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,282: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/smtp_reply_filter' to system conf '/etc/postfix/smtp_reply_filter'
2023-03-31 09:28:42,283: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,283: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-groups.cf' to system conf '/etc/postfix/ldap-groups.cf'
2023-03-31 09:28:42,284: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,284: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/default/postsrsd' to system conf '/etc/default/postsrsd'
2023-03-31 09:28:42,285: DEBUG - Configuration file '/etc/default/postsrsd' backed up to '/var/cache/yunohost/regenconf/backup/etc/default/postsrsd-20230331.082842'
2023-03-31 09:28:42,286: DEBUG - Configuration file '/etc/default/postsrsd' updated
2023-03-31 09:28:42,287: SUCCESS - Configuration updated for 'postfix'
2023-03-31 09:28:42,288: DEBUG - updating conf hashes for 'postfix' with: {'/etc/default/postsrsd': 'c23baa600bab04f0a45f93015f1a383e', '/etc/postfix/header_checks': '80a29f033d979766873a0bd90f5a6542', '/etc/postfix/ldap-accounts.cf': '301af4a3fa12e43fffa4216ffda0f2b2', '/etc/postfix/ldap-aliases.cf': '8712ccd28e11fda276abd34e8ce85b5a', '/etc/postfix/ldap-domains.cf': '082d1b0953e8021982c5cffd3d7f10a9', '/etc/postfix/ldap-groups.cf': '1cf2c66289db19475443b83d10a3f3eb', '/etc/postfix/main.cf': '446151f972519d65bc5548085bed2ad5', '/etc/postfix/master.cf': 'c32bf9a7d37a33b45a93d08e5fdbe1e2', '/etc/postfix/sasl_passwd': '1a9d5c50bb33950e8663fd988318fe97', '/etc/postfix/sender_canonical': '6af7cba824e4a563ec6d7d786f891e2f', '/etc/postfix/smtp_reply_filter': 'ff0bbf5d75d5e4096733c51d7745d924', '/etc/postfix/sni': 'e5d2e4ef31565f74470d9acd2ebdf729'}
2023-03-31 09:28:42,390: DEBUG - Checking pending configuration which would have been applied for category 'dovecot'...
2023-03-31 09:28:42,450: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot-ldap.conf' to system conf '/etc/dovecot/dovecot-ldap.conf'
2023-03-31 09:28:42,451: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,452: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf' to system conf '/etc/dovecot/dovecot.conf'
2023-03-31 09:28:42,455: DEBUG - Configuration file '/etc/dovecot/dovecot.conf' backed up to '/var/cache/yunohost/regenconf/backup/etc/dovecot/dovecot.conf-20230331.082842'
2023-03-31 09:28:42,457: DEBUG - Configuration file '/etc/dovecot/dovecot.conf' updated
2023-03-31 09:28:42,457: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d/pre-ext.conf' to system conf '/etc/dovecot/yunohost.d/pre-ext.conf'
2023-03-31 09:28:42,458: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,458: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d/post-ext.conf' to system conf '/etc/dovecot/yunohost.d/post-ext.conf'
2023-03-31 09:28:42,459: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,459: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/global_script/dovecot.sieve' to system conf '/etc/dovecot/global_script/dovecot.sieve'
2023-03-31 09:28:42,460: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,460: SUCCESS - Configuration updated for 'dovecot'
2023-03-31 09:28:42,461: DEBUG - updating conf hashes for 'dovecot' with: {'/etc/dovecot/dovecot-ldap.conf': 'f3fec990f5deb2121d0420fbfb4f4101', '/etc/dovecot/dovecot.conf': '26e3c62f6b725190324cdae0843b9df8', '/etc/dovecot/global_script/dovecot.sieve': 'f6c923affd80d9fda418dbf93664717c', '/etc/dovecot/yunohost.d/post-ext.conf': '714bdbe482b6130f817db02bb96f3770', '/etc/dovecot/yunohost.d/pre-ext.conf': '0f6216e006ef1be6ca7d7fc23ca91992'}
2023-03-31 09:28:42,563: DEBUG - Checking pending configuration which would have been applied for category 'rspamd'...
2023-03-31 09:28:42,624: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/dkim_signing.conf' to system conf '/etc/rspamd/local.d/dkim_signing.conf'
2023-03-31 09:28:42,625: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,625: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/metrics.conf' to system conf '/etc/rspamd/local.d/metrics.conf'
2023-03-31 09:28:42,626: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,626: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/rspamd/etc/dovecot/global_script/rspamd.sieve' to system conf '/etc/dovecot/global_script/rspamd.sieve'
2023-03-31 09:28:42,627: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,627: DEBUG - The configuration is already up-to-date for category 'rspamd'
2023-03-31 09:28:42,628: DEBUG - Checking pending configuration which would have been applied for category 'mdns'...
2023-03-31 09:28:42,687: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/mdns/etc/yunohost/mdns.yml' to system conf '/etc/yunohost/mdns.yml'
2023-03-31 09:28:42,688: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,689: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/mdns/etc/systemd/system/yunomdns.service' to system conf '/etc/systemd/system/yunomdns.service'
2023-03-31 09:28:42,689: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,690: DEBUG - The configuration is already up-to-date for category 'mdns'
2023-03-31 09:28:42,690: DEBUG - Checking pending configuration which would have been applied for category 'dnsmasq'...
2023-03-31 09:28:42,750: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/resolv.dnsmasq.conf' to system conf '/etc/resolv.dnsmasq.conf'
2023-03-31 09:28:42,752: DEBUG - Configuration file '/etc/resolv.dnsmasq.conf' backed up to '/var/cache/yunohost/regenconf/backup/etc/resolv.dnsmasq.conf-20230331.082842'
2023-03-31 09:28:42,753: DEBUG - Configuration file '/etc/resolv.dnsmasq.conf' updated
2023-03-31 09:28:42,753: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf' to system conf '/etc/dnsmasq.conf'
2023-03-31 09:28:42,754: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,755: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.domain2.tld' to system conf '/etc/dnsmasq.d/webmail.domain2.tld'
2023-03-31 09:28:42,756: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,756: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.domain2.tld' to system conf '/etc/dnsmasq.d/energy.domain2.tld'
2023-03-31 09:28:42,757: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,757: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.maindomain.tld' to system conf '/etc/dnsmasq.d/home.maindomain.tld'
2023-03-31 09:28:42,758: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,758: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain3.tld' to system conf '/etc/dnsmasq.d/homeassistant.domain3.tld'
2023-03-31 09:28:42,759: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,759: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.domain2.tld' to system conf '/etc/dnsmasq.d/homeassistant.domain2.tld'
2023-03-31 09:28:42,760: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,760: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nodered.maindomain.tld' to system conf '/etc/dnsmasq.d/nodered.maindomain.tld'
2023-03-31 09:28:42,761: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,761: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain2.tld' to system conf '/etc/dnsmasq.d/wikijs.domain2.tld'
2023-03-31 09:28:42,762: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,762: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.maindomain.tld' to system conf '/etc/dnsmasq.d/wikijs.maindomain.tld'
2023-03-31 09:28:42,763: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,763: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/grocy.maindomain.tld' to system conf '/etc/dnsmasq.d/grocy.maindomain.tld'
2023-03-31 09:28:42,763: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,764: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/home.domain2.tld' to system conf '/etc/dnsmasq.d/home.domain2.tld'
2023-03-31 09:28:42,764: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,765: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld' to system conf '/etc/dnsmasq.d/maindomain.tld'
2023-03-31 09:28:42,766: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,766: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.maindomain.tld' to system conf '/etc/dnsmasq.d/nextcloud.maindomain.tld'
2023-03-31 09:28:42,766: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,767: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain2.tld' to system conf '/etc/dnsmasq.d/domain2.tld'
2023-03-31 09:28:42,767: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,768: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/homeassistant.maindomain.tld' to system conf '/etc/dnsmasq.d/homeassistant.maindomain.tld'
2023-03-31 09:28:42,768: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,769: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/nextcloud.domain2.tld' to system conf '/etc/dnsmasq.d/nextcloud.domain2.tld'
2023-03-31 09:28:42,769: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,770: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/mqtt.maindomain.tld' to system conf '/etc/dnsmasq.d/mqtt.maindomain.tld'
2023-03-31 09:28:42,770: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,771: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/energy.maindomain.tld' to system conf '/etc/dnsmasq.d/energy.maindomain.tld'
2023-03-31 09:28:42,771: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,771: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/firefly.domain2.tld' to system conf '/etc/dnsmasq.d/firefly.domain2.tld'
2023-03-31 09:28:42,772: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,772: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/wikijs.domain3.tld' to system conf '/etc/dnsmasq.d/wikijs.domain3.tld'
2023-03-31 09:28:42,773: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,773: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/owntracks.maindomain.tld' to system conf '/etc/dnsmasq.d/owntracks.maindomain.tld'
2023-03-31 09:28:42,774: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,774: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/webmail.maindomain.tld' to system conf '/etc/dnsmasq.d/webmail.maindomain.tld'
2023-03-31 09:28:42,775: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,775: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/domain3.tld' to system conf '/etc/dnsmasq.d/domain3.tld'
2023-03-31 09:28:42,776: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,776: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/default/dnsmasq' to system conf '/etc/default/dnsmasq'
2023-03-31 09:28:42,776: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,777: SUCCESS - Configuration updated for 'dnsmasq'
2023-03-31 09:28:42,778: DEBUG - updating conf hashes for 'dnsmasq' with: {'/etc/default/dnsmasq': 'ff5c2923b4d5e1e51ffd8d226c26fe2b', '/etc/dnsmasq.conf': 'eb5a7091f047b94f656ea5a2e4bfbaa0', '/etc/dnsmasq.d/energy.maindomain.tld': 'ebb4a0dbb76f94a2f8c0c6ebe078c402', '/etc/dnsmasq.d/energy.domain2.tld': 'f2e53fe803d317bdeb67a0fab656c4a1', '/etc/dnsmasq.d/firefly.domain2.tld': '2ffc077e5c9ffee4089ecac7b5a3d7ff', '/etc/dnsmasq.d/grocy.maindomain.tld': 'b66631ab9bc32d75215199a77678fa2a', '/etc/dnsmasq.d/home.maindomain.tld': '610cc0365f4794f21ab0ec3f20970580', '/etc/dnsmasq.d/home.domain2.tld': '367e08af86adced522fe1d32b23d5808', '/etc/dnsmasq.d/homeassistant.domain3.tld': '747b28bfe6868f4a3c599521a4b0c2c2', '/etc/dnsmasq.d/homeassistant.maindomain.tld': 'f5f5fb8a8e015a57bea8c472e5a57881', '/etc/dnsmasq.d/homeassistant.domain2.tld': 'a7a736719831802ab9e61001a2d6fccb', '/etc/dnsmasq.d/domain3.tld': '542614856cd82d4973aabbdd62cf7237', '/etc/dnsmasq.d/maindomain.tld': '5309d182c2daeb3c84a6a64f2d84aed0', '/etc/dnsmasq.d/domain2.tld': 'c16dafe8c5ce2051684e37a3787bee16', '/etc/dnsmasq.d/mqtt.maindomain.tld': 'ad44033340a206d5b2340952c4c28501', '/etc/dnsmasq.d/nextcloud.maindomain.tld': '31c429a60a46bac8195616ae38c77ab4', '/etc/dnsmasq.d/nextcloud.domain2.tld': '9a5f83bf8c30e854bcabf61c0cd7476c', '/etc/dnsmasq.d/nodered.maindomain.tld': '592f11be1e3d97783ab517fe01edb758', '/etc/dnsmasq.d/owntracks.maindomain.tld': '709f6c78537f652f2c5ccdcbe81065f4', '/etc/dnsmasq.d/webmail.maindomain.tld': 'f812f668fc3f86ffc49cf0c8251c9967', '/etc/dnsmasq.d/webmail.domain2.tld': '486ee957398b6e900874b737c5674599', '/etc/dnsmasq.d/wikijs.domain3.tld': 'f33174a4fc2480f8f45e7ed394e20cbc', '/etc/dnsmasq.d/wikijs.maindomain.tld': '1086bc5f4f71e5ada40759a2447f6513', '/etc/dnsmasq.d/wikijs.domain2.tld': 'f5d1c0d32191b2e8077b4cf73d726565', '/etc/resolv.dnsmasq.conf': '124a237d743e5a64dfe2d3b36321ea1f'}
2023-03-31 09:28:42,880: DEBUG - Checking pending configuration which would have been applied for category 'nsswitch'...
2023-03-31 09:28:42,940: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nsswitch/etc/nsswitch.conf' to system conf '/etc/nsswitch.conf'
2023-03-31 09:28:42,957: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:42,958: DEBUG - The configuration is already up-to-date for category 'nsswitch'
2023-03-31 09:28:42,958: DEBUG - Checking pending configuration which would have been applied for category 'fail2ban'...
2023-03-31 09:28:43,019: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.conf' to system conf '/etc/fail2ban/jail.conf'
2023-03-31 09:28:43,020: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:43,020: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d/yunohost.conf' to system conf '/etc/fail2ban/filter.d/yunohost.conf'
2023-03-31 09:28:43,021: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:43,021: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d/postfix-sasl.conf' to system conf '/etc/fail2ban/filter.d/postfix-sasl.conf'
2023-03-31 09:28:43,022: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:43,022: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf' to system conf '/etc/fail2ban/jail.d/yunohost-jails.conf'
2023-03-31 09:28:43,023: DEBUG - > system conf is already up-to-date
2023-03-31 09:28:43,023: DEBUG - The configuration is already up-to-date for category 'fail2ban'
2023-03-31 09:28:43,025: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./01-yunohost" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:43,043: DEBUG - + set -e
2023-03-31 09:28:43,044: DEBUG - + do_post_regen
2023-03-31 09:28:43,045: DEBUG - + regen_conf_files=
2023-03-31 09:28:43,045: DEBUG - + chmod 770 /home/yunohost.backup
2023-03-31 09:28:43,047: DEBUG - + chmod 770 /home/yunohost.backup/archives
2023-03-31 09:28:43,050: DEBUG - + chmod 700 /var/cache/yunohost
2023-03-31 09:28:43,053: DEBUG - + chown root:admins /home/yunohost.backup
2023-03-31 09:28:43,063: DEBUG - + chown root:admins /home/yunohost.backup/archives
2023-03-31 09:28:43,067: DEBUG - + chown root:root /var/cache/yunohost
2023-03-31 09:28:43,075: DEBUG - + chmod 755 /etc/yunohost
2023-03-31 09:28:43,077: DEBUG - + chown -R root:ssl-cert /etc/yunohost/certs
2023-03-31 09:28:43,177: DEBUG - + chmod 750 /etc/yunohost/certs
2023-03-31 09:28:43,179: DEBUG - + find /etc/yunohost/certs/ -type f -exec chmod 640 '{}' ';'
2023-03-31 09:28:43,995: DEBUG - + find /etc/yunohost/certs/ -type d -exec chmod 750 '{}' ';'
2023-03-31 09:28:44,495: DEBUG - + find /etc/cron.daily/yunohost-certificate-renew /etc/cron.daily/yunohost-fetch-apps-catalog /etc/cron.d/yunohost-diagnosis /etc/cron.d/yunohost-dyndns -type f -exec chmod 755 '{}' ';'
2023-03-31 09:28:44,513: DEBUG - + find /etc/cron.d/yunohost-diagnosis /etc/cron.d/yunohost-dyndns -type f -exec chmod 644 '{}' ';'
2023-03-31 09:28:44,526: DEBUG - + find /etc/cron.daily/yunohost-certificate-renew /etc/cron.daily/yunohost-fetch-apps-catalog /etc/cron.d/yunohost-diagnosis /etc/cron.d/yunohost-dyndns -type f -exec chown root:root '{}' ';'
2023-03-31 09:28:44,548: DEBUG - + setfacl -m g:all_users:--- /var/www
2023-03-31 09:28:44,566: DEBUG - + setfacl -m g:all_users:--- /var/log/nginx
2023-03-31 09:28:44,571: DEBUG - + setfacl -m g:all_users:--- /etc/yunohost
2023-03-31 09:28:44,575: DEBUG - + setfacl -m g:all_users:--- /etc/ssowat
2023-03-31 09:28:44,581: DEBUG - ++ yunohost user list --quiet --output-as json
2023-03-31 09:28:44,582: DEBUG - ++ jq -r '.users | .[] | .username'
2023-03-31 09:28:45,297: DEBUG - + for USER in $(yunohost user list --quiet --output-as json | jq -r '.users | .[] | .username')
2023-03-31 09:28:45,297: DEBUG - + '[' '!' -e /home/kirkrehn ']'
2023-03-31 09:28:45,298: DEBUG - + setfacl -m g:all_users:--- /home/kirkrehn
2023-03-31 09:28:45,300: DEBUG - + for USER in $(yunohost user list --quiet --output-as json | jq -r '.users | .[] | .username')
2023-03-31 09:28:45,300: DEBUG - + '[' '!' -e /home/brianserjeant ']'
2023-03-31 09:28:45,301: DEBUG - + setfacl -m g:all_users:--- /home/brianserjeant
2023-03-31 09:28:45,303: DEBUG - + for USER in $(yunohost user list --quiet --output-as json | jq -r '.users | .[] | .username')
2023-03-31 09:28:45,303: DEBUG - + '[' '!' -e /home/nextcloud_admin ']'
2023-03-31 09:28:45,304: DEBUG - + setfacl -m g:all_users:--- /home/nextcloud_admin
2023-03-31 09:28:45,305: DEBUG - + for USER in $(yunohost user list --quiet --output-as json | jq -r '.users | .[] | .username')
2023-03-31 09:28:45,306: DEBUG - + '[' '!' -e /home/svc_wikijs_ldap ']'
2023-03-31 09:28:45,307: DEBUG - + setfacl -m g:all_users:--- /home/svc_wikijs_ldap
2023-03-31 09:28:45,308: DEBUG - + mkdir -p /etc/yunohost/domains
2023-03-31 09:28:45,313: DEBUG - ++ grep -vw mdns.yml
2023-03-31 09:28:45,314: DEBUG - ++ ls /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/regenconf.yml /etc/yunohost/services.yml /etc/yunohost/settings.yml /etc/yunohost/migrations.yaml '/etc/yunohost/*.json' /etc/yunohost/mysql /etc/yunohost/psql
2023-03-31 09:28:45,318: DEBUG - + chown root:root /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/migrations.yaml /etc/yunohost/psql /etc/yunohost/regenconf.yml /etc/yunohost/services.yml /etc/yunohost/settings.yml
2023-03-31 09:28:45,322: DEBUG - ++ ls /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/regenconf.yml /etc/yunohost/services.yml /etc/yunohost/settings.yml /etc/yunohost/migrations.yaml '/etc/yunohost/*.json' /etc/yunohost/mysql /etc/yunohost/psql
2023-03-31 09:28:45,327: DEBUG - + chmod 600 /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/migrations.yaml /etc/yunohost/psql /etc/yunohost/regenconf.yml /etc/yunohost/services.yml /etc/yunohost/settings.yml
2023-03-31 09:28:45,329: DEBUG - + [[ ! -e /etc/yunohost/hooks.d ]]
2023-03-31 09:28:45,330: DEBUG - + chown root /etc/yunohost/hooks.d
2023-03-31 09:28:45,335: DEBUG - + chmod 700 /etc/yunohost/hooks.d
2023-03-31 09:28:45,338: DEBUG - + [[ ! -e /etc/yunohost/apps ]]
2023-03-31 09:28:45,339: DEBUG - + chown root /etc/yunohost/apps
2023-03-31 09:28:45,342: DEBUG - + chmod 700 /etc/yunohost/apps
2023-03-31 09:28:45,345: DEBUG - + [[ ! -e /etc/yunohost/domains ]]
2023-03-31 09:28:45,345: DEBUG - + chown root /etc/yunohost/domains
2023-03-31 09:28:45,348: DEBUG - + chmod 700 /etc/yunohost/domains
2023-03-31 09:28:45,351: DEBUG - + grep -q '^ssh.app:' /etc/group
2023-03-31 09:28:45,354: DEBUG - + grep -q '^sftp.app:' /etc/group
2023-03-31 09:28:45,358: DEBUG - + systemctl
2023-03-31 09:28:45,359: DEBUG - + grep -q ntp.service
2023-03-31 09:28:45,372: DEBUG - + [[ ! '' =~ ntp\.service\.d/ynh-override\.conf ]]
2023-03-31 09:28:45,373: DEBUG - + [[ ! '' =~ nftables\.service\.d/ynh-override\.conf ]]
2023-03-31 09:28:45,374: DEBUG - + [[ ! '' =~ login\.conf\.d/ynh-override\.conf ]]
2023-03-31 09:28:45,374: DEBUG - + [[ ! '' =~ yunohost-firewall\.service ]]
2023-03-31 09:28:45,375: DEBUG - + [[ ! '' =~ yunohost-api\.service ]]
2023-03-31 09:28:45,375: DEBUG - + [[ '' =~ yunoprompt\.service ]]
2023-03-31 09:28:45,376: DEBUG - + [[ '' =~ proc-hidepid\.service ]]
2023-03-31 09:28:45,376: DEBUG - + readlink -f /etc/dpkg/origins/default
2023-03-31 09:28:45,377: DEBUG - + grep -q debian
2023-03-31 09:28:45,377: DEBUG - + test -e /etc/yunohost/installed
2023-03-31 09:28:45,378: DEBUG - + test -e /etc/profile.d/check_yunohost_is_installed.sh
2023-03-31 09:28:46,381: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./02-ssl" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:46,398: DEBUG - + set -e
2023-03-31 09:28:46,399: DEBUG - + ssl_dir=/usr/share/yunohost/ssl
2023-03-31 09:28:46,399: DEBUG - + template_dir=/usr/share/yunohost/conf/ssl/
2023-03-31 09:28:46,400: DEBUG - + ynh_ca=/etc/yunohost/certs/yunohost.org/ca.pem
2023-03-31 09:28:46,400: DEBUG - + ynh_crt=/etc/yunohost/certs/yunohost.org/crt.pem
2023-03-31 09:28:46,400: DEBUG - + ynh_key=**********
2023-03-31 09:28:46,401: DEBUG - + do_post_regen
2023-03-31 09:28:46,402: DEBUG - + regen_conf_files=
2023-03-31 09:28:46,404: DEBUG - ++ openssl x509 -in /etc/yunohost/certs/yunohost.org/ca.pem -text
2023-03-31 09:28:46,405: DEBUG - ++ grep Issuer
2023-03-31 09:28:46,406: DEBUG - ++ awk '{print $4}'
2023-03-31 09:28:46,407: DEBUG - ++ tr , '\n'
2023-03-31 09:28:46,418: DEBUG - + current_local_ca_domain=domain2.tld
2023-03-31 09:28:46,419: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-31 09:28:46,421: DEBUG - + main_domain=maindomain.tld
2023-03-31 09:28:46,422: DEBUG - + '[' -e /usr/share/yunohost/yunohost-config/ssl/yunoCA ']'
2023-03-31 09:28:46,423: DEBUG - + mkdir -p /usr/share/yunohost/ssl/ca /usr/share/yunohost/ssl/certs /usr/share/yunohost/ssl/crl /usr/share/yunohost/ssl/newcerts
2023-03-31 09:28:46,429: DEBUG - + chown root:root /usr/share/yunohost/ssl
2023-03-31 09:28:46,432: DEBUG - + chmod 750 /usr/share/yunohost/ssl
2023-03-31 09:28:46,435: DEBUG - + chmod -R o-rwx /usr/share/yunohost/ssl
2023-03-31 09:28:46,444: DEBUG - + chmod o+x /usr/share/yunohost/ssl/certs
2023-03-31 09:28:46,446: DEBUG - + chmod o+r /usr/share/yunohost/ssl/certs/yunohost_crt.pem
2023-03-31 09:28:46,449: DEBUG - + [[ domain2.tld != \k\i\r\k\r\e\h\n\.\m\y\d\d\n\s\.\m\e ]]
2023-03-31 09:28:46,450: DEBUG - + regen_local_ca maindomain.tld
2023-03-31 09:28:46,450: DEBUG - + domain=maindomain.tld
2023-03-31 09:28:46,450: DEBUG - + echo -e '\n# Creating local certification authority with domain=maindomain.tld\n'
2023-03-31 09:28:46,451: DEBUG - 
2023-03-31 09:28:46,451: DEBUG - # Creating local certification authority with domain=maindomain.tld
2023-03-31 09:28:46,452: DEBUG - 
2023-03-31 09:28:46,452: DEBUG - + mkdir -p /etc/yunohost/certs/yunohost.org
2023-03-31 09:28:46,453: DEBUG - + mkdir -p /usr/share/yunohost/ssl/ca /usr/share/yunohost/ssl/certs /usr/share/yunohost/ssl/crl /usr/share/yunohost/ssl/newcerts
2023-03-31 09:28:46,456: DEBUG - + pushd /usr/share/yunohost/ssl
2023-03-31 09:28:46,456: DEBUG - /usr/share/yunohost/ssl /usr/share/yunohost/hooks/conf_regen
2023-03-31 09:28:46,457: DEBUG - + RANDFILE=.rnd
2023-03-31 09:28:46,457: DEBUG - + openssl rand -hex 19
2023-03-31 09:28:46,465: DEBUG - + rm -f index.txt
2023-03-31 09:28:46,468: DEBUG - + touch index.txt
2023-03-31 09:28:46,470: DEBUG - + cp /usr/share/yunohost/conf/ssl//openssl.cnf openssl.ca.cnf
2023-03-31 09:28:46,474: DEBUG - + sed -i s/yunohost.org/maindomain.tld/g openssl.ca.cnf
2023-03-31 09:28:46,479: DEBUG - + openssl req -x509 -new -config openssl.ca.cnf -days 3650 -out ca/cacert.pem -keyout ca/cakey.pem -nodes -batch -subj /CN=maindomain.tld/O=kirkrehn.myddns
2023-03-31 09:28:46,491: DEBUG - Generating a RSA private key
2023-03-31 09:28:46,582: DEBUG - ..........................+++++
2023-03-31 09:28:46,835: DEBUG - .............................................................................+++++
2023-03-31 09:28:46,836: DEBUG - writing new private key to 'ca/cakey.pem'
2023-03-31 09:28:46,836: DEBUG - -----
2023-03-31 09:28:46,845: DEBUG - + chmod 640 ca/cacert.pem
2023-03-31 09:28:46,847: DEBUG - + chmod 640 ca/cakey.pem
2023-03-31 09:28:46,849: DEBUG - + cp ca/cacert.pem /etc/yunohost/certs/yunohost.org/ca.pem
2023-03-31 09:28:46,856: DEBUG - + ln -sf /etc/yunohost/certs/yunohost.org/ca.pem /etc/ssl/certs/ca-yunohost_crt.pem
2023-03-31 09:28:46,859: DEBUG - + update-ca-certificates
2023-03-31 09:28:46,868: DEBUG - Updating certificates in /etc/ssl/certs...
2023-03-31 09:28:47,971: DEBUG - 0 added, 0 removed; done.
2023-03-31 09:28:47,974: DEBUG - Running hooks in /etc/ca-certificates/update.d...
2023-03-31 09:28:47,977: DEBUG - done.
2023-03-31 09:28:47,982: DEBUG - + popd
2023-03-31 09:28:47,982: DEBUG - /usr/share/yunohost/hooks/conf_regen
2023-03-31 09:28:47,983: DEBUG - + ln -sf /etc/yunohost/certs/maindomain.tld/crt.pem /etc/ssl/certs/yunohost_crt.pem
2023-03-31 09:28:47,984: DEBUG - + ln -sf /etc/yunohost/certs/maindomain.tld/key.pem /etc/ssl/private/yunohost_key.pem
2023-03-31 09:28:48,988: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./03-ssh" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:49,005: DEBUG - + set -e
2023-03-31 09:28:49,006: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:49,008: DEBUG - +++ set +o
2023-03-31 09:28:49,009: DEBUG - +++ grep xtrace
2023-03-31 09:28:49,012: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:49,013: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:49,053: DEBUG - + do_post_regen
2023-03-31 09:28:49,054: DEBUG - + regen_conf_files=
2023-03-31 09:28:49,055: DEBUG - + return 0
2023-03-31 09:28:50,062: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./06-slapd" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:50,103: DEBUG - + set -e
2023-03-31 09:28:50,106: DEBUG - + tmp_backup_dir_file=/root/slapd-backup-dir.txt
2023-03-31 09:28:50,108: DEBUG - + config=/usr/share/yunohost/conf/slapd/config.ldif
2023-03-31 09:28:50,109: DEBUG - + db_init=/usr/share/yunohost/conf/slapd/db_init.ldif
2023-03-31 09:28:50,111: DEBUG - + do_post_regen
2023-03-31 09:28:50,112: DEBUG - + regen_conf_files=
2023-03-31 09:28:50,115: DEBUG - Enforce permissions on ldap/slapd directories and certs ...
2023-03-31 09:28:50,117: DEBUG - + usermod -aG ssl-cert openldap
2023-03-31 09:28:50,164: DEBUG - + chown -R openldap:openldap /etc/ldap/schema/
2023-03-31 09:28:50,183: DEBUG - + chown -R openldap:openldap /etc/ldap/slapd.d/
2023-03-31 09:28:50,189: DEBUG - + '[' -e /etc/sudo-ldap.conf ']'
2023-03-31 09:28:50,191: DEBUG - + grep -q '^/etc/systemd/system/slapd.service.d/ynh-override.conf$'
2023-03-31 09:28:50,192: DEBUG - + sed 's/,/\n/g'
2023-03-31 09:28:50,197: DEBUG - + slapcat -H ldap:///cn=admins,ou=groups,dc=yunohost,dc=org
2023-03-31 09:28:50,197: DEBUG - + grep -q cn=admins,ou=groups,dc=yunohost,dc=org
2023-03-31 09:28:50,241: DEBUG - + '[' -z '' ']'
2023-03-31 09:28:51,245: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./09-nslcd" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:51,267: DEBUG - + set -e
2023-03-31 09:28:51,268: DEBUG - + do_post_regen
2023-03-31 09:28:51,269: DEBUG - + regen_conf_files=
2023-03-31 09:28:51,269: DEBUG - + [[ -z '' ]]
2023-03-31 09:28:52,272: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./10-apt" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:52,289: DEBUG - + set -e
2023-03-31 09:28:52,290: DEBUG - + readonly YNH_DEFAULT_PHP_VERSION=7.4
2023-03-31 09:28:52,291: DEBUG - + YNH_DEFAULT_PHP_VERSION=7.4
2023-03-31 09:28:52,291: DEBUG - + do_post_regen
2023-03-31 09:28:52,292: DEBUG - + regen_conf_files=
2023-03-31 09:28:52,292: DEBUG - + [[ ! -s /etc/apt/trusted.gpg.d/extra_php_version.gpg ]]
2023-03-31 09:28:52,293: DEBUG - + test -e /usr/bin/php7.4
2023-03-31 09:28:52,293: DEBUG - + update-alternatives --set php /usr/bin/php7.4
2023-03-31 09:28:53,296: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./12-metronome" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:53,313: DEBUG - + set -e
2023-03-31 09:28:53,315: DEBUG - + dpkg --list
2023-03-31 09:28:53,316: DEBUG - + grep -q 'ii *metronome '
2023-03-31 09:28:53,355: DEBUG - + do_post_regen
2023-03-31 09:28:53,355: DEBUG - + regen_conf_files=
2023-03-31 09:28:53,357: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-31 09:28:53,359: DEBUG - + main_domain=maindomain.tld
2023-03-31 09:28:53,359: DEBUG - + for domain in $YNH_MAIN_DOMAINS
2023-03-31 09:28:53,360: DEBUG - + mkdir -p /var/lib/metronome/domain2%2etld/pep
2023-03-31 09:28:53,364: DEBUG - + mkdir -p /var/xmpp-upload/domain2.tld/upload
2023-03-31 09:28:53,367: DEBUG - + chmod g+s /var/xmpp-upload/domain2.tld/upload
2023-03-31 09:28:53,370: DEBUG - + for domain in $YNH_MAIN_DOMAINS
2023-03-31 09:28:53,371: DEBUG - + mkdir -p /var/lib/metronome/maindomain%2etld/pep
2023-03-31 09:28:53,374: DEBUG - + mkdir -p /var/xmpp-upload/maindomain.tld/upload
2023-03-31 09:28:53,378: DEBUG - + chmod g+s /var/xmpp-upload/maindomain.tld/upload
2023-03-31 09:28:53,381: DEBUG - + for domain in $YNH_MAIN_DOMAINS
2023-03-31 09:28:53,382: DEBUG - + mkdir -p /var/lib/metronome/domain3%2etld/pep
2023-03-31 09:28:53,385: DEBUG - + mkdir -p /var/xmpp-upload/domain3.tld/upload
2023-03-31 09:28:53,388: DEBUG - + chmod g+s /var/xmpp-upload/domain3.tld/upload
2023-03-31 09:28:53,390: DEBUG - + '[' '!' -e /var/xmpp-upload ']'
2023-03-31 09:28:53,391: DEBUG - + chown -R metronome:www-data /var/xmpp-upload/
2023-03-31 09:28:53,406: DEBUG - + '[' '!' -e /var/xmpp-upload ']'
2023-03-31 09:28:53,407: DEBUG - + chmod 750 /var/xmpp-upload/
2023-03-31 09:28:53,408: DEBUG - + usermod -aG ssl-cert metronome
2023-03-31 09:28:53,436: DEBUG - + chown -R metronome: /var/lib/metronome/
2023-03-31 09:28:53,452: DEBUG - + chown -R metronome: /etc/metronome/conf.d/
2023-03-31 09:28:53,456: DEBUG - ++ ls '/etc/metronome/conf.d/*.cfg.lua'
2023-03-31 09:28:53,460: DEBUG - + [[ -z '' ]]
2023-03-31 09:28:53,461: DEBUG - + systemctl is-enabled metronome
2023-03-31 09:28:54,464: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:28:54,487: DEBUG - + set -e
2023-03-31 09:28:54,488: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:54,489: DEBUG - +++ set +o
2023-03-31 09:28:54,489: DEBUG - +++ grep xtrace
2023-03-31 09:28:54,493: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:54,494: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:54,535: DEBUG - + do_post_regen
2023-03-31 09:28:54,536: DEBUG - + regen_conf_files=
2023-03-31 09:28:54,537: DEBUG - + '[' -z '' ']'
2023-03-31 09:28:55,544: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./19-postfix" post \'\' \'\' /etc/postfix/main.cf,/etc/default/postsrsd 7>&1']'
2023-03-31 09:28:55,575: DEBUG - + set -e
2023-03-31 09:28:55,576: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:55,580: DEBUG - +++ set +o
2023-03-31 09:28:55,581: DEBUG - +++ grep xtrace
2023-03-31 09:28:55,586: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:55,588: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:55,664: DEBUG - + do_post_regen /etc/postfix/main.cf,/etc/default/postsrsd
2023-03-31 09:28:55,665: DEBUG - + regen_conf_files=/etc/postfix/main.cf,/etc/default/postsrsd
2023-03-31 09:28:55,665: DEBUG - + chown postfix /etc/postfix
2023-03-31 09:28:55,673: DEBUG - + '[' -e /etc/postfix/sasl_passwd ']'
2023-03-31 09:28:55,673: DEBUG - + chmod 750 /etc/postfix/sasl_passwd /etc/postfix/sasl_passwd.db
2023-03-31 09:28:55,676: DEBUG - + chown postfix:root /etc/postfix/sasl_passwd /etc/postfix/sasl_passwd.db
2023-03-31 09:28:55,684: DEBUG - + postmap /etc/postfix/sasl_passwd
2023-03-31 09:28:55,729: DEBUG - + postmap -F hash:/etc/postfix/sni
2023-03-31 09:28:55,765: DEBUG - + [[ -z /etc/postfix/main.cf,/etc/default/postsrsd ]]
2023-03-31 09:28:55,766: DEBUG - + systemctl restart postfix
2023-03-31 09:28:57,220: DEBUG - + systemctl restart postsrsd
2023-03-31 09:28:58,224: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./25-dovecot" post \'\' \'\' /etc/dovecot/dovecot.conf 7>&1']'
2023-03-31 09:28:58,241: DEBUG - + set -e
2023-03-31 09:28:58,242: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:28:58,244: DEBUG - +++ set +o
2023-03-31 09:28:58,244: DEBUG - +++ grep xtrace
2023-03-31 09:28:58,248: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:28:58,249: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:28:58,289: DEBUG - + do_post_regen /etc/dovecot/dovecot.conf
2023-03-31 09:28:58,290: DEBUG - + regen_conf_files=/etc/dovecot/dovecot.conf
2023-03-31 09:28:58,290: DEBUG - + mkdir -p /etc/dovecot/yunohost.d/pre-ext.d
2023-03-31 09:28:58,293: DEBUG - + mkdir -p /etc/dovecot/yunohost.d/post-ext.d
2023-03-31 09:28:58,296: DEBUG - + id vmail
2023-03-31 09:28:58,321: DEBUG - + '[' '!' -e /home/vmail ']'
2023-03-31 09:28:58,322: DEBUG - + chown -R vmail:mail /etc/dovecot/global_script
2023-03-31 09:28:58,329: DEBUG - + chmod 770 /etc/dovecot/global_script
2023-03-31 09:28:58,332: DEBUG - + chown root:mail /var/mail
2023-03-31 09:28:58,335: DEBUG - + chmod 1775 /var/mail
2023-03-31 09:28:58,337: DEBUG - + '[' -z /etc/dovecot/dovecot.conf ']'
2023-03-31 09:28:58,338: DEBUG - + [[ /etc/dovecot/dovecot.conf =~ dovecot\.sieve ]]
2023-03-31 09:28:58,339: DEBUG - + systemctl restart dovecot
2023-03-31 09:29:00,342: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./31-rspamd" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:00,360: DEBUG - + set -e
2023-03-31 09:29:00,361: DEBUG - + do_post_regen
2023-03-31 09:29:00,361: DEBUG - + mkdir -p /etc/dkim
2023-03-31 09:29:00,365: DEBUG - + chown _rspamd /etc/dkim
2023-03-31 09:29:00,374: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-31 09:29:00,376: DEBUG - ++ jq -r '.domains[]'
2023-03-31 09:29:00,376: DEBUG - ++ tr '\n' ' '
2023-03-31 09:29:01,234: DEBUG - + domain_list='energy.domain2.tld firefly.domain2.tld home.domain2.tld homeassistant.domain2.tld nextcloud.domain2.tld webmail.domain2.tld wikijs.domain2.tld energy.maindomain.tld grocy.maindomain.tld home.maindomain.tld homeassistant.maindomain.tld mqtt.maindomain.tld nextcloud.maindomain.tld nodered.maindomain.tld owntracks.maindomain.tld webmail.maindomain.tld wikijs.maindomain.tld domain3.tld homeassistant.domain3.tld wikijs.domain3.tld '
2023-03-31 09:29:01,236: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,237: DEBUG - + domain_key=**********
2023-03-31 09:29:01,237: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,238: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,238: DEBUG - + domain_key=**********
2023-03-31 09:29:01,239: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,239: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,239: DEBUG - + domain_key=**********
2023-03-31 09:29:01,240: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,240: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,241: DEBUG - + domain_key=**********
2023-03-31 09:29:01,241: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,242: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,242: DEBUG - + domain_key=**********
2023-03-31 09:29:01,242: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,243: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,243: DEBUG - + domain_key=**********
2023-03-31 09:29:01,244: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,244: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,245: DEBUG - + domain_key=**********
2023-03-31 09:29:01,245: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,246: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,246: DEBUG - + domain_key=**********
2023-03-31 09:29:01,247: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,247: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,247: DEBUG - + domain_key=**********
2023-03-31 09:29:01,248: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,248: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,249: DEBUG - + domain_key=**********
2023-03-31 09:29:01,249: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,249: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,250: DEBUG - + domain_key=**********
2023-03-31 09:29:01,250: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,251: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,251: DEBUG - + domain_key=**********
2023-03-31 09:29:01,252: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,252: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,253: DEBUG - + domain_key=**********
2023-03-31 09:29:01,253: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,254: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,254: DEBUG - + domain_key=**********
2023-03-31 09:29:01,254: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,255: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,255: DEBUG - + domain_key=**********
2023-03-31 09:29:01,255: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,256: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,256: DEBUG - + domain_key=**********
2023-03-31 09:29:01,256: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,256: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,257: DEBUG - + domain_key=**********
2023-03-31 09:29:01,257: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,257: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,257: DEBUG - + domain_key=**********
2023-03-31 09:29:01,258: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,258: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,258: DEBUG - + domain_key=**********
2023-03-31 09:29:01,259: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,259: DEBUG - + for domain in $domain_list
2023-03-31 09:29:01,259: DEBUG - + domain_key=**********
2023-03-31 09:29:01,260: DEBUG - + '[' '!' -f ********** ']'
2023-03-31 09:29:01,260: DEBUG - + chown _rspamd /etc/dkim/adguard.maindomain.tld.mail.key /etc/dkim/adguard.domain2.tld.mail.key /etc/dkim/doc.maindomain.tld.mail.key ********** ********** ********** ********** /etc/dkim/homeassistant.kirklabs.xyz.mail.key ********** ********** ********** ********** ********** /etc/dkim/kirklabs.noho.st.mail.key /etc/dkim/kirklabs.nohost.me.mail.key /etc/dkim/kirklabs.nohost.st.mail.key /etc/dkim/kirklabs.xyz.mail.key ********** /etc/dkim/maindomain.tld.mail.key /etc/dkim/domain2.tld.mail.key /etc/dkim/librex.kirkehn.myddns.me.mail.key /etc/dkim/librex.maindomain.tld.mail.key /etc/dkim/matrix.maindomain.tld.mail.key ********** ********** ********** ********** ********** /etc/dkim/qbittorrent.maindomain.tld.mail.key /etc/dkim/s3.maindomain.tld.mail.key /etc/dkim/s3.domain2.tld.mail.key /etc/dkim/standard.maindomain.tld.mail.key /etc/dkim/tiddly.maindomain.tld.mail.key ********** ********** ********** ********** ********** /etc/dkim/wiki.maindomain.tld.mail.key /etc/dkim/wordpress.maindomain.tld.mail.key /etc/dkim/yunokirk.nohost.me.mail.key /etc/dkim/yunokirk.ynh.fr.mail.key
2023-03-31 09:29:01,261: DEBUG - + chmod 400 /etc/dkim/adguard.maindomain.tld.mail.key /etc/dkim/adguard.domain2.tld.mail.key /etc/dkim/doc.maindomain.tld.mail.key ********** ********** ********** ********** /etc/dkim/homeassistant.kirklabs.xyz.mail.key ********** ********** ********** ********** ********** /etc/dkim/kirklabs.noho.st.mail.key /etc/dkim/kirklabs.nohost.me.mail.key /etc/dkim/kirklabs.nohost.st.mail.key /etc/dkim/kirklabs.xyz.mail.key ********** /etc/dkim/maindomain.tld.mail.key /etc/dkim/domain2.tld.mail.key /etc/dkim/librex.kirkehn.myddns.me.mail.key /etc/dkim/librex.maindomain.tld.mail.key /etc/dkim/matrix.maindomain.tld.mail.key ********** ********** ********** ********** ********** /etc/dkim/qbittorrent.maindomain.tld.mail.key /etc/dkim/s3.maindomain.tld.mail.key /etc/dkim/s3.domain2.tld.mail.key /etc/dkim/standard.maindomain.tld.mail.key /etc/dkim/tiddly.maindomain.tld.mail.key ********** ********** ********** ********** ********** /etc/dkim/wiki.maindomain.tld.mail.key /etc/dkim/wordpress.maindomain.tld.mail.key /etc/dkim/yunokirk.nohost.me.mail.key /etc/dkim/yunokirk.ynh.fr.mail.key
2023-03-31 09:29:01,262: DEBUG - + '[' '!' -e /var/log/rspamd ']'
2023-03-31 09:29:01,262: DEBUG - + chown -R _rspamd:_rspamd /var/log/rspamd
2023-03-31 09:29:01,263: DEBUG - + regen_conf_files=
2023-03-31 09:29:01,263: DEBUG - + '[' -z '' ']'
2023-03-31 09:29:02,266: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./34-mysql" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:02,283: DEBUG - + set -e
2023-03-31 09:29:02,284: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:29:02,286: DEBUG - +++ set +o
2023-03-31 09:29:02,287: DEBUG - +++ grep xtrace
2023-03-31 09:29:02,291: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:29:02,292: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:29:02,333: DEBUG - + dpkg --list
2023-03-31 09:29:02,334: DEBUG - + grep -q 'ii *mariadb-server '
2023-03-31 09:29:02,374: DEBUG - + do_post_regen
2023-03-31 09:29:02,374: DEBUG - + regen_conf_files=
2023-03-31 09:29:02,375: DEBUG - + [[ ! -d /var/lib/mysql/mysql ]]
2023-03-31 09:29:02,375: DEBUG - + '[' '!' -e /etc/systemd/system/mysql.service ']'
2023-03-31 09:29:02,376: DEBUG - + systemctl stop mysql -q
2023-03-31 09:29:08,883: DEBUG - + systemctl disable mysql -q
2023-03-31 09:29:09,399: DEBUG - + systemctl disable mariadb -q
2023-03-31 09:29:10,375: WARNING - insserv: warning: current start runlevel(s) (empty) of script `mariadb' overrides LSB defaults (2 3 4 5).
2023-03-31 09:29:10,377: WARNING - insserv: warning: current stop runlevel(s) (0 1 2 3 4 5 6) of script `mariadb' overrides LSB defaults (0 1 6).
2023-03-31 09:29:11,422: DEBUG - + systemctl enable mariadb -q
2023-03-31 09:29:11,512: WARNING - insserv: warning: current start runlevel(s) (empty) of script `mariadb' overrides LSB defaults (2 3 4 5).
2023-03-31 09:29:11,514: WARNING - insserv: warning: current stop runlevel(s) (0 1 2 3 4 5 6) of script `mariadb' overrides LSB defaults (0 1 6).
2023-03-31 09:29:13,261: DEBUG - + systemctl is-active mariadb -q
2023-03-31 09:29:13,271: DEBUG - + systemctl start mariadb
2023-03-31 09:29:13,939: DEBUG - + [[ -z '' ]]
2023-03-31 09:29:14,942: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./35-postgresql" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:14,959: DEBUG - + set -e
2023-03-31 09:29:14,961: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:29:14,963: DEBUG - +++ set +o
2023-03-31 09:29:14,965: DEBUG - +++ grep xtrace
2023-03-31 09:29:14,967: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:29:14,968: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:29:15,011: DEBUG - + dpkg --list
2023-03-31 09:29:15,012: DEBUG - + grep -q 'ii *postgresql-13 '
2023-03-31 09:29:15,053: DEBUG - + '[' '!' -e /etc/postgresql/13 ']'
2023-03-31 09:29:15,054: DEBUG - + do_post_regen
2023-03-31 09:29:15,055: DEBUG - + systemctl is-active postgresql@13-main -q
2023-03-31 09:29:15,065: DEBUG - + systemctl is-enabled postgresql -q
2023-03-31 09:29:15,079: DEBUG - + '[' '!' -f /etc/yunohost/psql ']'
2023-03-31 09:29:15,081: DEBUG - ++ cat /etc/yunohost/psql
2023-03-31 09:29:15,083: DEBUG - + '[' -z ********** ']'
2023-03-31 09:29:15,084: DEBUG - + '[' '!' -e /etc/yunohost/psql ']'
2023-03-31 09:29:15,084: DEBUG - + chown root:postgres /etc/yunohost/psql
2023-03-31 09:29:15,093: DEBUG - + chmod 440 /etc/yunohost/psql
2023-03-31 09:29:15,097: DEBUG - ++ cat /etc/yunohost/psql
2023-03-31 09:29:15,100: DEBUG - + sudo --login --user=postgres psql '-cALTER user postgres WITH PASSWORD '\''**********'\''' postgres
2023-03-31 09:29:15,197: DEBUG - 
2023-03-31 09:29:15,199: DEBUG - Wi-Fi is currently blocked by rfkill.
2023-03-31 09:29:15,201: DEBUG - Use raspi-config to set the country before use.
2023-03-31 09:29:15,202: DEBUG - 
2023-03-31 09:29:15,435: DEBUG - ALTER ROLE
2023-03-31 09:29:15,445: DEBUG - + local pg_hba=/etc/postgresql/13/main/pg_hba.conf
2023-03-31 09:29:15,446: DEBUG - + ynh_replace_string '--match_string=local\(\s*\)all\(\s*\)all\(\s*\)peer' '--replace_string=local\1all\2all\3md5' --target_file=/etc/postgresql/13/main/pg_hba.conf
2023-03-31 09:29:15,587: DEBUG - + sed --in-place 'slocal\(\s*\)all\(\s*\)all\(\s*\)peerlocal\1all\2all\3md5g' /etc/postgresql/13/main/pg_hba.conf
2023-03-31 09:29:15,594: DEBUG - + ynh_systemd_action --service_name=postgresql --action=reload
2023-03-31 09:29:15,781: DEBUG - + service_name=postgresql
2023-03-31 09:29:15,782: DEBUG - + action=reload
2023-03-31 09:29:15,782: DEBUG - + line_match=
2023-03-31 09:29:15,783: DEBUG - + length=20
2023-03-31 09:29:15,784: DEBUG - + log_path=/var/log/postgresql/postgresql.log
2023-03-31 09:29:15,785: DEBUG - + timeout=300
2023-03-31 09:29:15,785: DEBUG - + '[' reload == stop ']'
2023-03-31 09:29:15,787: DEBUG - + '[' reload == reload ']'
2023-03-31 09:29:15,787: DEBUG - + action=reload-or-restart
2023-03-31 09:29:15,788: DEBUG - ++ date --utc --rfc-3339=seconds
2023-03-31 09:29:15,788: DEBUG - ++ cut -d+ -f1
2023-03-31 09:29:15,789: DEBUG - + local 'time_start=2023-03-31 08:29:15 UTC'
2023-03-31 09:29:15,789: DEBUG - + systemctl reload-or-restart postgresql
2023-03-31 09:29:16,978: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./36-redis" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:16,995: DEBUG - + do_post_regen
2023-03-31 09:29:16,996: DEBUG - + chown -R redis:adm /var/log/redis
2023-03-31 09:29:17,999: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./37-mdns" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:18,017: DEBUG - + set -e
2023-03-31 09:29:18,018: DEBUG - + do_post_regen
2023-03-31 09:29:18,019: DEBUG - + regen_conf_files=
2023-03-31 09:29:18,020: DEBUG - + chown mdns:mdns /etc/yunohost/mdns.yml
2023-03-31 09:29:18,035: DEBUG - + sed 's/,/\n/g'
2023-03-31 09:29:18,035: DEBUG - + grep -q '^/etc/systemd/system/yunomdns.service$'
2023-03-31 09:29:18,037: DEBUG - + [[ -e /etc/avahi/avahi-daemon.conf ]]
2023-03-31 09:29:18,040: DEBUG - + grep -q yunohost /etc/avahi/avahi-daemon.conf
2023-03-31 09:29:18,045: DEBUG - + [[ -z '' ]]
2023-03-31 09:29:19,048: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./43-dnsmasq" post \'\' \'\' /etc/resolv.dnsmasq.conf 7>&1']'
2023-03-31 09:29:19,065: DEBUG - + set -e
2023-03-31 09:29:19,066: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:29:19,067: DEBUG - +++ set +o
2023-03-31 09:29:19,068: DEBUG - +++ grep xtrace
2023-03-31 09:29:19,072: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:29:19,073: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:29:19,113: DEBUG - + do_post_regen /etc/resolv.dnsmasq.conf
2023-03-31 09:29:19,114: DEBUG - + regen_conf_files=/etc/resolv.dnsmasq.conf
2023-03-31 09:29:19,115: DEBUG - + chown 644 /etc/resolv.dnsmasq.conf
2023-03-31 09:29:19,122: DEBUG - + grep -q -E '^ *(domain|search)' /run/resolvconf/resolv.conf
2023-03-31 09:29:19,127: DEBUG - + grep -q -E '^ *(domain|search)' '/run/resolvconf/interface/*.dhclient'
2023-03-31 09:29:19,130: DEBUG - + grep -q '^supersede domain-name "";' /etc/dhcp/dhclient.conf
2023-03-31 09:29:19,137: DEBUG - + grep -q '^supersede domain-search "";' /etc/dhcp/dhclient.conf
2023-03-31 09:29:19,141: DEBUG - + grep -q '^supersede search "";' /etc/dhcp/dhclient.conf
2023-03-31 09:29:19,145: DEBUG - + systemctl restart resolvconf
2023-03-31 09:29:19,194: DEBUG - ++ hostname -s
2023-03-31 09:29:19,198: DEBUG - + short_hostname=kirkrehn
2023-03-31 09:29:19,199: DEBUG - + grep -q '127.0.0.1.*kirkrehn' /etc/hosts
2023-03-31 09:29:19,202: DEBUG - + [[ -n /etc/resolv.dnsmasq.conf ]]
2023-03-31 09:29:19,203: DEBUG - + for SERVICE in systemd-resolved bind9
2023-03-31 09:29:19,203: DEBUG - + systemctl is-enabled systemd-resolved
2023-03-31 09:29:19,227: DEBUG - + systemctl is-active systemd-resolved
2023-03-31 09:29:19,243: DEBUG - + for SERVICE in systemd-resolved bind9
2023-03-31 09:29:19,244: DEBUG - + systemctl is-enabled bind9
2023-03-31 09:29:19,253: DEBUG - + systemctl is-active bind9
2023-03-31 09:29:19,262: DEBUG - + systemctl restart dnsmasq
2023-03-31 09:29:21,270: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./46-nsswitch" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:21,308: DEBUG - + set -e
2023-03-31 09:29:21,311: DEBUG - + do_post_regen
2023-03-31 09:29:21,312: DEBUG - + regen_conf_files=
2023-03-31 09:29:21,313: DEBUG - + [[ -z '' ]]
2023-03-31 09:29:22,321: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./52-fail2ban" post \'\' \'\' \'\' 7>&1']'
2023-03-31 09:29:22,360: DEBUG - + set -e
2023-03-31 09:29:22,363: DEBUG - + . /usr/share/yunohost/helpers
2023-03-31 09:29:22,364: DEBUG - +++ set +o
2023-03-31 09:29:22,367: DEBUG - +++ grep xtrace
2023-03-31 09:29:22,377: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-31 09:29:22,378: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-31 09:29:22,438: DEBUG - + do_post_regen
2023-03-31 09:29:22,439: DEBUG - + regen_conf_files=
2023-03-31 09:29:22,439: DEBUG - + [[ -z '' ]]
2023-03-31 09:29:23,445: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230331-082746-regen_conf-all" style="text-decoration:underline">Regenerate system configurations 'all'</a>'
2023-03-31 09:29:23,507: INFO - Updating aliases for group 'admins'
2023-03-31 09:29:23,843: DEBUG - The permission database has been resynchronized
2023-03-31 09:29:24,315: DEBUG - SSOwat configuration regenerated
2023-03-31 09:29:24,331: SUCCESS - Group 'admins' updated
2023-03-31 09:29:24,334: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230331-082923-user_group_update-admins" style="text-decoration:underline">Update 'admins' group</a>'
2023-03-31 09:29:24,357: SUCCESS - The main domain has been changed
```

### reset lost root password

`yunohost tools rootpw`

