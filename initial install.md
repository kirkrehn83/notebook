---
share: true
---
> [!INFO] synopsis
> initial setup on new domain and server

## faq

| **item** | **description** |
| --- | --- |
| url | kirkrehn.myddns.me/yunohost/admin/#/login |
| local url | yunohost.local |
| ssh access | root@yunohost.local |
| ssh root user | root |
| web root user | admin |
| root/admin password | kirkster |
| user account | kirkrehn |
| user password | kirkster |
| user e-mail | kirkrehn@kirkrehn.myddns.me |
| mail forward to | kirk@kirkrehn.online |

## post-install

### run yunohost post-install


```sh
args:
  domain: maindomain.tld
  force_diskspace: false
  force_password: false
  ignore_dyndns: false
ended_at: 2023-03-30 19:54:36.310071
error: null
interface: api
operation: tools_postinstall
parent: null
related_to:
- - domain
  - maindomain.tld
started_at: 2023-03-30 19:52:47.265989
success: true
yunohost_version: 11.0.10.2

============

2023-03-30 20:52:47,289: INFO - Installing YunoHost...
2023-03-30 20:52:47,307: DEBUG - initializing ldap interface
2023-03-30 20:52:47,694: DEBUG - Can't load /usr/share/yunohost/ssl/.rnd into RNG
547686074880:error:2406F079:random number generator:RAND_load_file:Cannot open file:../crypto/rand/randfile.c:98:Filename=/usr/share/yunohost/ssl/.rnd
Generating a RSA private key
.......................................................+++++
...........................................+++++
writing new private key to '/etc/yunohost/certs//maindomain.tld-history/20230330.195247-selfsigned/key.pem'
-----

2023-03-30 20:52:47,730: DEBUG - Using configuration from /etc/yunohost/certs//maindomain.tld-history/20230330.195247-selfsigned/openssl.cnf
Check that the request matches the signature
Signature ok
Certificate Details:
        Serial Number:
            ce:21:89:ff:6a:2d:d6:5c:74:ce:08:7a:fe:ce:23:7b:78:39:c8
        Validity
            Not Before: Mar 30 19:52:47 2023 GMT
            Not After : Mar 27 19:52:47 2033 GMT
        Subject:
            commonName                = maindomain.tld
        X509v3 extensions:
            X509v3 Basic Constraints: 
                CA:FALSE
            Netscape Comment: 
                OpenSSL Generated Certificate
            X509v3 Subject Key Identifier: 
                C9:ED:A8:1C:41:EA:51:CA:2F:03:82:0F:38:F2:AA:4A:5C:71:8B:0A
            X509v3 Authority Key Identifier: 
                keyid:C4:29:9D:65:52:D7:24:0D:A6:59:25:1A:33:03:F3:0D:B8:63:27:B5

            X509v3 Key Usage: 
                Digital Signature, Non Repudiation, Key Encipherment
            X509v3 Subject Alternative Name: 
                DNS:maindomain.tld, DNS:www.maindomain.tld, DNS:ns.maindomain.tld, DNS:xmpp-upload.maindomain.tld
Certificate is to be certified until Mar 27 19:52:47 2033 GMT (3650 days)

Write out database with 1 new entries
Data Base Updated

2023-03-30 20:52:47,738: DEBUG - Enabling the certificate for domain maindomain.tld ...
2023-03-30 20:52:47,739: DEBUG - Restarting services...
2023-03-30 20:52:47,990: DEBUG - Running 'systemctl restart postfix'
2023-03-30 20:52:51,644: DEBUG - Running 'systemctl restart dovecot'
2023-03-30 20:52:53,260: DEBUG - Running 'systemctl restart metronome'
2023-03-30 20:52:53,696: DEBUG - Running 'systemctl reload nginx'
2023-03-30 20:52:53,792: SUCCESS - Self-signed certificate now installed for the domain 'maindomain.tld'
2023-03-30 20:52:53,795: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-195247-selfsigned_cert_install-maindomain.tld" style="text-decoration:underline">Install self-signed certificate on 'maindomain.tld' domain</a>'
2023-03-30 20:52:53,871: SUCCESS - Domain created
2023-03-30 20:52:53,873: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-195247-domain_add-maindomain.tld" style="text-decoration:underline">Add 'maindomain.tld' domain into system configuration</a>'
2023-03-30 20:52:54,057: DEBUG - b''
2023-03-30 20:52:54,076: DEBUG - b''
2023-03-30 20:52:54,097: DEBUG - b''
2023-03-30 20:52:54,118: DEBUG - SSOwat configuration regenerated
2023-03-30 20:52:54,119: SUCCESS - The main domain has been changed
2023-03-30 20:52:54,120: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-195253-domain_main_domain-maindomain.tld" style="text-decoration:underline">Make 'maindomain.tld' the main domain</a>'
2023-03-30 20:52:54,198: INFO - Your root password have been replaced by your admin password.
2023-03-30 20:52:54,199: SUCCESS - The administration password was changed
2023-03-30 20:52:54,934: DEBUG - Running 'systemctl reload fail2ban'
2023-03-30 20:52:55,248: SUCCESS - Firewall reloaded
2023-03-30 20:52:55,276: DEBUG - Initializing apps catalog system with YunoHost's default app list
2023-03-30 20:52:55,278: SUCCESS - App catalog system initialized!
2023-03-30 20:52:55,280: INFO - Updating application catalog...
2023-03-30 20:53:05,123: SUCCESS - The application catalog has been updated!
2023-03-30 20:53:05,132: DEBUG - Loading migration 0022_php73_to_php74_pools...
2023-03-30 20:53:05,136: DEBUG - Loading migration 0021_migrate_to_bullseye...
2023-03-30 20:53:05,138: DEBUG - Loading migration 0023_postgresql_11_to_13...
2023-03-30 20:53:05,140: DEBUG - Loading migration 0024_rebuild_python_venv...
2023-03-30 20:53:05,316: DEBUG - Running 'systemctl enable yunohost-firewall --quiet'
2023-03-30 20:53:05,748: SUCCESS - The service 'yunohost-firewall' will now be automatically started during system boots.
2023-03-30 20:53:05,923: DEBUG - Running 'systemctl start yunohost-firewall'
2023-03-30 20:53:06,955: DEBUG - Giving a lock to PID 2566 for service yunohost-firewall !
2023-03-30 20:53:12,631: SUCCESS - Service 'yunohost-firewall' started
2023-03-30 20:53:12,671: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./03-ssh" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/ssh 7>&1']'
2023-03-30 20:53:12,686: DEBUG - + set -e
2023-03-30 20:53:12,687: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:12,689: DEBUG - +++ set +o
2023-03-30 20:53:12,690: DEBUG - +++ grep xtrace
2023-03-30 20:53:12,693: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:12,693: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:12,748: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/ssh
2023-03-30 20:53:12,749: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/ssh
2023-03-30 20:53:12,749: DEBUG - + cd /usr/share/yunohost/conf/ssh
2023-03-30 20:53:12,749: DEBUG - + [[ -f /proc/net/if_inet6 ]]
2023-03-30 20:53:12,750: DEBUG - + ipv6_enabled=true
2023-03-30 20:53:12,752: DEBUG - ++ ls /etc/ssh/ssh_host_ed25519_key /etc/ssh/ssh_host_rsa_key /etc/ssh/ssh_host_ecdsa_key
2023-03-30 20:53:12,756: DEBUG - + ssh_keys='/etc/ssh/ssh_host_ecdsa_key
2023-03-30 20:53:12,756: DEBUG - /etc/ssh/ssh_host_ed25519_key
2023-03-30 20:53:12,757: DEBUG - /etc/ssh/ssh_host_rsa_key'
2023-03-30 20:53:12,757: DEBUG - ++ yunohost settings get service.ssh.allow_deprecated_dsa_hostkey
2023-03-30 20:53:13,264: DEBUG - + [[ False == \T\r\u\e ]]
2023-03-30 20:53:13,265: DEBUG - ++ yunohost settings get security.ssh.compatibility
2023-03-30 20:53:13,773: DEBUG - + export compatibility=modern
2023-03-30 20:53:13,774: DEBUG - + compatibility=modern
2023-03-30 20:53:13,774: DEBUG - ++ yunohost settings get security.ssh.port
2023-03-30 20:53:14,276: DEBUG - + export port=22
2023-03-30 20:53:14,277: DEBUG - + port=22
2023-03-30 20:53:14,278: DEBUG - ++ yunohost settings get security.ssh.password_authentication
2023-03-30 20:53:14,782: DEBUG - + export password_authentication=True
2023-03-30 20:53:14,782: DEBUG - + password_authentication=True
2023-03-30 20:53:14,783: DEBUG - + export ssh_keys
2023-03-30 20:53:14,783: DEBUG - + export ipv6_enabled
2023-03-30 20:53:14,784: DEBUG - + ynh_render_template sshd_config /var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-30 20:53:14,784: DEBUG - + local template_path=sshd_config
2023-03-30 20:53:14,785: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-30 20:53:14,785: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-30 20:53:14,786: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/ssh/etc/ssh
2023-03-30 20:53:14,789: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:14,789: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:14,790: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:15,799: DEBUG - Checking pending configuration which would have been applied for category 'ssh'...
2023-03-30 20:53:15,799: DEBUG - category ssh is not in categories.yml yet.
2023-03-30 20:53:15,800: DEBUG - updating conf hashes for 'ssh' with: {'/etc/ssh/sshd_config': 'fb8448dd6024b9e5e75653bad8953b53'}
2023-03-30 20:53:15,802: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config' to system conf '/etc/ssh/sshd_config'
2023-03-30 20:53:15,803: DEBUG - > system conf has been manually modified
2023-03-30 20:53:15,804: DEBUG - Configuration file '/etc/ssh/sshd_config' backed up to '/var/cache/yunohost/regenconf/backup/etc/ssh/sshd_config-20230330.195315'
2023-03-30 20:53:15,805: DEBUG - Configuration file '/etc/ssh/sshd_config' updated
2023-03-30 20:53:15,806: SUCCESS - Configuration updated for 'ssh'
2023-03-30 20:53:15,807: DEBUG - updating conf hashes for 'ssh' with: {'/etc/ssh/sshd_config': 'fb8448dd6024b9e5e75653bad8953b53'}
2023-03-30 20:53:15,812: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./03-ssh" post \'\' \'\' /etc/ssh/sshd_config 7>&1']'
2023-03-30 20:53:15,824: DEBUG - + set -e
2023-03-30 20:53:15,825: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:15,826: DEBUG - +++ set +o
2023-03-30 20:53:15,826: DEBUG - +++ grep xtrace
2023-03-30 20:53:15,830: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:15,830: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:15,865: DEBUG - + do_post_regen /etc/ssh/sshd_config
2023-03-30 20:53:15,866: DEBUG - + regen_conf_files=/etc/ssh/sshd_config
2023-03-30 20:53:15,866: DEBUG - + [[ -n /etc/ssh/sshd_config ]]
2023-03-30 20:53:15,867: DEBUG - + chown root:root /etc/ssh/sshd_config
2023-03-30 20:53:15,872: DEBUG - + chmod 644 /etc/ssh/sshd_config
2023-03-30 20:53:15,875: DEBUG - + systemctl restart ssh
2023-03-30 20:53:16,880: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-195312-regen_conf-ssh" style="text-decoration:underline">Regenerate system configurations 'ssh'</a>'
2023-03-30 20:53:16,964: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./01-yunohost" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/yunohost 7>&1']'
2023-03-30 20:53:16,985: DEBUG - + set -e
2023-03-30 20:53:16,988: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/yunohost
2023-03-30 20:53:16,988: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/yunohost
2023-03-30 20:53:16,989: DEBUG - + cd /usr/share/yunohost/conf/yunohost
2023-03-30 20:53:16,989: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system
2023-03-30 20:53:16,992: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/
2023-03-30 20:53:16,995: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/cron.daily/
2023-03-30 20:53:16,998: DEBUG - + cat
2023-03-30 20:53:17,000: DEBUG - + cat
2023-03-30 20:53:17,003: DEBUG - + cat
2023-03-30 20:53:17,005: DEBUG - + ls -l '/etc/yunohost/dyndns/K*.key'
2023-03-30 20:53:17,008: DEBUG - + touch /var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/yunohost-dyndns
2023-03-30 20:53:17,011: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/ntp.service.d/
2023-03-30 20:53:17,014: DEBUG - + cat
2023-03-30 20:53:17,016: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/nftables.service.d/
2023-03-30 20:53:17,019: DEBUG - + cat
2023-03-30 20:53:17,021: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/logind.conf.d/
2023-03-30 20:53:17,024: DEBUG - + cat
2023-03-30 20:53:17,027: DEBUG - + cp yunohost-api.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-api.service
2023-03-30 20:53:17,033: DEBUG - + cp yunohost-firewall.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-firewall.service
2023-03-30 20:53:17,037: DEBUG - + cp yunoprompt.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunoprompt.service
2023-03-30 20:53:17,040: DEBUG - + cp proc-hidepid.service /var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/proc-hidepid.service
2023-03-30 20:53:17,044: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/yunohost/etc/dpkg/origins/
2023-03-30 20:53:17,047: DEBUG - + cp dpkg-origins /var/cache/yunohost/regenconf/pending/yunohost/etc/dpkg/origins/yunohost
2023-03-30 20:53:18,051: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./02-ssl" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/ssl 7>&1']'
2023-03-30 20:53:18,065: DEBUG - + set -e
2023-03-30 20:53:18,066: DEBUG - + ssl_dir=/usr/share/yunohost/ssl
2023-03-30 20:53:18,067: DEBUG - + template_dir=/usr/share/yunohost/conf/ssl/
2023-03-30 20:53:18,067: DEBUG - + ynh_ca=/etc/yunohost/certs/yunohost.org/ca.pem
2023-03-30 20:53:18,067: DEBUG - + ynh_crt=/etc/yunohost/certs/yunohost.org/crt.pem
2023-03-30 20:53:18,068: DEBUG - + ynh_key=**********
2023-03-30 20:53:18,069: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/ssl
2023-03-30 20:53:18,069: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/ssl
2023-03-30 20:53:18,070: DEBUG - + install -D -m 644 /usr/share/yunohost/conf/ssl//openssl.cnf /var/cache/yunohost/regenconf/pending/ssl//usr/share/yunohost/ssl/openssl.cnf
2023-03-30 20:53:19,073: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./03-ssh" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/ssh 7>&1']'
2023-03-30 20:53:19,085: DEBUG - + set -e
2023-03-30 20:53:19,086: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:19,088: DEBUG - +++ set +o
2023-03-30 20:53:19,089: DEBUG - +++ grep xtrace
2023-03-30 20:53:19,092: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:19,093: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:19,126: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/ssh
2023-03-30 20:53:19,127: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/ssh
2023-03-30 20:53:19,128: DEBUG - + cd /usr/share/yunohost/conf/ssh
2023-03-30 20:53:19,128: DEBUG - + [[ -f /proc/net/if_inet6 ]]
2023-03-30 20:53:19,129: DEBUG - + ipv6_enabled=true
2023-03-30 20:53:19,129: DEBUG - ++ ls /etc/ssh/ssh_host_ed25519_key /etc/ssh/ssh_host_rsa_key /etc/ssh/ssh_host_ecdsa_key
2023-03-30 20:53:19,131: DEBUG - + ssh_keys='/etc/ssh/ssh_host_ecdsa_key
2023-03-30 20:53:19,132: DEBUG - /etc/ssh/ssh_host_ed25519_key
2023-03-30 20:53:19,133: DEBUG - /etc/ssh/ssh_host_rsa_key'
2023-03-30 20:53:19,133: DEBUG - ++ yunohost settings get service.ssh.allow_deprecated_dsa_hostkey
2023-03-30 20:53:19,634: DEBUG - + [[ False == \T\r\u\e ]]
2023-03-30 20:53:19,635: DEBUG - ++ yunohost settings get security.ssh.compatibility
2023-03-30 20:53:20,138: DEBUG - + export compatibility=modern
2023-03-30 20:53:20,138: DEBUG - + compatibility=modern
2023-03-30 20:53:20,139: DEBUG - ++ yunohost settings get security.ssh.port
2023-03-30 20:53:20,642: DEBUG - + export port=22
2023-03-30 20:53:20,643: DEBUG - + port=22
2023-03-30 20:53:20,643: DEBUG - ++ yunohost settings get security.ssh.password_authentication
2023-03-30 20:53:21,149: DEBUG - + export password_authentication=True
2023-03-30 20:53:21,150: DEBUG - + password_authentication=True
2023-03-30 20:53:21,150: DEBUG - + export ssh_keys
2023-03-30 20:53:21,151: DEBUG - + export ipv6_enabled
2023-03-30 20:53:21,151: DEBUG - + ynh_render_template sshd_config /var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-30 20:53:21,152: DEBUG - + local template_path=sshd_config
2023-03-30 20:53:21,152: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-30 20:53:21,153: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config
2023-03-30 20:53:21,153: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/ssh/etc/ssh
2023-03-30 20:53:21,156: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:21,157: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:21,158: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:22,165: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./06-slapd" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/slapd 7>&1']'
2023-03-30 20:53:22,196: DEBUG - + set -e
2023-03-30 20:53:22,198: DEBUG - + tmp_backup_dir_file=/root/slapd-backup-dir.txt
2023-03-30 20:53:22,198: DEBUG - + config=/usr/share/yunohost/conf/slapd/config.ldif
2023-03-30 20:53:22,199: DEBUG - + db_init=/usr/share/yunohost/conf/slapd/db_init.ldif
2023-03-30 20:53:22,200: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/slapd
2023-03-30 20:53:22,201: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/slapd
2023-03-30 20:53:22,202: DEBUG - + rm -f /root/slapd-backup-dir.txt
2023-03-30 20:53:22,205: DEBUG - ++ grep '^database' /etc/ldap/slapd.conf
2023-03-30 20:53:22,206: DEBUG - ++ awk '{print $2}'
2023-03-30 20:53:22,215: DEBUG - + curr_backend=
2023-03-30 20:53:22,216: DEBUG - + '[' -e /etc/ldap/slapd.conf ']'
2023-03-30 20:53:22,217: DEBUG - + ldap_dir=/var/cache/yunohost/regenconf/pending/slapd/etc/ldap
2023-03-30 20:53:22,218: DEBUG - + schema_dir=/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema
2023-03-30 20:53:22,219: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/slapd/etc/ldap /var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema
2023-03-30 20:53:22,221: DEBUG - + cd /usr/share/yunohost/conf/slapd
2023-03-30 20:53:22,222: DEBUG - + cp -a ldap.conf /var/cache/yunohost/regenconf/pending/slapd/etc/ldap
2023-03-30 20:53:22,231: DEBUG - + cp -a sudo.ldif mailserver.ldif permission.ldif /var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema
2023-03-30 20:53:22,239: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/slapd/etc/systemd/system/slapd.service.d/
2023-03-30 20:53:22,245: DEBUG - + cp systemd-override.conf /var/cache/yunohost/regenconf/pending/slapd/etc/systemd/system/slapd.service.d/ynh-override.conf
2023-03-30 20:53:22,254: DEBUG - + install -D -m 644 slapd.default /var/cache/yunohost/regenconf/pending/slapd/etc/default/slapd
2023-03-30 20:53:23,262: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./09-nslcd" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nslcd 7>&1']'
2023-03-30 20:53:23,293: DEBUG - + set -e
2023-03-30 20:53:23,295: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nslcd
2023-03-30 20:53:23,296: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nslcd
2023-03-30 20:53:23,297: DEBUG - + cd /usr/share/yunohost/conf/nslcd
2023-03-30 20:53:23,298: DEBUG - + install -D -m 644 nslcd.conf /var/cache/yunohost/regenconf/pending/nslcd/etc/nslcd.conf
2023-03-30 20:53:24,304: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./10-apt" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/apt 7>&1']'
2023-03-30 20:53:24,324: DEBUG - + set -e
2023-03-30 20:53:24,326: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/apt
2023-03-30 20:53:24,327: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/apt
2023-03-30 20:53:24,328: DEBUG - + mkdir --parents /var/cache/yunohost/regenconf/pending/apt/etc/apt/preferences.d
2023-03-30 20:53:24,334: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/apt/etc/apt/sources.list.d/
2023-03-30 20:53:24,340: DEBUG - ++ lsb_release --codename --short
2023-03-30 20:53:24,488: DEBUG - Package: php-common
2023-03-30 20:53:24,488: DEBUG - Pin: origin "packages.sury.org"
2023-03-30 20:53:24,488: DEBUG - Pin-Priority: 500'
2023-03-30 20:53:24,489: DEBUG - + packages_to_refuse_from_sury='php php-* openssl libssl1.1 libssl-dev'
2023-03-30 20:53:24,489: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-30 20:53:24,490: DEBUG - Package: php
2023-03-30 20:53:24,490: DEBUG - Pin: origin "packages.sury.org"
2023-03-30 20:53:24,490: DEBUG - Pin-Priority: -1'
2023-03-30 20:53:24,490: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-30 20:53:24,491: DEBUG - Package: php-*
2023-03-30 20:53:24,491: DEBUG - Pin: origin "packages.sury.org"
2023-03-30 20:53:24,491: DEBUG - Pin-Priority: -1'
2023-03-30 20:53:24,492: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-30 20:53:24,492: DEBUG - Package: openssl
2023-03-30 20:53:24,493: DEBUG - Pin: origin "packages.sury.org"
2023-03-30 20:53:24,493: DEBUG - Pin-Priority: -1'
2023-03-30 20:53:24,493: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-30 20:53:24,494: DEBUG - Package: libssl1.1
2023-03-30 20:53:24,494: DEBUG - Pin: origin "packages.sury.org"
2023-03-30 20:53:24,494: DEBUG - Pin-Priority: -1'
2023-03-30 20:53:24,494: DEBUG - + for package in $packages_to_refuse_from_sury
2023-03-30 20:53:24,495: DEBUG - Package: libssl-dev
2023-03-30 20:53:24,495: DEBUG - Pin: origin "packages.sury.org"
2023-03-30 20:53:24,495: DEBUG - Pin-Priority: -1'
2023-03-30 20:53:24,496: DEBUG - 
2023-03-30 20:53:24,496: DEBUG - # PLEASE READ THIS WARNING AND DON'\''T EDIT THIS FILE
2023-03-30 20:53:24,497: DEBUG - 
2023-03-30 20:53:24,497: DEBUG - # You are probably reading this file because you tried to install apache2 or
2023-03-30 20:53:24,497: DEBUG - # bind9. These 2 packages conflict with YunoHost.
2023-03-30 20:53:24,497: DEBUG - 
2023-03-30 20:53:24,498: DEBUG - # Installing apache2 will break nginx and break the entire YunoHost ecosystem
2023-03-30 20:53:24,498: DEBUG - # on your server, therefore don'\''t remove those lines!
2023-03-30 20:53:24,498: DEBUG - 
2023-03-30 20:53:24,499: DEBUG - # You have been warned.
2023-03-30 20:53:24,499: DEBUG - 
2023-03-30 20:53:24,499: DEBUG - Package: apache2
2023-03-30 20:53:24,499: DEBUG - Pin: release *
2023-03-30 20:53:24,500: DEBUG - Pin-Priority: -1
2023-03-30 20:53:24,500: DEBUG - 
2023-03-30 20:53:24,500: DEBUG - Package: apache2-bin
2023-03-30 20:53:24,501: DEBUG - Pin: release *
2023-03-30 20:53:24,501: DEBUG - Pin-Priority: -1
2023-03-30 20:53:24,501: DEBUG - 
2023-03-30 20:53:24,501: DEBUG - # Also bind9 will conflict with dnsmasq.
2023-03-30 20:53:24,502: DEBUG - # Same story as for apache2.
2023-03-30 20:53:24,502: DEBUG - # Don'\''t install it, don'\''t remove those lines.
2023-03-30 20:53:24,502: DEBUG - 
2023-03-30 20:53:24,502: DEBUG - Package: bind9
2023-03-30 20:53:24,503: DEBUG - Pin: release *
2023-03-30 20:53:24,503: DEBUG - Pin-Priority: -1
2023-03-30 20:53:24,503: DEBUG - '
2023-03-30 20:53:25,506: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./12-metronome" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/metronome 7>&1']'
2023-03-30 20:53:25,522: DEBUG - + set -e
2023-03-30 20:53:25,524: DEBUG - + dpkg --list
2023-03-30 20:53:25,525: DEBUG - + grep -q 'ii *metronome '
2023-03-30 20:53:25,556: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/metronome
2023-03-30 20:53:25,557: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/metronome
2023-03-30 20:53:25,557: DEBUG - + cd /usr/share/yunohost/conf/metronome
2023-03-30 20:53:25,558: DEBUG - + metronome_dir=/var/cache/yunohost/regenconf/pending/metronome/etc/metronome
2023-03-30 20:53:25,558: DEBUG - + metronome_conf_dir=/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d
2023-03-30 20:53:25,559: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d
2023-03-30 20:53:25,563: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 20:53:25,565: DEBUG - + main_domain=maindomain.tld
2023-03-30 20:53:25,566: DEBUG - + cat metronome.cfg.lua
2023-03-30 20:53:25,567: DEBUG - + sed 's/{{ main_domain }}/maindomain.tld/g'
2023-03-30 20:53:25,572: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 20:53:25,573: DEBUG - + cat domain.tpl.cfg.lua
2023-03-30 20:53:25,574: DEBUG - + sed 's/{{ domain }}/maindomain.tld/g'
2023-03-30 20:53:25,578: DEBUG - ++ ls -1 /etc/metronome/conf.d
2023-03-30 20:53:25,579: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*\.cfg\.lua$/ { print $1 }'
2023-03-30 20:53:25,584: DEBUG - + conf_files=
2023-03-30 20:53:26,598: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nginx 7>&1']'
2023-03-30 20:53:26,613: DEBUG - + set -e
2023-03-30 20:53:26,614: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:26,616: DEBUG - +++ set +o
2023-03-30 20:53:26,617: DEBUG - +++ grep xtrace
2023-03-30 20:53:26,620: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:26,621: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:26,655: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nginx
2023-03-30 20:53:26,656: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nginx
2023-03-30 20:53:26,657: DEBUG - + cd /usr/share/yunohost/conf/nginx
2023-03-30 20:53:26,657: DEBUG - + nginx_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx
2023-03-30 20:53:26,657: DEBUG - + nginx_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:26,658: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:26,662: DEBUG - + cp plain/acme-challenge.conf.inc plain/global.conf plain/ssowat.conf plain/yunohost_panel.conf.inc plain/yunohost_sso.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:26,670: DEBUG - ++ yunohost settings get ssowat.panel_overlay.enabled
2023-03-30 20:53:27,177: DEBUG - + panel_overlay=True
2023-03-30 20:53:27,178: DEBUG - + '[' True == false ']'
2023-03-30 20:53:27,178: DEBUG - + '[' True == False ']'
2023-03-30 20:53:27,179: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 20:53:27,181: DEBUG - + main_domain=maindomain.tld
2023-03-30 20:53:27,182: DEBUG - ++ yunohost settings get security.nginx.redirect_to_https
2023-03-30 20:53:27,686: DEBUG - + export redirect_to_https=True
2023-03-30 20:53:27,687: DEBUG - + redirect_to_https=True
2023-03-30 20:53:27,687: DEBUG - ++ yunohost settings get security.nginx.compatibility
2023-03-30 20:53:28,193: DEBUG - + export compatibility=intermediate
2023-03-30 20:53:28,194: DEBUG - + compatibility=intermediate
2023-03-30 20:53:28,194: DEBUG - ++ yunohost settings get security.experimental.enabled
2023-03-30 20:53:28,699: DEBUG - + export experimental=False
2023-03-30 20:53:28,700: DEBUG - + experimental=False
2023-03-30 20:53:28,700: DEBUG - + ynh_render_template security.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-30 20:53:28,701: DEBUG - + local template_path=security.conf.inc
2023-03-30 20:53:28,701: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-30 20:53:28,702: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-30 20:53:28,703: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:28,706: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:28,707: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:28,707: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:28,897: DEBUG - ++ yunohost domain cert status --json
2023-03-30 20:53:29,700: DEBUG - + cert_status='{"certificates": {"maindomain.tld": {"CA_type": "Self-signed", "validity": 3649, "summary": "WARNING"}}}'
2023-03-30 20:53:29,701: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 20:53:29,702: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-30 20:53:29,702: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-30 20:53:29,704: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-30 20:53:29,705: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-30 20:53:29,708: DEBUG - + export domain
2023-03-30 20:53:29,710: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"Self-signed",' '"validity":' 3649, '"summary":' '"WARNING"}}}'
2023-03-30 20:53:29,711: DEBUG - ++ jq '.certificates."maindomain.tld".CA_type'
2023-03-30 20:53:29,711: DEBUG - ++ tr -d '"'
2023-03-30 20:53:29,816: DEBUG - + export domain_cert_ca=Self-signed
2023-03-30 20:53:29,816: DEBUG - + domain_cert_ca=Self-signed
2023-03-30 20:53:29,817: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 20:53:29,817: DEBUG - + local template_path=server.tpl.conf
2023-03-30 20:53:29,817: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 20:53:29,818: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 20:53:29,821: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:29,824: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:29,825: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:29,825: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:30,020: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-30 20:53:30,021: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-30 20:53:30,022: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-30 20:53:30,022: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-30 20:53:30,024: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail
2023-03-30 20:53:30,027: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:30,028: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:30,028: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:30,212: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf
2023-03-30 20:53:30,215: DEBUG - ++ yunohost settings get security.webadmin.allowlist.enabled
2023-03-30 20:53:30,720: DEBUG - + export webadmin_allowlist_enabled=False
2023-03-30 20:53:30,721: DEBUG - + webadmin_allowlist_enabled=False
2023-03-30 20:53:30,721: DEBUG - + '[' False == True ']'
2023-03-30 20:53:30,722: DEBUG - + ynh_render_template yunohost_admin.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-30 20:53:30,722: DEBUG - + local template_path=yunohost_admin.conf.inc
2023-03-30 20:53:30,723: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-30 20:53:30,723: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-30 20:53:30,724: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:30,727: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:30,727: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:30,728: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:30,961: DEBUG - + ynh_render_template yunohost_api.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-30 20:53:30,962: DEBUG - + local template_path=yunohost_api.conf.inc
2023-03-30 20:53:30,962: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-30 20:53:30,963: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-30 20:53:30,964: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:30,967: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:30,968: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:30,969: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:31,154: DEBUG - + ynh_render_template yunohost_admin.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-30 20:53:31,155: DEBUG - + local template_path=yunohost_admin.conf
2023-03-30 20:53:31,155: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-30 20:53:31,156: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-30 20:53:31,157: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 20:53:31,160: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:31,161: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:31,162: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:31,343: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/
2023-03-30 20:53:31,346: DEBUG - + cp redirect_to_admin.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/
2023-03-30 20:53:31,354: DEBUG - ++ ls -1 /etc/nginx/conf.d
2023-03-30 20:53:31,355: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*\.conf$/ { print $1 }'
2023-03-30 20:53:31,360: DEBUG - + conf_files=
2023-03-30 20:53:31,364: DEBUG - ++ ls -1 '/var/www/.well-known/*/autoconfig/mail/config-v1.1.xml'
2023-03-30 20:53:31,368: DEBUG - ++ true
2023-03-30 20:53:31,368: DEBUG - + autoconfig_files=
2023-03-30 20:53:31,369: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled
2023-03-30 20:53:31,372: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled/default
2023-03-30 20:53:32,376: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./19-postfix" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/postfix 7>&1']'
2023-03-30 20:53:32,391: DEBUG - + set -e
2023-03-30 20:53:32,392: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:32,394: DEBUG - +++ set +o
2023-03-30 20:53:32,395: DEBUG - +++ grep xtrace
2023-03-30 20:53:32,398: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:32,399: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:32,432: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/postfix
2023-03-30 20:53:32,433: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/postfix
2023-03-30 20:53:32,434: DEBUG - + cd /usr/share/yunohost/conf/postfix
2023-03-30 20:53:32,434: DEBUG - + postfix_dir=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 20:53:32,435: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 20:53:32,436: DEBUG - + default_dir=/var/cache/yunohost/regenconf/pending/postfix/etc/default/
2023-03-30 20:53:32,437: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/default/
2023-03-30 20:53:32,443: DEBUG - + cp plain/header_checks plain/ldap-accounts.cf plain/ldap-aliases.cf plain/ldap-domains.cf plain/master.cf plain/sender_canonical plain/smtp_reply_filter /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 20:53:32,452: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 20:53:32,454: DEBUG - + main_domain=maindomain.tld
2023-03-30 20:53:32,455: DEBUG - ++ yunohost settings get security.postfix.compatibility
2023-03-30 20:53:32,957: DEBUG - + export compatibility=intermediate
2023-03-30 20:53:32,958: DEBUG - + compatibility=intermediate
2023-03-30 20:53:32,959: DEBUG - + export relay_port=
2023-03-30 20:53:32,959: DEBUG - + relay_port=
2023-03-30 20:53:32,960: DEBUG - + export relay_user=
2023-03-30 20:53:32,960: DEBUG - + relay_user=
2023-03-30 20:53:32,961: DEBUG - ++ yunohost settings get smtp.relay.host
2023-03-30 20:53:33,462: DEBUG - + export relay_host=
2023-03-30 20:53:33,463: DEBUG - + relay_host=
2023-03-30 20:53:33,464: DEBUG - + '[' -n '' ']'
2023-03-30 20:53:33,464: DEBUG - + export main_domain
2023-03-30 20:53:33,465: DEBUG - + export domain_list=maindomain.tld
2023-03-30 20:53:33,465: DEBUG - + domain_list=maindomain.tld
2023-03-30 20:53:33,466: DEBUG - + ynh_render_template main.cf /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-30 20:53:33,466: DEBUG - + local template_path=main.cf
2023-03-30 20:53:33,467: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-30 20:53:33,467: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-30 20:53:33,468: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 20:53:33,470: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:33,471: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:33,471: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:33,662: DEBUG - + ynh_render_template sni /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-30 20:53:33,663: DEBUG - + local template_path=sni
2023-03-30 20:53:33,664: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-30 20:53:33,664: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-30 20:53:33,666: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 20:53:33,669: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:33,670: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:33,670: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:33,854: DEBUG - + cat postsrsd
2023-03-30 20:53:33,855: DEBUG - + sed 's/{{ main_domain }}/maindomain.tld/g'
2023-03-30 20:53:33,856: DEBUG - + sed 's/{{ domain_list }}/maindomain.tld/g'
2023-03-30 20:53:33,862: DEBUG - ++ yunohost settings get smtp.allow_ipv6
2023-03-30 20:53:34,366: DEBUG - + ipv6=True
2023-03-30 20:53:34,367: DEBUG - + '[' True == False ']'
2023-03-30 20:53:34,368: DEBUG - + '[' '!' -f /proc/net/if_inet6 ']'
2023-03-30 20:53:35,371: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./25-dovecot" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/dovecot 7>&1']'
2023-03-30 20:53:35,387: DEBUG - + set -e
2023-03-30 20:53:35,388: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:35,389: DEBUG - +++ set +o
2023-03-30 20:53:35,390: DEBUG - +++ grep xtrace
2023-03-30 20:53:35,394: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:35,395: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:35,429: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/dovecot
2023-03-30 20:53:35,429: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/dovecot
2023-03-30 20:53:35,430: DEBUG - + cd /usr/share/yunohost/conf/dovecot
2023-03-30 20:53:35,430: DEBUG - + dovecot_dir=/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot
2023-03-30 20:53:35,431: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/global_script
2023-03-30 20:53:35,432: DEBUG - + cp dovecot-ldap.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot-ldap.conf
2023-03-30 20:53:35,440: DEBUG - + cp dovecot.sieve /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/global_script/dovecot.sieve
2023-03-30 20:53:35,445: DEBUG - ++ yunohost settings get pop3.enabled
2023-03-30 20:53:35,947: DEBUG - + export pop3_enabled=False
2023-03-30 20:53:35,948: DEBUG - + pop3_enabled=False
2023-03-30 20:53:35,949: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 20:53:35,951: DEBUG - + export main_domain=maindomain.tld
2023-03-30 20:53:35,952: DEBUG - + main_domain=maindomain.tld
2023-03-30 20:53:35,953: DEBUG - + export domain_list=maindomain.tld
2023-03-30 20:53:35,953: DEBUG - + domain_list=maindomain.tld
2023-03-30 20:53:35,954: DEBUG - + ynh_render_template dovecot.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf
2023-03-30 20:53:35,954: DEBUG - + local template_path=dovecot.conf
2023-03-30 20:53:35,954: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf
2023-03-30 20:53:35,955: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf
2023-03-30 20:53:35,955: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot
2023-03-30 20:53:35,959: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:35,959: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:35,960: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:36,147: DEBUG - + '[' '!' -f /proc/net/if_inet6 ']'
2023-03-30 20:53:36,147: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d
2023-03-30 20:53:36,150: DEBUG - + cp pre-ext.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d
2023-03-30 20:53:36,157: DEBUG - + cp post-ext.conf /var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d
2023-03-30 20:53:37,161: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./31-rspamd" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/rspamd 7>&1']'
2023-03-30 20:53:37,176: DEBUG - + set -e
2023-03-30 20:53:37,178: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/rspamd
2023-03-30 20:53:37,178: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/rspamd
2023-03-30 20:53:37,178: DEBUG - + cd /usr/share/yunohost/conf/rspamd
2023-03-30 20:53:37,179: DEBUG - + install -D -m 644 metrics.local.conf /var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/metrics.conf
2023-03-30 20:53:37,194: DEBUG - + install -D -m 644 dkim_signing.conf /var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/dkim_signing.conf
2023-03-30 20:53:37,202: DEBUG - + install -D -m 644 rspamd.sieve /var/cache/yunohost/regenconf/pending/rspamd/etc/dovecot/global_script/rspamd.sieve
2023-03-30 20:53:38,206: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./34-mysql" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/mysql 7>&1']'
2023-03-30 20:53:38,221: DEBUG - + set -e
2023-03-30 20:53:38,222: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:38,224: DEBUG - +++ set +o
2023-03-30 20:53:38,225: DEBUG - +++ grep xtrace
2023-03-30 20:53:38,228: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:38,229: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:38,263: DEBUG - + dpkg --list
2023-03-30 20:53:38,264: DEBUG - + grep -q 'ii *mariadb-server '
2023-03-30 20:53:38,296: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/mysql
2023-03-30 20:53:38,297: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/mysql
2023-03-30 20:53:39,300: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./35-postgresql" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/postgresql 7>&1']'
2023-03-30 20:53:39,316: DEBUG - + set -e
2023-03-30 20:53:39,317: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:39,318: DEBUG - +++ set +o
2023-03-30 20:53:39,319: DEBUG - +++ grep xtrace
2023-03-30 20:53:39,322: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:39,323: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:39,357: DEBUG - + dpkg --list
2023-03-30 20:53:39,358: DEBUG - + grep -q 'ii *postgresql-13 '
2023-03-30 20:53:39,393: DEBUG - postgresql is not installed, skipping
2023-03-30 20:53:40,401: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./36-redis" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/redis 7>&1']'
2023-03-30 20:53:40,433: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/redis
2023-03-30 20:53:40,435: DEBUG - + :
2023-03-30 20:53:41,443: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./37-mdns" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/mdns 7>&1']'
2023-03-30 20:53:41,470: DEBUG - + set -e
2023-03-30 20:53:41,473: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/mdns
2023-03-30 20:53:41,474: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/mdns
2023-03-30 20:53:41,475: DEBUG - + cd /usr/share/yunohost/conf/mdns
2023-03-30 20:53:41,476: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/mdns/etc/systemd/system/
2023-03-30 20:53:41,483: DEBUG - + cp yunomdns.service /var/cache/yunohost/regenconf/pending/mdns/etc/systemd/system/
2023-03-30 20:53:41,493: DEBUG - + getent passwd mdns
2023-03-30 20:53:41,507: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/mdns/etc/yunohost
2023-03-30 20:53:41,514: DEBUG - + _generate_config
2023-03-30 20:53:41,515: DEBUG - + echo domains:
2023-03-30 20:53:41,516: DEBUG - + echo maindomain.tld
2023-03-30 20:53:41,517: DEBUG - + tr ' ' '\n'
2023-03-30 20:53:41,518: DEBUG - + grep -q --line-regexp yunohost.local
2023-03-30 20:53:41,523: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 20:53:41,524: DEBUG - + [[ maindomain.tld =~ [^.]+\.[^.]+\.local$ ]]
2023-03-30 20:53:41,525: DEBUG - + [[ maindomain.tld =~ ^[^.]+\.local$ ]]
2023-03-30 20:53:41,525: DEBUG - + continue
2023-03-30 20:53:41,526: DEBUG - + [[ -e /etc/yunohost/mdns.aliases ]]
2023-03-30 20:53:42,544: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./43-dnsmasq" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/dnsmasq 7>&1']'
2023-03-30 20:53:42,572: DEBUG - + set -e
2023-03-30 20:53:42,574: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:42,575: DEBUG - +++ set +o
2023-03-30 20:53:42,576: DEBUG - +++ grep xtrace
2023-03-30 20:53:42,580: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:42,581: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:42,645: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/dnsmasq
2023-03-30 20:53:42,647: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/dnsmasq
2023-03-30 20:53:42,647: DEBUG - + cd /usr/share/yunohost/conf/dnsmasq
2023-03-30 20:53:42,648: DEBUG - + dnsmasq_dir=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-30 20:53:42,649: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-30 20:53:42,652: DEBUG - + etcdefault_dir=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/default
2023-03-30 20:53:42,653: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/default
2023-03-30 20:53:42,657: DEBUG - + cp plain/etcdefault /var/cache/yunohost/regenconf/pending/dnsmasq/etc/default/dnsmasq
2023-03-30 20:53:42,667: DEBUG - + cat plain/resolv.dnsmasq.conf
2023-03-30 20:53:42,667: DEBUG - + shuf
2023-03-30 20:53:42,668: DEBUG - + grep '^nameserver'
2023-03-30 20:53:42,674: DEBUG - ++ curl --max-time 10 -s -4 https://ip.yunohost.org
2023-03-30 20:53:48,811: DEBUG - + ipv4=xx.xx.xx.xx
2023-03-30 20:53:48,813: DEBUG - + ynh_validate_ip4 xx.xx.xx.xx
2023-03-30 20:53:48,864: DEBUG - + ynh_validate_ip --family=4 --ip_address=xx.xx.xx.xx
2023-03-30 20:53:48,963: DEBUG - + '[' 4 == 4 ']'
2023-03-30 20:53:48,964: DEBUG - + python3 /dev/stdin
2023-03-30 20:53:49,090: DEBUG - ++ curl --max-time 10 -s -6 https://ip6.yunohost.org
2023-03-30 20:53:49,302: DEBUG - ++ true
2023-03-30 20:53:49,303: DEBUG - + ipv6=
2023-03-30 20:53:49,303: DEBUG - + ynh_validate_ip6 ''
2023-03-30 20:53:49,323: DEBUG - + ynh_validate_ip --family=6 --ip_address=
2023-03-30 20:53:49,384: DEBUG - + '[' 6 == 4 ']'
2023-03-30 20:53:49,385: DEBUG - + '[' 6 == 6 ']'
2023-03-30 20:53:49,386: DEBUG - + python3 /dev/stdin
2023-03-30 20:53:49,471: DEBUG - + ipv6=
2023-03-30 20:53:49,473: DEBUG - ++ ip -j addr show
2023-03-30 20:53:49,474: DEBUG - ++ jq -r '[.[].ifname]|join(" ")'
2023-03-30 20:53:49,574: DEBUG - + interfaces='lo eth0 wlan0'
2023-03-30 20:53:49,575: DEBUG - + wireless_interfaces=lo
2023-03-30 20:53:49,575: DEBUG - ++ ls /sys/class/net
2023-03-30 20:53:49,579: DEBUG - + for dev in $(ls /sys/class/net)
2023-03-30 20:53:49,579: DEBUG - + '[' -d /sys/class/net/eth0/wireless ']'
2023-03-30 20:53:49,580: DEBUG - + for dev in $(ls /sys/class/net)
2023-03-30 20:53:49,580: DEBUG - + '[' -d /sys/class/net/lo/wireless ']'
2023-03-30 20:53:49,581: DEBUG - + for dev in $(ls /sys/class/net)
2023-03-30 20:53:49,581: DEBUG - + '[' -d /sys/class/net/wlan0/wireless ']'
2023-03-30 20:53:49,582: DEBUG - + grep -q up /sys/class/net/wlan0/operstate
2023-03-30 20:53:49,582: DEBUG - + export wireless_interfaces
2023-03-30 20:53:49,583: DEBUG - + ynh_render_template dnsmasq.conf.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf
2023-03-30 20:53:49,584: DEBUG - + local template_path=dnsmasq.conf.tpl
2023-03-30 20:53:49,584: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf
2023-03-30 20:53:49,585: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf
2023-03-30 20:53:49,586: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc
2023-03-30 20:53:49,590: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:49,590: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:49,591: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:49,802: DEBUG - + export interfaces
2023-03-30 20:53:49,803: DEBUG - + export ipv4
2023-03-30 20:53:49,804: DEBUG - + export ipv6
2023-03-30 20:53:49,804: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 20:53:49,805: DEBUG - + [[ ! maindomain.tld =~ \.local$ ]]
2023-03-30 20:53:49,805: DEBUG - + export domain
2023-03-30 20:53:49,805: DEBUG - + ynh_render_template domain.tpl /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld
2023-03-30 20:53:49,806: DEBUG - + local template_path=domain.tpl
2023-03-30 20:53:49,806: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld
2023-03-30 20:53:49,807: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld
2023-03-30 20:53:49,807: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d
2023-03-30 20:53:49,810: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:49,810: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:49,811: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:50,004: DEBUG - ++ ls -1 /etc/dnsmasq.d
2023-03-30 20:53:50,005: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*$/ { print $1 }'
2023-03-30 20:53:50,010: DEBUG - + conf_files=
2023-03-30 20:53:51,014: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./46-nsswitch" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nsswitch 7>&1']'
2023-03-30 20:53:51,028: DEBUG - + set -e
2023-03-30 20:53:51,029: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nsswitch
2023-03-30 20:53:51,030: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nsswitch
2023-03-30 20:53:51,031: DEBUG - + cd /usr/share/yunohost/conf/nsswitch
2023-03-30 20:53:51,031: DEBUG - + install -D -m 644 nsswitch.conf /var/cache/yunohost/regenconf/pending/nsswitch/etc/nsswitch.conf
2023-03-30 20:53:52,035: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./52-fail2ban" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/fail2ban 7>&1']'
2023-03-30 20:53:52,050: DEBUG - + set -e
2023-03-30 20:53:52,051: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:53:52,053: DEBUG - +++ set +o
2023-03-30 20:53:52,054: DEBUG - +++ grep xtrace
2023-03-30 20:53:52,057: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:53:52,058: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:53:52,091: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/fail2ban
2023-03-30 20:53:52,092: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/fail2ban
2023-03-30 20:53:52,093: DEBUG - + cd /usr/share/yunohost/conf/fail2ban
2023-03-30 20:53:52,093: DEBUG - + fail2ban_dir=/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban
2023-03-30 20:53:52,094: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d
2023-03-30 20:53:52,095: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d
2023-03-30 20:53:52,099: DEBUG - + cp yunohost.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d/yunohost.conf
2023-03-30 20:53:52,105: DEBUG - + cp jail.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.conf
2023-03-30 20:53:52,111: DEBUG - ++ yunohost settings get security.ssh.port
2023-03-30 20:53:52,616: DEBUG - + export ssh_port=22
2023-03-30 20:53:52,616: DEBUG - + ssh_port=22
2023-03-30 20:53:52,617: DEBUG - + ynh_render_template yunohost-jails.conf /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-30 20:53:52,618: DEBUG - + local template_path=yunohost-jails.conf
2023-03-30 20:53:52,618: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-30 20:53:52,618: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-30 20:53:52,619: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d
2023-03-30 20:53:52,622: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 20:53:52,623: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 20:53:52,623: DEBUG -                     ).render(os.environ));'
2023-03-30 20:53:53,639: DEBUG - Checking pending configuration which would have been applied for category 'yunohost'...
2023-03-30 20:53:53,642: DEBUG - category yunohost is not in categories.yml yet.
2023-03-30 20:53:53,642: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/yunohost-dyndns' to system conf '/etc/cron.d/yunohost-dyndns'
2023-03-30 20:53:53,643: DEBUG - > system conf is already removed
2023-03-30 20:53:53,643: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.d/yunohost-diagnosis' to system conf '/etc/cron.d/yunohost-diagnosis'
2023-03-30 20:53:53,644: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,645: DEBUG - Configuration file '/etc/cron.d/yunohost-diagnosis' updated
2023-03-30 20:53:53,645: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.daily/yunohost-fetch-apps-catalog' to system conf '/etc/cron.daily/yunohost-fetch-apps-catalog'
2023-03-30 20:53:53,649: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,649: DEBUG - Configuration file '/etc/cron.daily/yunohost-fetch-apps-catalog' updated
2023-03-30 20:53:53,650: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/cron.daily/yunohost-certificate-renew' to system conf '/etc/cron.daily/yunohost-certificate-renew'
2023-03-30 20:53:53,650: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,651: DEBUG - Configuration file '/etc/cron.daily/yunohost-certificate-renew' updated
2023-03-30 20:53:53,651: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/dpkg/origins/yunohost' to system conf '/etc/dpkg/origins/yunohost'
2023-03-30 20:53:53,653: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,653: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,654: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/logind.conf.d/ynh-override.conf' to system conf '/etc/systemd/logind.conf.d/ynh-override.conf'
2023-03-30 20:53:53,654: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,655: DEBUG - Configuration file '/etc/systemd/logind.conf.d/ynh-override.conf' updated
2023-03-30 20:53:53,656: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunoprompt.service' to system conf '/etc/systemd/system/yunoprompt.service'
2023-03-30 20:53:53,657: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,657: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,658: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-api.service' to system conf '/etc/systemd/system/yunohost-api.service'
2023-03-30 20:53:53,658: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,659: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,659: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/yunohost-firewall.service' to system conf '/etc/systemd/system/yunohost-firewall.service'
2023-03-30 20:53:53,659: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,660: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,660: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/proc-hidepid.service' to system conf '/etc/systemd/system/proc-hidepid.service'
2023-03-30 20:53:53,661: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,661: DEBUG - Configuration file '/etc/systemd/system/proc-hidepid.service' updated
2023-03-30 20:53:53,662: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/ntp.service.d/ynh-override.conf' to system conf '/etc/systemd/system/ntp.service.d/ynh-override.conf'
2023-03-30 20:53:53,662: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,663: DEBUG - Configuration file '/etc/systemd/system/ntp.service.d/ynh-override.conf' updated
2023-03-30 20:53:53,664: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/yunohost/etc/systemd/system/nftables.service.d/ynh-override.conf' to system conf '/etc/systemd/system/nftables.service.d/ynh-override.conf'
2023-03-30 20:53:53,664: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,665: DEBUG - Configuration file '/etc/systemd/system/nftables.service.d/ynh-override.conf' updated
2023-03-30 20:53:53,666: SUCCESS - Configuration updated for 'yunohost'
2023-03-30 20:53:53,667: DEBUG - updating conf hashes for 'yunohost' with: {'/etc/cron.d/yunohost-dyndns': None, '/etc/cron.d/yunohost-diagnosis': 'c86768dea989cce283f1bfce7c372ef5', '/etc/cron.daily/yunohost-fetch-apps-catalog': '5200097057aefd4e7c9c8f4f06c736ff', '/etc/cron.daily/yunohost-certificate-renew': 'ae74efd8ca119096c494e1acba683117', '/etc/dpkg/origins/yunohost': '54a72c77e761bafbc3a11b040d8ab266', '/etc/systemd/logind.conf.d/ynh-override.conf': 'fe9b22c808448846ae36b050e5ac5f83', '/etc/systemd/system/yunoprompt.service': '70e12fece55b2e8e9e95ab8903392f14', '/etc/systemd/system/yunohost-api.service': '1b33d6458bca4e280e15aa37ff52234b', '/etc/systemd/system/yunohost-firewall.service': '0dee0c5ef54e07f1592e7c1eb5185a57', '/etc/systemd/system/proc-hidepid.service': 'a3d2f1732a9eb23e7dd93bca2d7e6cec', '/etc/systemd/system/ntp.service.d/ynh-override.conf': 'a900599b3d83e37b4d3f1b616eaaa48b', '/etc/systemd/system/nftables.service.d/ynh-override.conf': 'ceb28ead4c7638d8e6821e9b7a6d349d'}
2023-03-30 20:53:53,674: DEBUG - Checking pending configuration which would have been applied for category 'ssl'...
2023-03-30 20:53:53,681: DEBUG - category ssl is not in categories.yml yet.
2023-03-30 20:53:53,681: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/ssl/usr/share/yunohost/ssl/openssl.cnf' to system conf '/usr/share/yunohost/ssl/openssl.cnf'
2023-03-30 20:53:53,682: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,682: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,683: SUCCESS - Configuration updated for 'ssl'
2023-03-30 20:53:53,683: DEBUG - updating conf hashes for 'ssl' with: {'/usr/share/yunohost/ssl/openssl.cnf': '2bb7d01b193040934af8ef8043b22bd7'}
2023-03-30 20:53:53,696: DEBUG - Checking pending configuration which would have been applied for category 'ssh'...
2023-03-30 20:53:53,703: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/ssh/etc/ssh/sshd_config' to system conf '/etc/ssh/sshd_config'
2023-03-30 20:53:53,704: DEBUG - > system conf is already up-to-date
2023-03-30 20:53:53,705: DEBUG - The configuration is already up-to-date for category 'ssh'
2023-03-30 20:53:53,705: DEBUG - Checking pending configuration which would have been applied for category 'slapd'...
2023-03-30 20:53:53,712: DEBUG - category slapd is not in categories.yml yet.
2023-03-30 20:53:53,713: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/ldap.conf' to system conf '/etc/ldap/ldap.conf'
2023-03-30 20:53:53,713: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,714: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,714: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema/mailserver.ldif' to system conf '/etc/ldap/schema/mailserver.ldif'
2023-03-30 20:53:53,718: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,718: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,719: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema/sudo.ldif' to system conf '/etc/ldap/schema/sudo.ldif'
2023-03-30 20:53:53,720: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,720: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,721: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/ldap/schema/permission.ldif' to system conf '/etc/ldap/schema/permission.ldif'
2023-03-30 20:53:53,722: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,722: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,723: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/default/slapd' to system conf '/etc/default/slapd'
2023-03-30 20:53:53,723: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,724: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,724: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/slapd/etc/systemd/system/slapd.service.d/ynh-override.conf' to system conf '/etc/systemd/system/slapd.service.d/ynh-override.conf'
2023-03-30 20:53:53,725: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,725: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,725: SUCCESS - Configuration updated for 'slapd'
2023-03-30 20:53:53,726: DEBUG - updating conf hashes for 'slapd' with: {'/etc/ldap/ldap.conf': '8e8b048fb294294cee014cb6738b2a08', '/etc/ldap/schema/mailserver.ldif': '731ce8a4a50623fc3a3940e4b77b3512', '/etc/ldap/schema/sudo.ldif': '4d02ae0c33cdf847b84c0a1d505ddd73', '/etc/ldap/schema/permission.ldif': '5aad096e8fe30bc9d49a9d1b6c20de9f', '/etc/default/slapd': 'a20f421f8bbc95078384ceb54d2e68a8', '/etc/systemd/system/slapd.service.d/ynh-override.conf': 'c2441b545c3d43c735f631250fb38305'}
2023-03-30 20:53:53,741: DEBUG - Checking pending configuration which would have been applied for category 'nslcd'...
2023-03-30 20:53:53,751: DEBUG - category nslcd is not in categories.yml yet.
2023-03-30 20:53:53,752: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nslcd/etc/nslcd.conf' to system conf '/etc/nslcd.conf'
2023-03-30 20:53:53,753: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,753: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,753: SUCCESS - Configuration updated for 'nslcd'
2023-03-30 20:53:53,754: DEBUG - updating conf hashes for 'nslcd' with: {'/etc/nslcd.conf': 'e8bd1e22e7b91e60ebe5b1701e159437'}
2023-03-30 20:53:53,772: DEBUG - Checking pending configuration which would have been applied for category 'apt'...
2023-03-30 20:53:53,783: DEBUG - category apt is not in categories.yml yet.
2023-03-30 20:53:53,783: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/apt/etc/apt/sources.list.d/extra_php_version.list' to system conf '/etc/apt/sources.list.d/extra_php_version.list'
2023-03-30 20:53:53,820: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,821: DEBUG - Configuration file '/etc/apt/sources.list.d/extra_php_version.list' updated
2023-03-30 20:53:53,822: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/apt/etc/apt/preferences.d/extra_php_version' to system conf '/etc/apt/preferences.d/extra_php_version'
2023-03-30 20:53:53,823: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,824: DEBUG - Configuration file '/etc/apt/preferences.d/extra_php_version' updated
2023-03-30 20:53:53,825: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/apt/etc/apt/preferences.d/ban_packages' to system conf '/etc/apt/preferences.d/ban_packages'
2023-03-30 20:53:53,825: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,826: DEBUG - Configuration file '/etc/apt/preferences.d/ban_packages' updated
2023-03-30 20:53:53,826: SUCCESS - Configuration updated for 'apt'
2023-03-30 20:53:53,827: DEBUG - updating conf hashes for 'apt' with: {'/etc/apt/sources.list.d/extra_php_version.list': 'af92c221aec2c563082b5bc15b85b3c9', '/etc/apt/preferences.d/extra_php_version': '41ab3a1639c937dc117fafe75e48086b', '/etc/apt/preferences.d/ban_packages': '10b3a80bb3cfa34027ca1f4d5fab1f00'}
2023-03-30 20:53:53,847: DEBUG - Checking pending configuration which would have been applied for category 'metronome'...
2023-03-30 20:53:53,859: DEBUG - category metronome is not in categories.yml yet.
2023-03-30 20:53:53,860: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/metronome.cfg.lua' to system conf '/etc/metronome/metronome.cfg.lua'
2023-03-30 20:53:53,861: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,861: INFO - The configuration file '/etc/metronome/metronome.cfg.lua' is now managed by YunoHost (category metronome).
2023-03-30 20:53:53,862: DEBUG - Configuration file '/etc/metronome/metronome.cfg.lua' backed up to '/var/cache/yunohost/regenconf/backup/etc/metronome/metronome.cfg.lua-20230330.195353'
2023-03-30 20:53:53,864: DEBUG - Configuration file '/etc/metronome/metronome.cfg.lua' updated
2023-03-30 20:53:53,864: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/metronome/etc/metronome/conf.d/maindomain.tld.cfg.lua' to system conf '/etc/metronome/conf.d/maindomain.tld.cfg.lua'
2023-03-30 20:53:53,865: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,865: DEBUG - Configuration file '/etc/metronome/conf.d/maindomain.tld.cfg.lua' updated
2023-03-30 20:53:53,866: SUCCESS - Configuration updated for 'metronome'
2023-03-30 20:53:53,867: DEBUG - updating conf hashes for 'metronome' with: {'/etc/metronome/metronome.cfg.lua': '16a63aa3b50bce30d38bfad112879d00', '/etc/metronome/conf.d/maindomain.tld.cfg.lua': '61722bffddc1fa96e3c1fa5c92d288a6'}
2023-03-30 20:53:53,889: DEBUG - Checking pending configuration which would have been applied for category 'nginx'...
2023-03-30 20:53:53,903: DEBUG - category nginx is not in categories.yml yet.
2023-03-30 20:53:53,903: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled/default' to system conf '/etc/nginx/sites-enabled/default'
2023-03-30 20:53:53,904: DEBUG - > system conf is already removed
2023-03-30 20:53:53,904: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc' to system conf '/etc/nginx/conf.d/security.conf.inc'
2023-03-30 20:53:53,905: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,905: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,906: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_admin.conf.inc'
2023-03-30 20:53:53,906: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,906: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,907: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_api.conf.inc'
2023-03-30 20:53:53,907: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,908: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,908: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf' to system conf '/etc/nginx/conf.d/yunohost_admin.conf'
2023-03-30 20:53:53,909: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,909: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,909: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_panel.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_panel.conf.inc'
2023-03-30 20:53:53,913: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,913: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,914: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf' to system conf '/etc/nginx/conf.d/maindomain.tld.conf'
2023-03-30 20:53:53,914: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,915: DEBUG - Configuration file '/etc/nginx/conf.d/maindomain.tld.conf' updated
2023-03-30 20:53:53,915: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/ssowat.conf' to system conf '/etc/nginx/conf.d/ssowat.conf'
2023-03-30 20:53:53,916: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,916: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,917: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/acme-challenge.conf.inc' to system conf '/etc/nginx/conf.d/acme-challenge.conf.inc'
2023-03-30 20:53:53,918: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,918: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,918: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/global.conf' to system conf '/etc/nginx/conf.d/global.conf'
2023-03-30 20:53:53,919: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,919: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,920: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_sso.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_sso.conf.inc'
2023-03-30 20:53:53,921: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,921: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,922: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/redirect_to_admin.conf' to system conf '/etc/nginx/conf.d/default.d/redirect_to_admin.conf'
2023-03-30 20:53:53,922: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,922: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:53,923: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf'
2023-03-30 20:53:53,923: DEBUG - > system conf is already removed
2023-03-30 20:53:53,924: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-30 20:53:53,924: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,925: DEBUG - Configuration file '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml' updated
2023-03-30 20:53:53,926: SUCCESS - Configuration updated for 'nginx'
2023-03-30 20:53:53,927: DEBUG - updating conf hashes for 'nginx' with: {'/etc/nginx/sites-enabled/default': None, '/etc/nginx/conf.d/security.conf.inc': '2ceb56ca697e974c9021a47b7c415eb7', '/etc/nginx/conf.d/yunohost_admin.conf.inc': '1903e867bcfa00af27e0e51dfa37c8ed', '/etc/nginx/conf.d/yunohost_api.conf.inc': '71e89f68f5af5d83d161c54ade8d192f', '/etc/nginx/conf.d/yunohost_admin.conf': '4f23bfc63fa5614e5b6997efcd83706c', '/etc/nginx/conf.d/yunohost_panel.conf.inc': '3de64e15d9874e6e17ab29cb6e48f188', '/etc/nginx/conf.d/maindomain.tld.conf': '5a7cf948412f7df7e7e751e4d529c419', '/etc/nginx/conf.d/ssowat.conf': '88f0941db4a897c214f34a0661db890d', '/etc/nginx/conf.d/acme-challenge.conf.inc': '6e532401262f7daf627c6482d6367f5d', '/etc/nginx/conf.d/global.conf': 'f8c8721f10d718546b2735080770d307', '/etc/nginx/conf.d/yunohost_sso.conf.inc': '2230d8402c1167bea5db3f06f327e8fa', '/etc/nginx/conf.d/default.d/redirect_to_admin.conf': '69b9d60d4f87f404e4d376458d9de4e1', '/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf': None, '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml': '5a6ed21fd8a9edbfb216ad9a00593dec'}
2023-03-30 20:53:53,955: DEBUG - Checking pending configuration which would have been applied for category 'postfix'...
2023-03-30 20:53:53,974: DEBUG - category postfix is not in categories.yml yet.
2023-03-30 20:53:53,974: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-domains.cf' to system conf '/etc/postfix/ldap-domains.cf'
2023-03-30 20:53:53,975: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,975: DEBUG - Configuration file '/etc/postfix/ldap-domains.cf' updated
2023-03-30 20:53:53,976: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/header_checks' to system conf '/etc/postfix/header_checks'
2023-03-30 20:53:53,977: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,977: DEBUG - Configuration file '/etc/postfix/header_checks' updated
2023-03-30 20:53:53,978: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sender_canonical' to system conf '/etc/postfix/sender_canonical'
2023-03-30 20:53:53,978: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,979: DEBUG - Configuration file '/etc/postfix/sender_canonical' updated
2023-03-30 20:53:53,979: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-aliases.cf' to system conf '/etc/postfix/ldap-aliases.cf'
2023-03-30 20:53:53,980: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,981: DEBUG - Configuration file '/etc/postfix/ldap-aliases.cf' updated
2023-03-30 20:53:53,981: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/master.cf' to system conf '/etc/postfix/master.cf'
2023-03-30 20:53:53,982: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,982: INFO - The configuration file '/etc/postfix/master.cf' is now managed by YunoHost (category postfix).
2023-03-30 20:53:53,983: DEBUG - Configuration file '/etc/postfix/master.cf' backed up to '/var/cache/yunohost/regenconf/backup/etc/postfix/master.cf-20230330.195353'
2023-03-30 20:53:53,984: DEBUG - Configuration file '/etc/postfix/master.cf' updated
2023-03-30 20:53:53,985: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf' to system conf '/etc/postfix/main.cf'
2023-03-30 20:53:53,985: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,986: INFO - The configuration file '/etc/postfix/main.cf' is now managed by YunoHost (category postfix).
2023-03-30 20:53:53,987: DEBUG - Configuration file '/etc/postfix/main.cf' backed up to '/var/cache/yunohost/regenconf/backup/etc/postfix/main.cf-20230330.195353'
2023-03-30 20:53:53,988: DEBUG - Configuration file '/etc/postfix/main.cf' updated
2023-03-30 20:53:53,988: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-accounts.cf' to system conf '/etc/postfix/ldap-accounts.cf'
2023-03-30 20:53:53,989: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,990: DEBUG - Configuration file '/etc/postfix/ldap-accounts.cf' updated
2023-03-30 20:53:53,990: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni' to system conf '/etc/postfix/sni'
2023-03-30 20:53:53,991: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,992: DEBUG - Configuration file '/etc/postfix/sni' updated
2023-03-30 20:53:53,992: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/smtp_reply_filter' to system conf '/etc/postfix/smtp_reply_filter'
2023-03-30 20:53:53,993: DEBUG - > system conf has been manually removed
2023-03-30 20:53:53,993: DEBUG - Configuration file '/etc/postfix/smtp_reply_filter' updated
2023-03-30 20:53:53,994: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/default/postsrsd' to system conf '/etc/default/postsrsd'
2023-03-30 20:53:53,994: DEBUG - > system conf is not managed yet
2023-03-30 20:53:53,995: INFO - The configuration file '/etc/default/postsrsd' is now managed by YunoHost (category postfix).
2023-03-30 20:53:53,996: DEBUG - Configuration file '/etc/default/postsrsd' backed up to '/var/cache/yunohost/regenconf/backup/etc/default/postsrsd-20230330.195353'
2023-03-30 20:53:53,997: DEBUG - Configuration file '/etc/default/postsrsd' updated
2023-03-30 20:53:53,998: SUCCESS - Configuration updated for 'postfix'
2023-03-30 20:53:53,998: DEBUG - updating conf hashes for 'postfix' with: {'/etc/postfix/ldap-domains.cf': '082d1b0953e8021982c5cffd3d7f10a9', '/etc/postfix/header_checks': '80a29f033d979766873a0bd90f5a6542', '/etc/postfix/sender_canonical': '6af7cba824e4a563ec6d7d786f891e2f', '/etc/postfix/ldap-aliases.cf': '8712ccd28e11fda276abd34e8ce85b5a', '/etc/postfix/master.cf': 'c32bf9a7d37a33b45a93d08e5fdbe1e2', '/etc/postfix/main.cf': '8308082d24260099927be1f237e87cea', '/etc/postfix/ldap-accounts.cf': '301af4a3fa12e43fffa4216ffda0f2b2', '/etc/postfix/sni': '43523cecd234392fa41d6d5c36c74735', '/etc/postfix/smtp_reply_filter': 'ff0bbf5d75d5e4096733c51d7745d924', '/etc/default/postsrsd': '33b64b225d18a7faa161eb35dac1ee9c'}
2023-03-30 20:53:54,034: DEBUG - Checking pending configuration which would have been applied for category 'dovecot'...
2023-03-30 20:53:54,057: DEBUG - category dovecot is not in categories.yml yet.
2023-03-30 20:53:54,057: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot-ldap.conf' to system conf '/etc/dovecot/dovecot-ldap.conf'
2023-03-30 20:53:54,058: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,059: DEBUG - Configuration file '/etc/dovecot/dovecot-ldap.conf' updated
2023-03-30 20:53:54,059: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/dovecot.conf' to system conf '/etc/dovecot/dovecot.conf'
2023-03-30 20:53:54,060: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,060: INFO - The configuration file '/etc/dovecot/dovecot.conf' is now managed by YunoHost (category dovecot).
2023-03-30 20:53:54,062: DEBUG - Configuration file '/etc/dovecot/dovecot.conf' backed up to '/var/cache/yunohost/regenconf/backup/etc/dovecot/dovecot.conf-20230330.195354'
2023-03-30 20:53:54,063: DEBUG - Configuration file '/etc/dovecot/dovecot.conf' updated
2023-03-30 20:53:54,063: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d/pre-ext.conf' to system conf '/etc/dovecot/yunohost.d/pre-ext.conf'
2023-03-30 20:53:54,064: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,065: DEBUG - Configuration file '/etc/dovecot/yunohost.d/pre-ext.conf' updated
2023-03-30 20:53:54,065: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/yunohost.d/post-ext.conf' to system conf '/etc/dovecot/yunohost.d/post-ext.conf'
2023-03-30 20:53:54,066: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,066: DEBUG - Configuration file '/etc/dovecot/yunohost.d/post-ext.conf' updated
2023-03-30 20:53:54,067: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dovecot/etc/dovecot/global_script/dovecot.sieve' to system conf '/etc/dovecot/global_script/dovecot.sieve'
2023-03-30 20:53:54,067: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,068: DEBUG - Configuration file '/etc/dovecot/global_script/dovecot.sieve' updated
2023-03-30 20:53:54,069: SUCCESS - Configuration updated for 'dovecot'
2023-03-30 20:53:54,069: DEBUG - updating conf hashes for 'dovecot' with: {'/etc/dovecot/dovecot-ldap.conf': 'f3fec990f5deb2121d0420fbfb4f4101', '/etc/dovecot/dovecot.conf': 'eb46689633c15e30e47c203f11fdf844', '/etc/dovecot/yunohost.d/pre-ext.conf': '0f6216e006ef1be6ca7d7fc23ca91992', '/etc/dovecot/yunohost.d/post-ext.conf': '714bdbe482b6130f817db02bb96f3770', '/etc/dovecot/global_script/dovecot.sieve': '726652e0d927a6ac79193175f73027f4'}
2023-03-30 20:53:54,139: DEBUG - Checking pending configuration which would have been applied for category 'rspamd'...
2023-03-30 20:53:54,193: DEBUG - category rspamd is not in categories.yml yet.
2023-03-30 20:53:54,194: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/dkim_signing.conf' to system conf '/etc/rspamd/local.d/dkim_signing.conf'
2023-03-30 20:53:54,194: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,195: DEBUG - Configuration file '/etc/rspamd/local.d/dkim_signing.conf' updated
2023-03-30 20:53:54,196: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/rspamd/etc/rspamd/local.d/metrics.conf' to system conf '/etc/rspamd/local.d/metrics.conf'
2023-03-30 20:53:54,196: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,197: DEBUG - Configuration file '/etc/rspamd/local.d/metrics.conf' updated
2023-03-30 20:53:54,198: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/rspamd/etc/dovecot/global_script/rspamd.sieve' to system conf '/etc/dovecot/global_script/rspamd.sieve'
2023-03-30 20:53:54,198: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,199: DEBUG - Configuration file '/etc/dovecot/global_script/rspamd.sieve' updated
2023-03-30 20:53:54,199: SUCCESS - Configuration updated for 'rspamd'
2023-03-30 20:53:54,200: DEBUG - updating conf hashes for 'rspamd' with: {'/etc/rspamd/local.d/dkim_signing.conf': '50c04522653dd3e852202aeea1a18c14', '/etc/rspamd/local.d/metrics.conf': '63a4770fdc452038681f903d3b9ca8d5', '/etc/dovecot/global_script/rspamd.sieve': '48eee4f4b94c66a1105142e27cad0548'}
2023-03-30 20:53:54,244: DEBUG - Checking pending configuration which would have been applied for category 'mdns'...
2023-03-30 20:53:54,272: DEBUG - category mdns is not in categories.yml yet.
2023-03-30 20:53:54,273: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/mdns/etc/yunohost/mdns.yml' to system conf '/etc/yunohost/mdns.yml'
2023-03-30 20:53:54,273: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,273: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:54,274: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/mdns/etc/systemd/system/yunomdns.service' to system conf '/etc/systemd/system/yunomdns.service'
2023-03-30 20:53:54,274: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,275: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:54,275: SUCCESS - Configuration updated for 'mdns'
2023-03-30 20:53:54,276: DEBUG - updating conf hashes for 'mdns' with: {'/etc/yunohost/mdns.yml': 'bb685d81b53973f9783c16b784252fee', '/etc/systemd/system/yunomdns.service': '0c08ef242c09941d39ff453aa613073d'}
2023-03-30 20:53:54,322: DEBUG - Checking pending configuration which would have been applied for category 'dnsmasq'...
2023-03-30 20:53:54,350: DEBUG - category dnsmasq is not in categories.yml yet.
2023-03-30 20:53:54,351: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/resolv.dnsmasq.conf' to system conf '/etc/resolv.dnsmasq.conf'
2023-03-30 20:53:54,352: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,352: DEBUG - Configuration file '/etc/resolv.dnsmasq.conf' updated
2023-03-30 20:53:54,353: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.conf' to system conf '/etc/dnsmasq.conf'
2023-03-30 20:53:54,354: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,354: INFO - The configuration file '/etc/dnsmasq.conf' is now managed by YunoHost (category dnsmasq).
2023-03-30 20:53:54,355: DEBUG - Configuration file '/etc/dnsmasq.conf' backed up to '/var/cache/yunohost/regenconf/backup/etc/dnsmasq.conf-20230330.195354'
2023-03-30 20:53:54,356: DEBUG - Configuration file '/etc/dnsmasq.conf' updated
2023-03-30 20:53:54,357: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/dnsmasq.d/maindomain.tld' to system conf '/etc/dnsmasq.d/maindomain.tld'
2023-03-30 20:53:54,357: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,358: DEBUG - Configuration file '/etc/dnsmasq.d/maindomain.tld' updated
2023-03-30 20:53:54,359: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/dnsmasq/etc/default/dnsmasq' to system conf '/etc/default/dnsmasq'
2023-03-30 20:53:54,359: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,359: INFO - The configuration file '/etc/default/dnsmasq' is now managed by YunoHost (category dnsmasq).
2023-03-30 20:53:54,361: DEBUG - Configuration file '/etc/default/dnsmasq' backed up to '/var/cache/yunohost/regenconf/backup/etc/default/dnsmasq-20230330.195354'
2023-03-30 20:53:54,362: DEBUG - Configuration file '/etc/default/dnsmasq' updated
2023-03-30 20:53:54,362: SUCCESS - Configuration updated for 'dnsmasq'
2023-03-30 20:53:54,363: DEBUG - updating conf hashes for 'dnsmasq' with: {'/etc/resolv.dnsmasq.conf': '4711805d9a4e13ea05f499b416f31a81', '/etc/dnsmasq.conf': 'eb5a7091f047b94f656ea5a2e4bfbaa0', '/etc/dnsmasq.d/maindomain.tld': '5309d182c2daeb3c84a6a64f2d84aed0', '/etc/default/dnsmasq': 'ff5c2923b4d5e1e51ffd8d226c26fe2b'}
2023-03-30 20:53:54,412: DEBUG - Checking pending configuration which would have been applied for category 'nsswitch'...
2023-03-30 20:53:54,442: DEBUG - category nsswitch is not in categories.yml yet.
2023-03-30 20:53:54,442: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nsswitch/etc/nsswitch.conf' to system conf '/etc/nsswitch.conf'
2023-03-30 20:53:54,443: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,443: DEBUG - > no changes to system conf has been made
2023-03-30 20:53:54,444: SUCCESS - Configuration updated for 'nsswitch'
2023-03-30 20:53:54,444: DEBUG - updating conf hashes for 'nsswitch' with: {'/etc/nsswitch.conf': '4e541356b947dd940aa7548c77bfe415'}
2023-03-30 20:53:54,496: DEBUG - Checking pending configuration which would have been applied for category 'fail2ban'...
2023-03-30 20:53:54,527: DEBUG - category fail2ban is not in categories.yml yet.
2023-03-30 20:53:54,527: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.conf' to system conf '/etc/fail2ban/jail.conf'
2023-03-30 20:53:54,528: DEBUG - > system conf is not managed yet
2023-03-30 20:53:54,528: INFO - The configuration file '/etc/fail2ban/jail.conf' is now managed by YunoHost (category fail2ban).
2023-03-30 20:53:54,530: DEBUG - Configuration file '/etc/fail2ban/jail.conf' backed up to '/var/cache/yunohost/regenconf/backup/etc/fail2ban/jail.conf-20230330.195354'
2023-03-30 20:53:54,531: DEBUG - Configuration file '/etc/fail2ban/jail.conf' updated
2023-03-30 20:53:54,531: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/filter.d/yunohost.conf' to system conf '/etc/fail2ban/filter.d/yunohost.conf'
2023-03-30 20:53:54,532: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,533: DEBUG - Configuration file '/etc/fail2ban/filter.d/yunohost.conf' updated
2023-03-30 20:53:54,533: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/fail2ban/etc/fail2ban/jail.d/yunohost-jails.conf' to system conf '/etc/fail2ban/jail.d/yunohost-jails.conf'
2023-03-30 20:53:54,534: DEBUG - > system conf has been manually removed
2023-03-30 20:53:54,534: DEBUG - Configuration file '/etc/fail2ban/jail.d/yunohost-jails.conf' updated
2023-03-30 20:53:54,535: SUCCESS - Configuration updated for 'fail2ban'
2023-03-30 20:53:54,535: DEBUG - updating conf hashes for 'fail2ban' with: {'/etc/fail2ban/jail.conf': 'd7996651d349f5a6a21a76a192c3bf3f', '/etc/fail2ban/filter.d/yunohost.conf': '5b475a44e9e19fbd8c88066b9e1ae9ff', '/etc/fail2ban/jail.d/yunohost-jails.conf': '78987acc0395f8b334b23b42e2728441'}
2023-03-30 20:53:54,590: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./01-yunohost" post \'\' \'\' /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf 7>&1']'
2023-03-30 20:53:54,603: DEBUG - + set -e
2023-03-30 20:53:54,604: DEBUG - + do_post_regen /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf
2023-03-30 20:53:54,605: DEBUG - + regen_conf_files=/etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf
2023-03-30 20:53:54,606: DEBUG - + chmod 750 /home/admin
2023-03-30 20:53:54,607: DEBUG - + chmod 750 /home/yunohost.backup
2023-03-30 20:53:54,609: DEBUG - + chmod 750 /home/yunohost.backup/archives
2023-03-30 20:53:54,614: DEBUG - + chmod 700 /var/cache/yunohost
2023-03-30 20:53:54,616: DEBUG - + chown admin:root /home/yunohost.backup
2023-03-30 20:53:54,629: DEBUG - + chown admin:root /home/yunohost.backup/archives
2023-03-30 20:53:54,631: DEBUG - + chown root:root /var/cache/yunohost
2023-03-30 20:53:54,634: DEBUG - + chmod 755 /etc/yunohost
2023-03-30 20:53:54,636: DEBUG - + chown -R root:ssl-cert /etc/yunohost/certs
2023-03-30 20:53:54,643: DEBUG - + chmod 750 /etc/yunohost/certs
2023-03-30 20:53:54,645: DEBUG - + find /etc/yunohost/certs/ -type f -exec chmod 640 '{}' ';'
2023-03-30 20:53:54,659: DEBUG - + find /etc/yunohost/certs/ -type d -exec chmod 750 '{}' ';'
2023-03-30 20:53:54,674: DEBUG - + find /etc/cron.daily/yunohost-certificate-renew /etc/cron.daily/yunohost-fetch-apps-catalog /etc/cron.d/yunohost-diagnosis -type f -exec chmod 755 '{}' ';'
2023-03-30 20:53:54,682: DEBUG - + find /etc/cron.d/yunohost-diagnosis -type f -exec chmod 644 '{}' ';'
2023-03-30 20:53:54,688: DEBUG - + find /etc/cron.daily/yunohost-certificate-renew /etc/cron.daily/yunohost-fetch-apps-catalog /etc/cron.d/yunohost-diagnosis -type f -exec chown root:root '{}' ';'
2023-03-30 20:53:54,698: DEBUG - + setfacl -m g:all_users:--- /var/www
2023-03-30 20:53:54,710: DEBUG - + setfacl -m g:all_users:--- /var/log/nginx
2023-03-30 20:53:54,712: DEBUG - + setfacl -m g:all_users:--- /etc/yunohost
2023-03-30 20:53:54,715: DEBUG - + setfacl -m g:all_users:--- /etc/ssowat
2023-03-30 20:53:54,718: DEBUG - ++ yunohost user list --quiet --output-as json
2023-03-30 20:53:54,719: DEBUG - ++ jq -r '.users | .[] | .username'
2023-03-30 20:53:55,424: DEBUG - + mkdir -p /etc/yunohost/domains
2023-03-30 20:53:55,428: DEBUG - ++ ls /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/regenconf.yml /etc/yunohost/services.yml /etc/yunohost/migrations.yaml '/etc/yunohost/*.json' /etc/yunohost/mysql /etc/yunohost/psql
2023-03-30 20:53:55,432: DEBUG - + chown root:root /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/migrations.yaml /etc/yunohost/regenconf.yml /etc/yunohost/services.yml
2023-03-30 20:53:55,436: DEBUG - ++ ls /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/regenconf.yml /etc/yunohost/services.yml /etc/yunohost/migrations.yaml '/etc/yunohost/*.json' /etc/yunohost/mysql /etc/yunohost/psql
2023-03-30 20:53:55,440: DEBUG - + chmod 600 /etc/yunohost/apps_catalog.yml /etc/yunohost/firewall.yml /etc/yunohost/mdns.yml /etc/yunohost/migrations.yaml /etc/yunohost/regenconf.yml /etc/yunohost/services.yml
2023-03-30 20:53:55,442: DEBUG - + [[ ! -e /etc/yunohost/hooks.d ]]
2023-03-30 20:53:55,443: DEBUG - + [[ ! -e /etc/yunohost/apps ]]
2023-03-30 20:53:55,443: DEBUG - + chown root /etc/yunohost/apps
2023-03-30 20:53:55,445: DEBUG - + chmod 700 /etc/yunohost/apps
2023-03-30 20:53:55,447: DEBUG - + [[ ! -e /etc/yunohost/domains ]]
2023-03-30 20:53:55,448: DEBUG - + chown root /etc/yunohost/domains
2023-03-30 20:53:55,450: DEBUG - + chmod 700 /etc/yunohost/domains
2023-03-30 20:53:55,453: DEBUG - + grep -q '^ssh.app:' /etc/group
2023-03-30 20:53:55,456: DEBUG - + groupadd ssh.app
2023-03-30 20:53:55,555: DEBUG - + grep -q '^sftp.app:' /etc/group
2023-03-30 20:53:55,557: DEBUG - + groupadd sftp.app
2023-03-30 20:53:55,636: DEBUG - + [[ ! /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ ntp\.service\.d/ynh-override\.conf ]]
2023-03-30 20:53:55,637: DEBUG - + systemctl daemon-reload
2023-03-30 20:53:56,050: DEBUG - + systemctl restart ntp
2023-03-30 20:53:56,109: DEBUG - + [[ ! /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ nftables\.service\.d/ynh-override\.conf ]]
2023-03-30 20:53:56,110: DEBUG - + systemctl daemon-reload
2023-03-30 20:53:56,534: DEBUG - + [[ ! /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ login\.conf\.d/ynh-override\.conf ]]
2023-03-30 20:53:56,535: DEBUG - + [[ ! /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ yunohost-firewall\.service ]]
2023-03-30 20:53:56,536: DEBUG - + systemctl daemon-reload
2023-03-30 20:53:56,961: DEBUG - + [[ ! /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ yunohost-api\.service ]]
2023-03-30 20:53:56,962: DEBUG - + systemctl daemon-reload
2023-03-30 20:53:57,364: DEBUG - + [[ /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ yunoprompt\.service ]]
2023-03-30 20:53:57,367: DEBUG - + systemctl daemon-reload
2023-03-30 20:53:57,773: DEBUG - ++ [[ -e /etc/systemd/system/yunoprompt.service ]]
2023-03-30 20:53:57,774: DEBUG - ++ echo enable
2023-03-30 20:53:57,776: DEBUG - + action=enable
2023-03-30 20:53:57,777: DEBUG - + systemctl enable yunoprompt --quiet --now
2023-03-30 20:53:58,205: DEBUG - + [[ /etc/cron.d/yunohost-diagnosis,/etc/cron.daily/yunohost-fetch-apps-catalog,/etc/cron.daily/yunohost-certificate-renew,/etc/dpkg/origins/yunohost,/etc/systemd/logind.conf.d/ynh-override.conf,/etc/systemd/system/yunoprompt.service,/etc/systemd/system/yunohost-api.service,/etc/systemd/system/yunohost-firewall.service,/etc/systemd/system/proc-hidepid.service,/etc/systemd/system/ntp.service.d/ynh-override.conf,/etc/systemd/system/nftables.service.d/ynh-override.conf =~ proc-hidepid\.service ]]
2023-03-30 20:53:58,206: DEBUG - + systemctl daemon-reload
2023-03-30 20:53:58,648: DEBUG - ++ [[ -e /etc/systemd/system/proc-hidepid.service ]]
2023-03-30 20:53:58,649: DEBUG - ++ echo enable
2023-03-30 20:53:58,650: DEBUG - + action=enable
2023-03-30 20:53:58,651: DEBUG - + systemctl enable proc-hidepid --quiet --now
2023-03-30 20:53:59,091: DEBUG - + readlink -f /etc/dpkg/origins/default
2023-03-30 20:53:59,093: DEBUG - + grep -q debian
2023-03-30 20:54:00,096: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./02-ssl" post \'\' \'\' /usr/share/yunohost/ssl/openssl.cnf 7>&1']'
2023-03-30 20:54:00,108: DEBUG - + set -e
2023-03-30 20:54:00,109: DEBUG - + ssl_dir=/usr/share/yunohost/ssl
2023-03-30 20:54:00,110: DEBUG - + template_dir=/usr/share/yunohost/conf/ssl/
2023-03-30 20:54:00,110: DEBUG - + ynh_ca=/etc/yunohost/certs/yunohost.org/ca.pem
2023-03-30 20:54:00,110: DEBUG - + ynh_crt=/etc/yunohost/certs/yunohost.org/crt.pem
2023-03-30 20:54:00,110: DEBUG - + ynh_key=**********
2023-03-30 20:54:00,112: DEBUG - + do_post_regen /usr/share/yunohost/ssl/openssl.cnf
2023-03-30 20:54:00,112: DEBUG - + regen_conf_files=/usr/share/yunohost/ssl/openssl.cnf
2023-03-30 20:54:00,114: DEBUG - ++ openssl x509 -in /etc/yunohost/certs/yunohost.org/ca.pem -text
2023-03-30 20:54:00,116: DEBUG - ++ grep Issuer
2023-03-30 20:54:00,117: DEBUG - ++ awk '{print $4}'
2023-03-30 20:54:00,118: DEBUG - ++ tr , '\n'
2023-03-30 20:54:00,125: DEBUG - + current_local_ca_domain=yunohost.org
2023-03-30 20:54:00,126: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 20:54:00,128: DEBUG - + main_domain=maindomain.tld
2023-03-30 20:54:00,129: DEBUG - + '[' -e /usr/share/yunohost/yunohost-config/ssl/yunoCA ']'
2023-03-30 20:54:00,129: DEBUG - + mkdir -p /usr/share/yunohost/ssl/ca /usr/share/yunohost/ssl/certs /usr/share/yunohost/ssl/crl /usr/share/yunohost/ssl/newcerts
2023-03-30 20:54:00,131: DEBUG - + chown root:root /usr/share/yunohost/ssl
2023-03-30 20:54:00,142: DEBUG - + chmod 750 /usr/share/yunohost/ssl
2023-03-30 20:54:00,144: DEBUG - + chmod -R o-rwx /usr/share/yunohost/ssl
2023-03-30 20:54:00,149: DEBUG - + chmod o+x /usr/share/yunohost/ssl/certs
2023-03-30 20:54:00,151: DEBUG - + chmod o+r /usr/share/yunohost/ssl/certs/yunohost_crt.pem
2023-03-30 20:54:00,154: DEBUG - + [[ yunohost.org != \k\i\r\k\r\e\h\n\.\m\y\d\d\n\s\.\m\e ]]
2023-03-30 20:54:00,154: DEBUG - + regen_local_ca maindomain.tld
2023-03-30 20:54:00,155: DEBUG - + domain=maindomain.tld
2023-03-30 20:54:00,155: DEBUG - + echo -e '\n# Creating local certification authority with domain=maindomain.tld\n'
2023-03-30 20:54:00,156: DEBUG - 
2023-03-30 20:54:00,156: DEBUG - # Creating local certification authority with domain=maindomain.tld
2023-03-30 20:54:00,157: DEBUG - 
2023-03-30 20:54:00,157: DEBUG - + mkdir -p /etc/yunohost/certs/yunohost.org
2023-03-30 20:54:00,158: DEBUG - + mkdir -p /usr/share/yunohost/ssl/ca /usr/share/yunohost/ssl/certs /usr/share/yunohost/ssl/crl /usr/share/yunohost/ssl/newcerts
2023-03-30 20:54:00,161: DEBUG - + pushd /usr/share/yunohost/ssl
2023-03-30 20:54:00,161: DEBUG - /usr/share/yunohost/ssl /usr/share/yunohost/hooks/conf_regen
2023-03-30 20:54:00,162: DEBUG - + RANDFILE=.rnd
2023-03-30 20:54:00,162: DEBUG - + openssl rand -hex 19
2023-03-30 20:54:00,170: DEBUG - + rm -f index.txt
2023-03-30 20:54:00,172: DEBUG - + touch index.txt
2023-03-30 20:54:00,174: DEBUG - + cp /usr/share/yunohost/conf/ssl//openssl.cnf openssl.ca.cnf
2023-03-30 20:54:00,178: DEBUG - + sed -i s/yunohost.org/maindomain.tld/g openssl.ca.cnf
2023-03-30 20:54:00,182: DEBUG - + openssl req -x509 -new -config openssl.ca.cnf -days 3650 -out ca/cacert.pem -keyout ca/cakey.pem -nodes -batch -subj /CN=maindomain.tld/O=kirkrehn.myddns
2023-03-30 20:54:00,190: DEBUG - Generating a RSA private key
2023-03-30 20:54:00,216: DEBUG - .....+++++
2023-03-30 20:54:00,257: DEBUG - ..........+++++
2023-03-30 20:54:00,258: DEBUG - writing new private key to 'ca/cakey.pem'
2023-03-30 20:54:00,259: DEBUG - -----
2023-03-30 20:54:00,267: DEBUG - + chmod 640 ca/cacert.pem
2023-03-30 20:54:00,269: DEBUG - + chmod 640 ca/cakey.pem
2023-03-30 20:54:00,271: DEBUG - + cp ca/cacert.pem /etc/yunohost/certs/yunohost.org/ca.pem
2023-03-30 20:54:00,275: DEBUG - + ln -sf /etc/yunohost/certs/yunohost.org/ca.pem /etc/ssl/certs/ca-yunohost_crt.pem
2023-03-30 20:54:00,277: DEBUG - + update-ca-certificates
2023-03-30 20:54:00,285: DEBUG - Updating certificates in /etc/ssl/certs...
2023-03-30 20:54:01,225: DEBUG - 0 added, 0 removed; done.
2023-03-30 20:54:01,227: DEBUG - Running hooks in /etc/ca-certificates/update.d...
2023-03-30 20:54:01,230: DEBUG - done.
2023-03-30 20:54:01,235: DEBUG - + popd
2023-03-30 20:54:01,236: DEBUG - /usr/share/yunohost/hooks/conf_regen
2023-03-30 20:54:01,236: DEBUG - + ln -sf /etc/yunohost/certs/maindomain.tld/crt.pem /etc/ssl/certs/yunohost_crt.pem
2023-03-30 20:54:01,237: DEBUG - + ln -sf /etc/yunohost/certs/maindomain.tld/key.pem /etc/ssl/private/yunohost_key.pem
2023-03-30 20:54:02,241: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./03-ssh" post \'\' \'\' \'\' 7>&1']'
2023-03-30 20:54:02,252: DEBUG - + set -e
2023-03-30 20:54:02,253: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:02,255: DEBUG - +++ set +o
2023-03-30 20:54:02,256: DEBUG - +++ grep xtrace
2023-03-30 20:54:02,260: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:02,261: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:02,294: DEBUG - + do_post_regen
2023-03-30 20:54:02,295: DEBUG - + regen_conf_files=
2023-03-30 20:54:02,295: DEBUG - + return 0
2023-03-30 20:54:03,298: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./06-slapd" post \'\' \'\' /etc/ldap/ldap.conf,/etc/ldap/schema/mailserver.ldif,/etc/ldap/schema/sudo.ldif,/etc/ldap/schema/permission.ldif,/etc/default/slapd,/etc/systemd/system/slapd.service.d/ynh-override.conf 7>&1']'
2023-03-30 20:54:03,311: DEBUG - + set -e
2023-03-30 20:54:03,312: DEBUG - + tmp_backup_dir_file=/root/slapd-backup-dir.txt
2023-03-30 20:54:03,312: DEBUG - + config=/usr/share/yunohost/conf/slapd/config.ldif
2023-03-30 20:54:03,312: DEBUG - + db_init=/usr/share/yunohost/conf/slapd/db_init.ldif
2023-03-30 20:54:03,313: DEBUG - + do_post_regen /etc/ldap/ldap.conf,/etc/ldap/schema/mailserver.ldif,/etc/ldap/schema/sudo.ldif,/etc/ldap/schema/permission.ldif,/etc/default/slapd,/etc/systemd/system/slapd.service.d/ynh-override.conf
2023-03-30 20:54:03,314: DEBUG - + regen_conf_files=/etc/ldap/ldap.conf,/etc/ldap/schema/mailserver.ldif,/etc/ldap/schema/sudo.ldif,/etc/ldap/schema/permission.ldif,/etc/default/slapd,/etc/systemd/system/slapd.service.d/ynh-override.conf
2023-03-30 20:54:03,315: DEBUG - Enforce permissions on ldap/slapd directories and certs ...
2023-03-30 20:54:03,315: DEBUG - + usermod -aG ssl-cert openldap
2023-03-30 20:54:03,367: DEBUG - + chown -R openldap:openldap /etc/ldap/schema/
2023-03-30 20:54:03,379: DEBUG - + chown -R openldap:openldap /etc/ldap/slapd.d/
2023-03-30 20:54:03,383: DEBUG - + echo /etc/ldap/ldap.conf,/etc/ldap/schema/mailserver.ldif,/etc/ldap/schema/sudo.ldif,/etc/ldap/schema/permission.ldif,/etc/default/slapd,/etc/systemd/system/slapd.service.d/ynh-override.conf
2023-03-30 20:54:03,384: DEBUG - + sed 's/,/\n/g'
2023-03-30 20:54:03,385: DEBUG - + grep -q '^/etc/systemd/system/slapd.service.d/ynh-override.conf$'
2023-03-30 20:54:03,387: DEBUG - + systemctl daemon-reload
2023-03-30 20:54:03,824: DEBUG - + systemctl restart slapd
2023-03-30 20:54:03,960: DEBUG - + sleep 3
2023-03-30 20:54:06,965: DEBUG - + slapcat -H ldap:///cn=admins,ou=groups,dc=yunohost,dc=org
2023-03-30 20:54:06,967: DEBUG - + grep -q cn=admins,ou=groups,dc=yunohost,dc=org
2023-03-30 20:54:07,043: DEBUG - + '[' -z /etc/ldap/ldap.conf,/etc/ldap/schema/mailserver.ldif,/etc/ldap/schema/sudo.ldif,/etc/ldap/schema/permission.ldif,/etc/default/slapd,/etc/systemd/system/slapd.service.d/ynh-override.conf ']'
2023-03-30 20:54:07,044: DEBUG - Regenerate LDAP config directory from config.ldif
2023-03-30 20:54:07,045: DEBUG - + _regenerate_slapd_conf
2023-03-30 20:54:07,045: DEBUG - + rm -Rf /etc/ldap/slapd_new.d
2023-03-30 20:54:07,046: DEBUG - + mkdir /etc/ldap/slapd_new.d
2023-03-30 20:54:07,049: DEBUG - + slapadd -b cn=config -l /usr/share/yunohost/conf/slapd/config.ldif -F /etc/ldap/slapd_new.d/
2023-03-30 20:54:07,050: DEBUG - + grep -v 'none elapsed\|Closing DB'
2023-03-30 20:54:07,091: DEBUG - + true
2023-03-30 20:54:07,091: DEBUG - + slaptest -Q -u -F /etc/ldap/slapd_new.d
2023-03-30 20:54:07,122: DEBUG - + rm -Rf /etc/ldap/slapd.d
2023-03-30 20:54:07,125: DEBUG - + mv /etc/ldap/slapd_new.d /etc/ldap/slapd.d
2023-03-30 20:54:07,128: DEBUG - + chown -R openldap:openldap /etc/ldap/slapd.d/
2023-03-30 20:54:07,132: DEBUG - ++ cat /root/slapd-backup-dir.txt
2023-03-30 20:54:07,134: DEBUG - ++ true
2023-03-30 20:54:07,136: DEBUG - + backup_dir=
2023-03-30 20:54:07,137: DEBUG - Running slapdindex
2023-03-30 20:54:07,137: DEBUG - + su openldap -s /bin/bash -c /usr/sbin/slapindex
2023-03-30 20:54:07,540: DEBUG - Reloading slapd
2023-03-30 20:54:07,541: DEBUG - + systemctl force-reload slapd
2023-03-30 20:54:07,680: DEBUG - + number_of_wait=0
2023-03-30 20:54:07,681: DEBUG - + su admin -c ''
2023-03-30 20:54:08,684: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./09-nslcd" post \'\' \'\' /etc/nslcd.conf 7>&1']'
2023-03-30 20:54:08,696: DEBUG - + set -e
2023-03-30 20:54:08,698: DEBUG - + do_post_regen /etc/nslcd.conf
2023-03-30 20:54:08,698: DEBUG - + regen_conf_files=/etc/nslcd.conf
2023-03-30 20:54:08,699: DEBUG - + [[ -z /etc/nslcd.conf ]]
2023-03-30 20:54:08,699: DEBUG - + systemctl restart nslcd
2023-03-30 20:54:09,702: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./10-apt" post \'\' \'\' /etc/apt/sources.list.d/extra_php_version.list,/etc/apt/preferences.d/extra_php_version,/etc/apt/preferences.d/ban_packages 7>&1']'
2023-03-30 20:54:09,714: DEBUG - + set -e
2023-03-30 20:54:09,715: DEBUG - + do_post_regen /etc/apt/sources.list.d/extra_php_version.list,/etc/apt/preferences.d/extra_php_version,/etc/apt/preferences.d/ban_packages
2023-03-30 20:54:09,716: DEBUG - + regen_conf_files=/etc/apt/sources.list.d/extra_php_version.list,/etc/apt/preferences.d/extra_php_version,/etc/apt/preferences.d/ban_packages
2023-03-30 20:54:09,716: DEBUG - + [[ ! -s /etc/apt/trusted.gpg.d/extra_php_version.gpg ]]
2023-03-30 20:54:09,720: DEBUG - + wget --timeout 900 --quiet https://packages.sury.org/php/apt.gpg --output-document=-
2023-03-30 20:54:09,721: DEBUG - + gpg --dearmor
2023-03-30 20:54:10,344: DEBUG - + update-alternatives --set php /usr/bin/php7.4
2023-03-30 20:54:11,347: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./12-metronome" post \'\' \'\' /etc/metronome/metronome.cfg.lua,/etc/metronome/conf.d/maindomain.tld.cfg.lua 7>&1']'
2023-03-30 20:54:11,360: DEBUG - + set -e
2023-03-30 20:54:11,361: DEBUG - + dpkg --list
2023-03-30 20:54:11,362: DEBUG - + grep -q 'ii *metronome '
2023-03-30 20:54:11,393: DEBUG - + do_post_regen /etc/metronome/metronome.cfg.lua,/etc/metronome/conf.d/maindomain.tld.cfg.lua
2023-03-30 20:54:11,394: DEBUG - + regen_conf_files=/etc/metronome/metronome.cfg.lua,/etc/metronome/conf.d/maindomain.tld.cfg.lua
2023-03-30 20:54:11,394: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 20:54:11,396: DEBUG - + main_domain=maindomain.tld
2023-03-30 20:54:11,397: DEBUG - + for domain in $YNH_MAIN_DOMAINS
2023-03-30 20:54:11,397: DEBUG - + mkdir -p /var/lib/metronome/maindomain%2etld/pep
2023-03-30 20:54:11,400: DEBUG - + mkdir -p /var/xmpp-upload/maindomain.tld/upload
2023-03-30 20:54:11,403: DEBUG - + chmod g+s /var/xmpp-upload/maindomain.tld/upload
2023-03-30 20:54:11,405: DEBUG - + '[' '!' -e /var/xmpp-upload ']'
2023-03-30 20:54:11,406: DEBUG - + chown -R metronome:www-data /var/xmpp-upload/
2023-03-30 20:54:11,416: DEBUG - + '[' '!' -e /var/xmpp-upload ']'
2023-03-30 20:54:11,417: DEBUG - + chmod 750 /var/xmpp-upload/
2023-03-30 20:54:11,418: DEBUG - + usermod -aG ssl-cert metronome
2023-03-30 20:54:11,440: DEBUG - + chown -R metronome: /var/lib/metronome/
2023-03-30 20:54:11,451: DEBUG - + chown -R metronome: /etc/metronome/conf.d/
2023-03-30 20:54:11,453: DEBUG - + [[ -z /etc/metronome/metronome.cfg.lua,/etc/metronome/conf.d/maindomain.tld.cfg.lua ]]
2023-03-30 20:54:11,454: DEBUG - + systemctl restart metronome
2023-03-30 20:54:12,457: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" post \'\' \'\' /etc/nginx/conf.d/security.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf.inc,/etc/nginx/conf.d/yunohost_api.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf,/etc/nginx/conf.d/yunohost_panel.conf.inc,/etc/nginx/conf.d/maindomain.tld.conf,/etc/nginx/conf.d/ssowat.conf,/etc/nginx/conf.d/acme-challenge.conf.inc,/etc/nginx/conf.d/global.conf,/etc/nginx/conf.d/yunohost_sso.conf.inc,/etc/nginx/conf.d/default.d/redirect_to_admin.conf,/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml 7>&1']'
2023-03-30 20:54:12,474: DEBUG - + set -e
2023-03-30 20:54:12,475: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:12,477: DEBUG - +++ set +o
2023-03-30 20:54:12,477: DEBUG - +++ grep xtrace
2023-03-30 20:54:12,481: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:12,482: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:12,517: DEBUG - + do_post_regen /etc/nginx/conf.d/security.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf.inc,/etc/nginx/conf.d/yunohost_api.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf,/etc/nginx/conf.d/yunohost_panel.conf.inc,/etc/nginx/conf.d/maindomain.tld.conf,/etc/nginx/conf.d/ssowat.conf,/etc/nginx/conf.d/acme-challenge.conf.inc,/etc/nginx/conf.d/global.conf,/etc/nginx/conf.d/yunohost_sso.conf.inc,/etc/nginx/conf.d/default.d/redirect_to_admin.conf,/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-30 20:54:12,518: DEBUG - + regen_conf_files=/etc/nginx/conf.d/security.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf.inc,/etc/nginx/conf.d/yunohost_api.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf,/etc/nginx/conf.d/yunohost_panel.conf.inc,/etc/nginx/conf.d/maindomain.tld.conf,/etc/nginx/conf.d/ssowat.conf,/etc/nginx/conf.d/acme-challenge.conf.inc,/etc/nginx/conf.d/global.conf,/etc/nginx/conf.d/yunohost_sso.conf.inc,/etc/nginx/conf.d/default.d/redirect_to_admin.conf,/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-30 20:54:12,519: DEBUG - + '[' -z /etc/nginx/conf.d/security.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf.inc,/etc/nginx/conf.d/yunohost_api.conf.inc,/etc/nginx/conf.d/yunohost_admin.conf,/etc/nginx/conf.d/yunohost_panel.conf.inc,/etc/nginx/conf.d/maindomain.tld.conf,/etc/nginx/conf.d/ssowat.conf,/etc/nginx/conf.d/acme-challenge.conf.inc,/etc/nginx/conf.d/global.conf,/etc/nginx/conf.d/yunohost_sso.conf.inc,/etc/nginx/conf.d/default.d/redirect_to_admin.conf,/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml ']'
2023-03-30 20:54:12,519: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 20:54:12,520: DEBUG - + mkdir -p /etc/nginx/conf.d/maindomain.tld.d
2023-03-30 20:54:12,521: DEBUG - + nginx -t
2023-03-30 20:54:12,670: DEBUG - + pgrep nginx
2023-03-30 20:54:12,703: DEBUG - 807
2023-03-30 20:54:12,704: DEBUG - 808
2023-03-30 20:54:12,705: DEBUG - 2385
2023-03-30 20:54:12,705: DEBUG - 2386
2023-03-30 20:54:12,706: DEBUG - 2387
2023-03-30 20:54:12,706: DEBUG - 2388
2023-03-30 20:54:12,706: DEBUG - + systemctl reload nginx
2023-03-30 20:54:13,710: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./19-postfix" post \'\' \'\' /etc/postfix/ldap-domains.cf,/etc/postfix/header_checks,/etc/postfix/sender_canonical,/etc/postfix/ldap-aliases.cf,/etc/postfix/master.cf,/etc/postfix/main.cf,/etc/postfix/ldap-accounts.cf,/etc/postfix/sni,/etc/postfix/smtp_reply_filter,/etc/default/postsrsd 7>&1']'
2023-03-30 20:54:13,722: DEBUG - + set -e
2023-03-30 20:54:13,723: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:13,724: DEBUG - +++ set +o
2023-03-30 20:54:13,725: DEBUG - +++ grep xtrace
2023-03-30 20:54:13,728: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:13,729: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:13,763: DEBUG - + do_post_regen /etc/postfix/ldap-domains.cf,/etc/postfix/header_checks,/etc/postfix/sender_canonical,/etc/postfix/ldap-aliases.cf,/etc/postfix/master.cf,/etc/postfix/main.cf,/etc/postfix/ldap-accounts.cf,/etc/postfix/sni,/etc/postfix/smtp_reply_filter,/etc/default/postsrsd
2023-03-30 20:54:13,764: DEBUG - + regen_conf_files=/etc/postfix/ldap-domains.cf,/etc/postfix/header_checks,/etc/postfix/sender_canonical,/etc/postfix/ldap-aliases.cf,/etc/postfix/master.cf,/etc/postfix/main.cf,/etc/postfix/ldap-accounts.cf,/etc/postfix/sni,/etc/postfix/smtp_reply_filter,/etc/default/postsrsd
2023-03-30 20:54:13,764: DEBUG - + '[' -e /etc/postfix/sasl_passwd ']'
2023-03-30 20:54:13,765: DEBUG - + postmap -F hash:/etc/postfix/sni
2023-03-30 20:54:13,869: DEBUG - + [[ -z /etc/postfix/ldap-domains.cf,/etc/postfix/header_checks,/etc/postfix/sender_canonical,/etc/postfix/ldap-aliases.cf,/etc/postfix/master.cf,/etc/postfix/main.cf,/etc/postfix/ldap-accounts.cf,/etc/postfix/sni,/etc/postfix/smtp_reply_filter,/etc/default/postsrsd ]]
2023-03-30 20:54:13,870: DEBUG - + systemctl restart postfix
2023-03-30 20:54:15,037: DEBUG - + systemctl restart postsrsd
2023-03-30 20:54:16,041: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./25-dovecot" post \'\' \'\' /etc/dovecot/dovecot-ldap.conf,/etc/dovecot/dovecot.conf,/etc/dovecot/yunohost.d/pre-ext.conf,/etc/dovecot/yunohost.d/post-ext.conf,/etc/dovecot/global_script/dovecot.sieve 7>&1']'
2023-03-30 20:54:16,053: DEBUG - + set -e
2023-03-30 20:54:16,054: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:16,056: DEBUG - +++ set +o
2023-03-30 20:54:16,057: DEBUG - +++ grep xtrace
2023-03-30 20:54:16,060: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:16,061: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:16,094: DEBUG - + do_post_regen /etc/dovecot/dovecot-ldap.conf,/etc/dovecot/dovecot.conf,/etc/dovecot/yunohost.d/pre-ext.conf,/etc/dovecot/yunohost.d/post-ext.conf,/etc/dovecot/global_script/dovecot.sieve
2023-03-30 20:54:16,095: DEBUG - + regen_conf_files=/etc/dovecot/dovecot-ldap.conf,/etc/dovecot/dovecot.conf,/etc/dovecot/yunohost.d/pre-ext.conf,/etc/dovecot/yunohost.d/post-ext.conf,/etc/dovecot/global_script/dovecot.sieve
2023-03-30 20:54:16,096: DEBUG - + mkdir -p /etc/dovecot/yunohost.d/pre-ext.d
2023-03-30 20:54:16,098: DEBUG - + mkdir -p /etc/dovecot/yunohost.d/post-ext.d
2023-03-30 20:54:16,101: DEBUG - + id vmail
2023-03-30 20:54:16,111: DEBUG - + adduser --system --ingroup mail --uid 500 vmail --home /var/vmail --no-create-home
2023-03-30 20:54:16,278: DEBUG - Warning: The home dir /var/vmail you specified can't be accessed: No such file or directory
2023-03-30 20:54:16,278: DEBUG - Adding system user `vmail' (UID 500) ...
2023-03-30 20:54:16,290: DEBUG - Adding new user `vmail' (UID 500) with group `mail' ...
2023-03-30 20:54:16,464: DEBUG - Not creating home directory `/var/vmail'.
2023-03-30 20:54:16,468: DEBUG - + '[' '!' -e /home/vmail ']'
2023-03-30 20:54:16,469: DEBUG - + chown -R vmail:mail /etc/dovecot/global_script
2023-03-30 20:54:16,479: DEBUG - + chmod 770 /etc/dovecot/global_script
2023-03-30 20:54:16,481: DEBUG - + chown root:mail /var/mail
2023-03-30 20:54:16,488: DEBUG - + chmod 1775 /var/mail
2023-03-30 20:54:16,490: DEBUG - + '[' -z /etc/dovecot/dovecot-ldap.conf,/etc/dovecot/dovecot.conf,/etc/dovecot/yunohost.d/pre-ext.conf,/etc/dovecot/yunohost.d/post-ext.conf,/etc/dovecot/global_script/dovecot.sieve ']'
2023-03-30 20:54:16,491: DEBUG - + [[ /etc/dovecot/dovecot-ldap.conf,/etc/dovecot/dovecot.conf,/etc/dovecot/yunohost.d/pre-ext.conf,/etc/dovecot/yunohost.d/post-ext.conf,/etc/dovecot/global_script/dovecot.sieve =~ dovecot\.sieve ]]
2023-03-30 20:54:16,492: DEBUG - + sievec /etc/dovecot/global_script/dovecot.sieve
2023-03-30 20:54:16,530: DEBUG - + chown -R vmail:mail /etc/dovecot/global_script
2023-03-30 20:54:16,533: DEBUG - + systemctl restart dovecot
2023-03-30 20:54:18,537: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./31-rspamd" post \'\' \'\' /etc/rspamd/local.d/dkim_signing.conf,/etc/rspamd/local.d/metrics.conf,/etc/dovecot/global_script/rspamd.sieve 7>&1']'
2023-03-30 20:54:18,549: DEBUG - + set -e
2023-03-30 20:54:18,550: DEBUG - + do_post_regen /etc/rspamd/local.d/dkim_signing.conf,/etc/rspamd/local.d/metrics.conf,/etc/dovecot/global_script/rspamd.sieve
2023-03-30 20:54:18,551: DEBUG - + mkdir -p /etc/dkim
2023-03-30 20:54:18,554: DEBUG - + chown _rspamd /etc/dkim
2023-03-30 20:54:18,5fv60: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 20:54:18,561: DEBUG - + domain_key=**********
2023-03-30 20:54:18,561: DEBUG - + '[' '!' -f ********** ']'
2023-03-30 20:54:18,562: DEBUG - + opendkim-genkey --domain=maindomain.tld --selector=mail --directory=/etc/dkim -b 1024
2023-03-30 20:54:18,743: DEBUG - + mv /etc/dkim/mail.private **********
2023-03-30 20:54:18,746: DEBUG - + mv /etc/dkim/mail.txt /etc/dkim/maindomain.tld.mail.txt
2023-03-30 20:54:18,749: DEBUG - + chown _rspamd **********
2023-03-30 20:54:18,752: DEBUG - + chmod 400 **********
2023-03-30 20:54:18,754: DEBUG - + '[' '!' -e /var/log/rspamd ']'
2023-03-30 20:54:18,754: DEBUG - + chown -R _rspamd:_rspamd /var/log/rspamd
2023-03-30 20:54:18,761: DEBUG - + regen_conf_files=/etc/rspamd/local.d/dkim_signing.conf,/etc/rspamd/local.d/metrics.conf,/etc/dovecot/global_script/rspamd.sieve
2023-03-30 20:54:18,761: DEBUG - + '[' -z /etc/rspamd/local.d/dkim_signing.conf,/etc/rspamd/local.d/metrics.conf,/etc/dovecot/global_script/rspamd.sieve ']'
2023-03-30 20:54:18,762: DEBUG - + [[ /etc/rspamd/local.d/dkim_signing.conf,/etc/rspamd/local.d/metrics.conf,/etc/dovecot/global_script/rspamd.sieve =~ rspamd\.sieve ]]
2023-03-30 20:54:18,762: DEBUG - + sievec /etc/dovecot/global_script/rspamd.sieve
2023-03-30 20:54:18,779: DEBUG - + chown -R vmail:mail /etc/dovecot/global_script
2023-03-30 20:54:18,781: DEBUG - + systemctl restart dovecot
2023-03-30 20:54:20,127: DEBUG - + systemctl -q restart rspamd.service
2023-03-30 20:54:21,131: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./34-mysql" post \'\' \'\' \'\' 7>&1']'
2023-03-30 20:54:21,143: DEBUG - + set -e
2023-03-30 20:54:21,144: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:21,145: DEBUG - +++ set +o
2023-03-30 20:54:21,146: DEBUG - +++ grep xtrace
2023-03-30 20:54:21,149: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:21,150: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:21,184: DEBUG - + dpkg --list
2023-03-30 20:54:21,185: DEBUG - + grep -q 'ii *mariadb-server '
2023-03-30 20:54:21,219: DEBUG - + do_post_regen
2023-03-30 20:54:21,221: DEBUG - + regen_conf_files=
2023-03-30 20:54:21,222: DEBUG - + [[ ! -d /var/lib/mysql/mysql ]]
2023-03-30 20:54:21,222: DEBUG - + '[' '!' -e /etc/systemd/system/mysql.service ']'
2023-03-30 20:54:21,223: DEBUG - + systemctl stop mysql -q
2023-03-30 20:54:21,515: DEBUG - + systemctl disable mysql -q
2023-03-30 20:54:22,001: DEBUG - + systemctl disable mariadb -q
2023-03-30 20:54:22,591: WARNING - insserv: warning: current start runlevel(s) (empty) of script `mariadb' overrides LSB defaults (2 3 4 5).
2023-03-30 20:54:22,592: WARNING - insserv: warning: current stop runlevel(s) (0 1 2 3 4 5 6) of script `mariadb' overrides LSB defaults (0 1 6).
2023-03-30 20:54:23,539: DEBUG - + systemctl enable mariadb -q
2023-03-30 20:54:23,616: WARNING - insserv: warning: current start runlevel(s) (empty) of script `mariadb' overrides LSB defaults (2 3 4 5).
2023-03-30 20:54:23,617: WARNING - insserv: warning: current stop runlevel(s) (0 1 2 3 4 5 6) of script `mariadb' overrides LSB defaults (0 1 6).
2023-03-30 20:54:25,042: DEBUG - + systemctl is-active mariadb -q
2023-03-30 20:54:25,050: DEBUG - + systemctl start mariadb
2023-03-30 20:54:25,423: DEBUG - + [[ -z '' ]]
2023-03-30 20:54:26,427: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./35-postgresql" post \'\' \'\' \'\' 7>&1']'
2023-03-30 20:54:26,438: DEBUG - + set -e
2023-03-30 20:54:26,439: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:26,441: DEBUG - +++ set +o
2023-03-30 20:54:26,442: DEBUG - +++ grep xtrace
2023-03-30 20:54:26,445: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:26,446: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:26,480: DEBUG - + dpkg --list
2023-03-30 20:54:26,481: DEBUG - + grep -q 'ii *postgresql-13 '
2023-03-30 20:54:26,515: DEBUG - postgresql is not installed, skipping
2023-03-30 20:54:27,519: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./36-redis" post \'\' \'\' \'\' 7>&1']'
2023-03-30 20:54:27,531: DEBUG - + do_post_regen
2023-03-30 20:54:27,532: DEBUG - + chown -R redis:adm /var/log/redis
2023-03-30 20:54:28,538: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./37-mdns" post \'\' \'\' /etc/yunohost/mdns.yml,/etc/systemd/system/yunomdns.service 7>&1']'
2023-03-30 20:54:28,562: DEBUG - + set -e
2023-03-30 20:54:28,565: DEBUG - + do_post_regen /etc/yunohost/mdns.yml,/etc/systemd/system/yunomdns.service
2023-03-30 20:54:28,567: DEBUG - + regen_conf_files=/etc/yunohost/mdns.yml,/etc/systemd/system/yunomdns.service
2023-03-30 20:54:28,568: DEBUG - + chown mdns:mdns /etc/yunohost/mdns.yml
2023-03-30 20:54:28,590: DEBUG - + echo /etc/yunohost/mdns.yml,/etc/systemd/system/yunomdns.service
2023-03-30 20:54:28,592: DEBUG - + sed 's/,/\n/g'
2023-03-30 20:54:28,593: DEBUG - + grep -q '^/etc/systemd/system/yunomdns.service$'
2023-03-30 20:54:28,598: DEBUG - + systemctl daemon-reload
2023-03-30 20:54:29,064: DEBUG - + systemctl disable avahi-daemon.socket --quiet --now
2023-03-30 20:54:29,518: DEBUG - + systemctl disable avahi-daemon --quiet --now
2023-03-30 20:54:31,022: DEBUG - + [[ -e /etc/avahi/avahi-daemon.conf ]]
2023-03-30 20:54:31,025: DEBUG - + grep -q yunohost /etc/avahi/avahi-daemon.conf
2023-03-30 20:54:31,028: DEBUG - + [[ -z /etc/yunohost/mdns.yml,/etc/systemd/system/yunomdns.service ]]
2023-03-30 20:54:31,029: DEBUG - + systemctl restart yunomdns
2023-03-30 20:54:32,032: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./43-dnsmasq" post \'\' \'\' /etc/resolv.dnsmasq.conf,/etc/dnsmasq.conf,/etc/dnsmasq.d/maindomain.tld,/etc/default/dnsmasq 7>&1']'
2023-03-30 20:54:32,044: DEBUG - + set -e
2023-03-30 20:54:32,046: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:32,046: DEBUG - +++ set +o
2023-03-30 20:54:32,047: DEBUG - +++ grep xtrace
2023-03-30 20:54:32,050: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:32,051: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:32,086: DEBUG - + do_post_regen /etc/resolv.dnsmasq.conf,/etc/dnsmasq.conf,/etc/dnsmasq.d/maindomain.tld,/etc/default/dnsmasq
2023-03-30 20:54:32,086: DEBUG - + regen_conf_files=/etc/resolv.dnsmasq.conf,/etc/dnsmasq.conf,/etc/dnsmasq.d/maindomain.tld,/etc/default/dnsmasq
2023-03-30 20:54:32,087: DEBUG - + chown 644 /etc/resolv.dnsmasq.conf
2023-03-30 20:54:32,095: DEBUG - + grep -q -E '^ *(domain|search)' /run/resolvconf/resolv.conf
2023-03-30 20:54:32,098: DEBUG - + grep -q -E '^ *(domain|search)' '/run/resolvconf/interface/*.dhclient'
2023-03-30 20:54:32,102: DEBUG - + grep -q '^supersede domain-name "";' /etc/dhcp/dhclient.conf
2023-03-30 20:54:32,108: DEBUG - + grep -q '^supersede domain-search "";' /etc/dhcp/dhclient.conf
2023-03-30 20:54:32,112: DEBUG - + grep -q '^supersede search "";' /etc/dhcp/dhclient.conf
2023-03-30 20:54:32,115: DEBUG - + systemctl restart resolvconf
2023-03-30 20:54:32,142: DEBUG - ++ hostname -s
2023-03-30 20:54:32,145: DEBUG - + short_hostname=kirkrehn
2023-03-30 20:54:32,146: DEBUG - + grep -q '127.0.0.1.*kirkrehn' /etc/hosts
2023-03-30 20:54:32,149: DEBUG - + echo -e '\n127.0.0.1\tkirkrehn'
2023-03-30 20:54:32,150: DEBUG - + [[ -n /etc/resolv.dnsmasq.conf,/etc/dnsmasq.conf,/etc/dnsmasq.d/maindomain.tld,/etc/default/dnsmasq ]]
2023-03-30 20:54:32,150: DEBUG - + for SERVICE in systemd-resolved bind9
2023-03-30 20:54:32,151: DEBUG - + systemctl is-enabled systemd-resolved
2023-03-30 20:54:32,173: DEBUG - + systemctl is-active systemd-resolved
2023-03-30 20:54:32,188: DEBUG - + for SERVICE in systemd-resolved bind9
2023-03-30 20:54:32,190: DEBUG - + systemctl is-enabled bind9
2023-03-30 20:54:32,198: DEBUG - + systemctl is-active bind9
2023-03-30 20:54:32,206: DEBUG - + systemctl restart dnsmasq
2023-03-30 20:54:34,210: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./46-nsswitch" post \'\' \'\' /etc/nsswitch.conf 7>&1']'
2023-03-30 20:54:34,222: DEBUG - + set -e
2023-03-30 20:54:34,223: DEBUG - + do_post_regen /etc/nsswitch.conf
2023-03-30 20:54:34,224: DEBUG - + regen_conf_files=/etc/nsswitch.conf
2023-03-30 20:54:34,224: DEBUG - + [[ -z /etc/nsswitch.conf ]]
2023-03-30 20:54:34,225: DEBUG - + systemctl restart unscd
2023-03-30 20:54:35,228: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./52-fail2ban" post \'\' \'\' /etc/fail2ban/jail.conf,/etc/fail2ban/filter.d/yunohost.conf,/etc/fail2ban/jail.d/yunohost-jails.conf 7>&1']'
2023-03-30 20:54:35,244: DEBUG - + set -e
2023-03-30 20:54:35,245: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 20:54:35,246: DEBUG - +++ set +o
2023-03-30 20:54:35,246: DEBUG - +++ grep xtrace
2023-03-30 20:54:35,250: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 20:54:35,250: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 20:54:35,285: DEBUG - + do_post_regen /etc/fail2ban/jail.conf,/etc/fail2ban/filter.d/yunohost.conf,/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-30 20:54:35,286: DEBUG - + regen_conf_files=/etc/fail2ban/jail.conf,/etc/fail2ban/filter.d/yunohost.conf,/etc/fail2ban/jail.d/yunohost-jails.conf
2023-03-30 20:54:35,286: DEBUG - + [[ -z /etc/fail2ban/jail.conf,/etc/fail2ban/filter.d/yunohost.conf,/etc/fail2ban/jail.d/yunohost-jails.conf ]]
2023-03-30 20:54:35,287: DEBUG - + systemctl reload fail2ban
2023-03-30 20:54:36,289: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-195316-regen_conf-all" style="text-decoration:underline">Regenerate system configurations 'all'</a>'
2023-03-30 20:54:36,308: SUCCESS - YunoHost is now configured
2023-03-30 20:54:36,309: WARNING - The post-install completed! To finalize your setup, please consider:
    - adding a first user through the 'Users' section of the webadmin (or 'yunohost user create <username>' in command-line);
    - diagnose potential issues through the 'Diagnosis' section of the webadmin (or 'yunohost diagnosis run' in command-line);
    - reading the 'Finalizing your setup' and 'Getting to know YunoHost' parts in the admin documentation: https://yunohost.org/admindoc.
```

### reload services

```sh
systemctl reload postfix
systemctl daemon-reload
```

### run yunohost update/upgrade

```sh
args:
  target: system
ended_at: 2023-03-30 20:15:03.630491
error: null
interface: api
operation: tools_upgrade
parent: null
related_to: []
started_at: 2023-03-30 20:06:56.555718
success: true
yunohost_version: 11.1.15

============

2023-03-30 21:06:56,572: INFO - Upgrading system packages
2023-03-30 21:06:56,573: DEBUG - Running apt command :
DEBIAN_FRONTEND=noninteractive YUNOHOST_API_RESTART_WILL_BE_HANDLED_BY_YUNOHOST=yes APT_LISTCHANGES_FRONTEND=none apt-get --fix-broken --show-upgraded --assume-yes --quiet -o=Dpkg::Use-Pty=0 -o Dpkg::Options::="--force-confold" -o Dpkg::Options::="--force-confmiss" -o Dpkg::Options::="--force-confdef" dist-upgrade
2023-03-30 21:06:56,661: INFO - + Reading package lists...
2023-03-30 21:06:57,366: INFO - + Building dependency tree...
2023-03-30 21:06:57,369: INFO - + Reading state information...
2023-03-30 21:06:58,164: INFO - + Calculating upgrade...
2023-03-30 21:06:58,664: INFO - + The following package was automatically installed and is no longer required:
2023-03-30 21:06:58,666: INFO - +   raspinfo
2023-03-30 21:06:58,667: INFO - + Use 'apt autoremove' to remove it.
2023-03-30 21:06:58,983: INFO - + The following NEW packages will be installed:
2023-03-30 21:06:58,986: INFO - +   libabsl20200923 libaom0 libavif9 libdav1d4 libde265-0 libgav1-0 libheif1
2023-03-30 21:06:58,991: INFO - +   libnuma1 libx265-192 raspi-utils
2023-03-30 21:06:59,006: INFO - + The following packages will be upgraded:
2023-03-30 21:06:59,009: INFO - +   base-files bind9-dnsutils bind9-host bind9-libs bluez-firmware curl
2023-03-30 21:06:59,012: INFO - +   distro-info-data git git-man libcurl3-gnutls libcurl4 libgd3 libgnutls30
2023-03-30 21:06:59,015: INFO - +   libksba8 libmariadb3 libnftables1 libnss3 libpcre2-8-0 libpcre3
2023-03-30 21:06:59,018: INFO - +   libraspberrypi-bin libraspberrypi-dev libraspberrypi-doc libraspberrypi0
2023-03-30 21:06:59,021: INFO - +   libssl1.1 libtasn1-6 libtiff5 libxml2 linux-libc-dev mariadb-client-10.5
2023-03-30 21:06:59,024: INFO - +   mariadb-client-core-10.5 mariadb-common mariadb-server mariadb-server-10.5
2023-03-30 21:06:59,027: INFO - +   mariadb-server-core-10.5 moulinette nano nftables openssl php-common
2023-03-30 21:06:59,030: INFO - +   php7.4-cli php7.4-common php7.4-curl php7.4-fpm php7.4-gd php7.4-intl
2023-03-30 21:06:59,033: INFO - +   php7.4-json php7.4-ldap php7.4-mbstring php7.4-mysql php7.4-opcache
2023-03-30 21:06:59,034: INFO - +   php7.4-readline php7.4-xml postfix postfix-ldap postfix-pcre python3-lexicon
2023-03-30 21:06:59,036: INFO - +   raspberrypi-bootloader raspberrypi-kernel raspi-config raspinfo rpi-eeprom
2023-03-30 21:06:59,037: INFO - +   ssowat sudo-ldap tzdata yunohost yunohost-admin
2023-03-30 21:06:59,834: INFO - + 66 upgraded, 10 newly installed, 0 to remove and 0 not upgraded.
2023-03-30 21:06:59,836: INFO - + Need to get 85.9 MB of archives.
2023-03-30 21:06:59,837: INFO - + After this operation, 16.0 MB of additional disk space will be used.
2023-03-30 21:06:59,838: INFO - + Get:1 http://deb.debian.org/debian bullseye/main arm64 base-files arm64 11.1+deb11u6 [70.1 kB]
2023-03-30 21:06:59,855: INFO - + Get:2 http://security.debian.org/debian-security bullseye-security/main arm64 bind9-libs arm64 1:9.16.37-1~deb11u1 [1,309 kB]
2023-03-30 21:07:00,382: INFO - + Get:3 http://deb.debian.org/debian bullseye/main arm64 postfix arm64 3.5.17-0+deb11u1 [1,503 kB]
2023-03-30 21:07:03,940: INFO - + Get:4 http://security.debian.org/debian-security bullseye-security/main arm64 bind9-dnsutils arm64 1:9.16.37-1~deb11u1 [399 kB]
2023-03-30 21:07:04,094: INFO - + Get:5 http://deb.debian.org/debian bullseye/main arm64 postfix-pcre arm64 3.5.17-0+deb11u1 [361 kB]
2023-03-30 21:07:04,820: INFO - + Get:6 http://archive.raspberrypi.org/debian bullseye/main arm64 libssl1.1 arm64 1.1.1n-0+deb11u4+rpt1 [1,394 kB]
2023-03-30 21:07:05,137: INFO - + Get:7 http://forge.yunohost.org/debian bullseye/stable arm64 moulinette all 11.1.4 [72.4 kB]
2023-03-30 21:07:05,409: INFO - + Get:8 https://packages.sury.org/php bullseye/main arm64 libxml2 arm64 2.9.14+dfsg-0+0~20220524.12+debian11~1.gbpc5dc45 [640 kB]
2023-03-30 21:07:05,958: INFO - + Get:9 http://security.debian.org/debian-security bullseye-security/main arm64 bind9-host arm64 1:9.16.37-1~deb11u1 [306 kB]
2023-03-30 21:07:05,976: INFO - + Get:10 http://deb.debian.org/debian bullseye/main arm64 postfix-ldap arm64 3.5.17-0+deb11u1 [372 kB]
2023-03-30 21:07:06,754: INFO - + Get:11 http://forge.yunohost.org/debian bullseye/stable arm64 ssowat all 11.1.4 [762 kB]
2023-03-30 21:07:07,190: INFO - + Get:12 http://archive.raspberrypi.org/debian bullseye/main arm64 openssl arm64 1.1.1n-0+deb11u4+rpt1 [831 kB]
2023-03-30 21:07:07,234: INFO - + Get:13 http://security.debian.org/debian-security bullseye-security/main arm64 sudo-ldap arm64 1.9.5p2-3+deb11u1 [1,029 kB]
2023-03-30 21:07:07,264: INFO - + Get:14 https://packages.sury.org/php bullseye/main arm64 libpcre3 arm64 2:8.44-2+0~20210301.9+debian11~1.gbpa278ad [323 kB]
2023-03-30 21:07:07,756: INFO - + Get:15 https://packages.sury.org/php bullseye/main arm64 libpcre2-8-0 arm64 10.40-1+0~20220713.16+debian11~1.gbpb6cec5 [228 kB]
2023-03-30 21:07:07,985: INFO - + Get:16 https://packages.sury.org/php bullseye/main arm64 libgd3 arm64 2.3.3-9+0~20230207.13+debian11~1.gbp649015 [130 kB]
2023-03-30 21:07:07,993: INFO - + Get:17 https://packages.sury.org/php bullseye/main arm64 php-common all 2:93+0~20221211.45+debian11~1.gbpdb4dcc [16.4 kB]
2023-03-30 21:07:07,997: INFO - + Get:18 https://packages.sury.org/php bullseye/main arm64 php7.4-xml arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [89.7 kB]
2023-03-30 21:07:08,002: INFO - + Get:19 https://packages.sury.org/php bullseye/main arm64 php7.4-readline arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [11.7 kB]
2023-03-30 21:07:08,005: INFO - + Get:20 https://packages.sury.org/php bullseye/main arm64 php7.4-opcache arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [180 kB]
2023-03-30 21:07:08,020: INFO - + Get:21 https://packages.sury.org/php bullseye/main arm64 php7.4-mysql arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [111 kB]
2023-03-30 21:07:08,189: INFO - + Get:22 http://archive.raspberrypi.org/debian bullseye/main arm64 linux-libc-dev arm64 1:1.20230317-1 [1,134 kB]
2023-03-30 21:07:08,218: INFO - + Get:23 http://archive.raspberrypi.org/debian bullseye/main arm64 bluez-firmware all 1.2-4+rpt10 [200 kB]
2023-03-30 21:07:08,223: INFO - + Get:24 http://archive.raspberrypi.org/debian bullseye/main arm64 libraspberrypi-dev arm64 1:2+git20220616~133208+6e8f786-1 [129 kB]
2023-03-30 21:07:08,227: INFO - + Get:25 http://archive.raspberrypi.org/debian bullseye/main arm64 raspberrypi-kernel arm64 1:1.20230317-1 [27.0 MB]
2023-03-30 21:07:08,274: INFO - + Get:26 https://packages.sury.org/php bullseye/main arm64 php7.4-mbstring arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [386 kB]
2023-03-30 21:07:08,292: INFO - + Get:27 https://packages.sury.org/php bullseye/main arm64 php7.4-ldap arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [27.5 kB]
2023-03-30 21:07:08,295: INFO - + Get:28 https://packages.sury.org/php bullseye/main arm64 php7.4-json arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [18.2 kB]
2023-03-30 21:07:08,298: INFO - + Get:29 https://packages.sury.org/php bullseye/main arm64 php7.4-intl arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [114 kB]
2023-03-30 21:07:08,759: INFO - + Get:30 https://packages.sury.org/php bullseye/main arm64 php7.4-gd arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [26.8 kB]
2023-03-30 21:07:08,763: INFO - + Get:31 https://packages.sury.org/php bullseye/main arm64 php7.4-fpm arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [1,318 kB]
2023-03-30 21:07:09,359: INFO - + Get:32 https://packages.sury.org/php bullseye/main arm64 php7.4-curl arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [29.1 kB]
2023-03-30 21:07:09,362: INFO - + Get:33 https://packages.sury.org/php bullseye/main arm64 php7.4-cli arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [1,304 kB]
2023-03-30 21:07:09,428: INFO - + Get:34 https://packages.sury.org/php bullseye/main arm64 php7.4-common arm64 1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f [624 kB]
2023-03-30 21:07:15,310: INFO - + Get:35 http://deb.debian.org/debian bullseye/main arm64 libtasn1-6 arm64 4.16.0-2+deb11u1 [53.3 kB]
2023-03-30 21:07:15,897: INFO - + Get:36 http://archive.raspberrypi.org/debian bullseye/main arm64 raspberrypi-bootloader arm64 1:1.20230317-1 [4,542 kB]
2023-03-30 21:07:17,098: INFO - + Get:37 http://deb.debian.org/debian bullseye/main arm64 nftables arm64 0.9.8-3.1+deb11u1 [68.4 kB]
2023-03-30 21:07:17,241: INFO - + Get:38 http://archive.raspberrypi.org/debian bullseye/main arm64 libraspberrypi-bin arm64 1:2+git20220616~133208+6e8f786-1 [67.5 kB]
2023-03-30 21:07:17,243: INFO - + Get:39 http://archive.raspberrypi.org/debian bullseye/main arm64 libraspberrypi0 arm64 1:2+git20220616~133208+6e8f786-1 [78.4 kB]
2023-03-30 21:07:17,246: INFO - + Get:40 http://archive.raspberrypi.org/debian bullseye/main arm64 libraspberrypi-doc all 1:2+git20220616~133208+6e8f786-1 [1,988 B]
2023-03-30 21:07:17,247: INFO - + Get:41 http://archive.raspberrypi.org/debian bullseye/main arm64 raspi-config all 20230214 [32.7 kB]
2023-03-30 21:07:17,249: INFO - + Get:42 http://archive.raspberrypi.org/debian bullseye/main arm64 raspinfo all 20230123-1 [2,564 B]
2023-03-30 21:07:17,251: INFO - + Get:43 http://archive.raspberrypi.org/debian bullseye/main arm64 raspi-utils arm64 20230123-1 [41.8 kB]
2023-03-30 21:07:17,252: INFO - + Get:44 http://archive.raspberrypi.org/debian bullseye/main arm64 rpi-eeprom arm64 16.0-1 [2,336 kB]
2023-03-30 21:07:18,683: INFO - + Get:45 http://deb.debian.org/debian bullseye/main arm64 libnftables1 arm64 0.9.8-3.1+deb11u1 [244 kB]
2023-03-30 21:07:21,950: INFO - + Get:46 http://deb.debian.org/debian bullseye/main arm64 mariadb-common all 1:10.5.18-0+deb11u1 [36.9 kB]
2023-03-30 21:07:22,201: INFO - + Get:47 http://deb.debian.org/debian bullseye/main arm64 libmariadb3 arm64 1:10.5.18-0+deb11u1 [167 kB]
2023-03-30 21:07:22,772: INFO - + Get:48 http://forge.yunohost.org/debian bullseye/stable arm64 python3-lexicon all 3.11.2+ynh11-1 [138 kB]
2023-03-30 21:07:22,776: INFO - + Get:49 http://security.debian.org/debian-security bullseye-security/main arm64 git-man all 1:2.30.2-1+deb11u2 [1,828 kB]
2023-03-30 21:07:23,021: INFO - + Get:50 http://deb.debian.org/debian bullseye/main arm64 mariadb-client-core-10.5 arm64 1:10.5.18-0+deb11u1 [762 kB]
2023-03-30 21:07:23,440: INFO - + Get:51 http://forge.yunohost.org/debian bullseye/stable arm64 yunohost all 11.1.15 [1,133 kB]
2023-03-30 21:07:24,852: INFO - + Get:52 http://deb.debian.org/debian bullseye/main arm64 mariadb-client-10.5 arm64 1:10.5.18-0+deb11u1 [1,497 kB]
2023-03-30 21:07:26,474: INFO - + Get:53 http://forge.yunohost.org/debian bullseye/stable arm64 yunohost-admin all 11.1.8 [7,051 kB]
2023-03-30 21:07:28,282: INFO - + Get:54 http://security.debian.org/debian-security bullseye-security/main arm64 libgnutls30 arm64 3.7.1-5+deb11u3 [1,262 kB]
2023-03-30 21:07:30,246: INFO - + Get:55 http://deb.debian.org/debian bullseye/main arm64 mariadb-server-core-10.5 arm64 1:10.5.18-0+deb11u1 [6,336 kB]
2023-03-30 21:07:33,867: INFO - + Get:56 http://security.debian.org/debian-security bullseye-security/main arm64 libcurl3-gnutls arm64 7.74.0-1.3+deb11u7 [321 kB]
2023-03-30 21:07:36,977: INFO - + Get:57 http://security.debian.org/debian-security bullseye-security/main arm64 git arm64 1:2.30.2-1+deb11u2 [5,423 kB]
2023-03-30 21:08:24,595: INFO - + Get:58 http://deb.debian.org/debian bullseye/main arm64 mariadb-server-10.5 arm64 1:10.5.18-0+deb11u1 [4,104 kB]
2023-03-30 21:08:29,467: INFO - + Get:59 http://deb.debian.org/debian bullseye-updates/main arm64 tzdata all 2021a-1+deb11u9 [286 kB]
2023-03-30 21:08:29,753: INFO - + Get:60 http://deb.debian.org/debian bullseye/main arm64 distro-info-data all 0.51+deb11u3 [7,812 B]
2023-03-30 21:08:29,758: INFO - + Get:61 http://deb.debian.org/debian bullseye/main arm64 libabsl20200923 arm64 0~20200923.3-2 [319 kB]
2023-03-30 21:08:30,254: INFO - + Get:62 http://deb.debian.org/debian bullseye/main arm64 libaom0 arm64 1.0.0.errata1-3 [824 kB]
2023-03-30 21:08:31,375: INFO - + Get:63 http://deb.debian.org/debian bullseye/main arm64 libdav1d4 arm64 0.7.1-3 [256 kB]
2023-03-30 21:08:31,705: INFO - + Get:64 http://deb.debian.org/debian bullseye/main arm64 libgav1-0 arm64 0.16.0-5 [369 kB]
2023-03-30 21:08:32,266: INFO - + Get:65 http://deb.debian.org/debian bullseye/main arm64 libavif9 arm64 0.8.4-2+deb11u1 [54.4 kB]
2023-03-30 21:08:32,367: INFO - + Get:66 http://deb.debian.org/debian bullseye/main arm64 libnuma1 arm64 2.0.12-1+b1 [25.8 kB]
2023-03-30 21:08:32,391: INFO - + Get:67 http://deb.debian.org/debian bullseye/main arm64 libx265-192 arm64 3.4-2 [584 kB]
2023-03-30 21:08:33,435: INFO - + Get:68 http://deb.debian.org/debian bullseye/main arm64 libheif1 arm64 1.11.0-1 [173 kB]
2023-03-30 21:08:33,700: INFO - + Get:69 http://deb.debian.org/debian bullseye/main arm64 nano arm64 5.4-2+deb11u2 [647 kB]
2023-03-30 21:08:34,633: INFO - + Get:70 http://deb.debian.org/debian bullseye/main arm64 mariadb-server all 1:10.5.18-0+deb11u1 [35.4 kB]
2023-03-30 21:08:37,718: INFO - + Get:71 http://security.debian.org/debian-security bullseye-security/main arm64 libcurl4 arm64 7.74.0-1.3+deb11u7 [325 kB]
2023-03-30 21:08:39,648: INFO - + Get:72 http://security.debian.org/debian-security bullseye-security/main arm64 curl arm64 7.74.0-1.3+deb11u7 [265 kB]
2023-03-30 21:08:41,134: INFO - + Get:73 http://security.debian.org/debian-security bullseye-security/main arm64 libde265-0 arm64 1.0.11-0+deb11u1 [146 kB]
2023-03-30 21:08:42,193: INFO - + Get:74 http://security.debian.org/debian-security bullseye-security/main arm64 libtiff5 arm64 4.2.0-1+deb11u4 [278 kB]
2023-03-30 21:08:46,166: INFO - + Get:75 http://security.debian.org/debian-security bullseye-security/main arm64 libksba8 arm64 1.5.0-3+deb11u2 [115 kB]
2023-03-30 21:08:47,501: INFO - + Get:76 http://security.debian.org/debian-security bullseye-security/main arm64 libnss3 arm64 2:3.61-1+deb11u3 [1,209 kB]
2023-03-30 21:08:58,396: INFO - + Preconfiguring packages ...
2023-03-30 21:08:59,166: INFO - + Fetched 85.9 MB in 1min 58s (729 kB/s)
2023-03-30 21:08:59,715: DEBUG - (Reading database ... 50238 files and directories currently installed.)
2023-03-30 21:08:59,721: DEBUG - Preparing to unpack .../base-files_11.1+deb11u6_arm64.deb ...
2023-03-30 21:08:59,783: INFO - + Unpacking base-files (11.1+deb11u6) over (11.1+deb11u5) ...
2023-03-30 21:09:00,128: INFO - + Setting up base-files (11.1+deb11u6) ...
2023-03-30 21:09:00,150: DEBUG - Installing new version of config file /etc/debian_version ...
2023-03-30 21:09:00,558: DEBUG - (Reading database ... 50238 files and directories currently installed.)
2023-03-30 21:09:00,565: DEBUG - Preparing to unpack .../moulinette_11.1.4_all.deb ...
2023-03-30 21:09:00,845: INFO - + Unpacking moulinette (11.1.4) over (11.0.9) ...
2023-03-30 21:09:01,150: INFO - + Setting up moulinette (11.1.4) ...
2023-03-30 21:09:01,887: DEBUG - (Reading database ... 50241 files and directories currently installed.)
2023-03-30 21:09:01,894: DEBUG - Preparing to unpack .../archives/ssowat_11.1.4_all.deb ...
2023-03-30 21:09:01,943: INFO - + Unpacking ssowat (11.1.4) over (11.0.9) ...
2023-03-30 21:09:02,294: INFO - + Setting up ssowat (11.1.4) ...
2023-03-30 21:09:02,734: DEBUG - (Reading database ... 50244 files and directories currently installed.)
2023-03-30 21:09:02,740: DEBUG - Preparing to unpack .../python3-lexicon_3.11.2+ynh11-1_all.deb ...
2023-03-30 21:09:03,071: INFO - + Unpacking python3-lexicon (3.11.2+ynh11-1) over (3.7.0+ynh11-1) ...
2023-03-30 21:09:03,344: INFO - + Setting up python3-lexicon (3.11.2+ynh11-1) ...
2023-03-30 21:09:04,430: DEBUG - (Reading database ... 50254 files and directories currently installed.)
2023-03-30 21:09:04,436: DEBUG - Preparing to unpack .../libssl1.1_1.1.1n-0+deb11u4+rpt1_arm64.deb ...
2023-03-30 21:09:04,470: INFO - + Unpacking libssl1.1:arm64 (1.1.1n-0+deb11u4+rpt1) over (1.1.1n-0+deb11u3+rpt1) ...
2023-03-30 21:09:04,826: INFO - + Setting up libssl1.1:arm64 (1.1.1n-0+deb11u4+rpt1) ...
2023-03-30 21:09:05,425: DEBUG - (Reading database ... 50254 files and directories currently installed.)
2023-03-30 21:09:05,431: DEBUG - Preparing to unpack .../libxml2_2.9.14+dfsg-0+0~20220524.12+debian11~1.gbpc5dc45_arm64.deb ...
2023-03-30 21:09:05,453: INFO - + Unpacking libxml2:arm64 (2.9.14+dfsg-0+0~20220524.12+debian11~1.gbpc5dc45) over (2.9.10+dfsg-6.7+deb11u3) ...
2023-03-30 21:09:05,723: INFO - + Setting up libxml2:arm64 (2.9.14+dfsg-0+0~20220524.12+debian11~1.gbpc5dc45) ...
2023-03-30 21:09:05,918: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:05,925: DEBUG - Preparing to unpack .../bind9-libs_1%3a9.16.37-1~deb11u1_arm64.deb ...
2023-03-30 21:09:05,948: INFO - + Unpacking bind9-libs:arm64 (1:9.16.37-1~deb11u1) over (1:9.16.33-1~deb11u1) ...
2023-03-30 21:09:06,474: INFO - + Setting up bind9-libs:arm64 (1:9.16.37-1~deb11u1) ...
2023-03-30 21:09:06,725: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:06,731: DEBUG - Preparing to unpack .../bind9-dnsutils_1%3a9.16.37-1~deb11u1_arm64.deb ...
2023-03-30 21:09:06,789: INFO - + Unpacking bind9-dnsutils (1:9.16.37-1~deb11u1) over (1:9.16.33-1~deb11u1) ...
2023-03-30 21:09:07,094: INFO - + Setting up bind9-dnsutils (1:9.16.37-1~deb11u1) ...
2023-03-30 21:09:07,399: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:07,405: DEBUG - Preparing to unpack .../bind9-host_1%3a9.16.37-1~deb11u1_arm64.deb ...
2023-03-30 21:09:07,463: INFO - + Unpacking bind9-host (1:9.16.37-1~deb11u1) over (1:9.16.33-1~deb11u1) ...
2023-03-30 21:09:07,728: INFO - + Setting up bind9-host (1:9.16.37-1~deb11u1) ...
2023-03-30 21:09:07,997: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:08,003: DEBUG - Preparing to unpack .../openssl_1.1.1n-0+deb11u4+rpt1_arm64.deb ...
2023-03-30 21:09:08,053: INFO - + Unpacking openssl (1.1.1n-0+deb11u4+rpt1) over (1.1.1n-0+deb11u3+rpt1) ...
2023-03-30 21:09:08,475: INFO - + Setting up openssl (1.1.1n-0+deb11u4+rpt1) ...
2023-03-30 21:09:08,697: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:08,703: DEBUG - Preparing to unpack .../sudo-ldap_1.9.5p2-3+deb11u1_arm64.deb ...
2023-03-30 21:09:08,754: INFO - + Unpacking sudo-ldap (1.9.5p2-3+deb11u1) over (1.9.5p2-3) ...
2023-03-30 21:09:09,300: INFO - + Setting up sudo-ldap (1.9.5p2-3+deb11u1) ...
2023-03-30 21:09:10,225: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:10,231: DEBUG - Preparing to unpack .../postfix_3.5.17-0+deb11u1_arm64.deb ...
2023-03-30 21:09:11,326: INFO - + Unpacking postfix (3.5.17-0+deb11u1) over (3.5.13-0+deb11u1) ...
2023-03-30 21:09:11,982: INFO - + Setting up postfix (3.5.17-0+deb11u1) ...
2023-03-30 21:09:13,794: DEBUG - 
2023-03-30 21:09:13,795: WARNING - Postfix (main.cf) configuration was not changed.  If you need to make changes,
2023-03-30 21:09:13,797: WARNING - edit /etc/postfix/main.cf (and others) as needed.  To view Postfix
2023-03-30 21:09:13,798: WARNING - configuration values, see postconf(1).
2023-03-30 21:09:13,800: DEBUG - 
2023-03-30 21:09:13,801: WARNING - After modifying main.cf, be sure to run 'systemctl reload postfix'.
2023-03-30 21:09:13,802: DEBUG - 
2023-03-30 21:09:13,864: WARNING - Warning: The unit file, source configuration file or drop-ins of postfix.service changed on disk. Run 'systemctl daemon-reload' to reload units.
2023-03-30 21:09:17,992: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:17,998: DEBUG - Preparing to unpack .../postfix-pcre_3.5.17-0+deb11u1_arm64.deb ...
2023-03-30 21:09:18,133: INFO - + Removing pcre map entry from /etc/postfix/dynamicmaps.cf
2023-03-30 21:09:18,179: INFO - + Unpacking postfix-pcre (3.5.17-0+deb11u1) over (3.5.13-0+deb11u1) ...
2023-03-30 21:09:18,416: INFO - + Setting up postfix-pcre (3.5.17-0+deb11u1) ...
2023-03-30 21:09:18,829: WARNING - Adding pcre map entry to /etc/postfix/dynamicmaps.cf
2023-03-30 21:09:19,104: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:19,109: DEBUG - Preparing to unpack .../postfix-ldap_3.5.17-0+deb11u1_arm64.deb ...
2023-03-30 21:09:19,233: INFO - + Removing ldap map entry from /etc/postfix/dynamicmaps.cf
2023-03-30 21:09:19,255: INFO - + Unpacking postfix-ldap (3.5.17-0+deb11u1) over (3.5.13-0+deb11u1) ...
2023-03-30 21:09:19,414: INFO - + Setting up postfix-ldap (3.5.17-0+deb11u1) ...
2023-03-30 21:09:19,796: WARNING - Adding ldap map entry to /etc/postfix/dynamicmaps.cf
2023-03-30 21:09:20,010: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:20,015: DEBUG - Preparing to unpack .../libpcre3_2%3a8.44-2+0~20210301.9+debian11~1.gbpa278ad_arm64.deb ...
2023-03-30 21:09:20,038: INFO - + Unpacking libpcre3:arm64 (2:8.44-2+0~20210301.9+debian11~1.gbpa278ad) over (2:8.39-13) ...
2023-03-30 21:09:20,221: INFO - + Setting up libpcre3:arm64 (2:8.44-2+0~20210301.9+debian11~1.gbpa278ad) ...
2023-03-30 21:09:20,409: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:20,414: DEBUG - Preparing to unpack .../git-man_1%3a2.30.2-1+deb11u2_all.deb ...
2023-03-30 21:09:20,436: INFO - + Unpacking git-man (1:2.30.2-1+deb11u2) over (1:2.30.2-1) ...
2023-03-30 21:09:20,746: INFO - + Setting up git-man (1:2.30.2-1+deb11u2) ...
2023-03-30 21:09:20,942: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:20,949: DEBUG - Preparing to unpack .../libtasn1-6_4.16.0-2+deb11u1_arm64.deb ...
2023-03-30 21:09:20,971: INFO - + Unpacking libtasn1-6:arm64 (4.16.0-2+deb11u1) over (4.16.0-2) ...
2023-03-30 21:09:21,244: INFO - + Setting up libtasn1-6:arm64 (4.16.0-2+deb11u1) ...
2023-03-30 21:09:21,535: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:21,541: DEBUG - Preparing to unpack .../libgnutls30_3.7.1-5+deb11u3_arm64.deb ...
2023-03-30 21:09:21,593: INFO - + Unpacking libgnutls30:arm64 (3.7.1-5+deb11u3) over (3.7.1-5+deb11u2) ...
2023-03-30 21:09:21,966: INFO - + Setting up libgnutls30:arm64 (3.7.1-5+deb11u3) ...
2023-03-30 21:09:22,166: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:22,172: DEBUG - Preparing to unpack .../libcurl3-gnutls_7.74.0-1.3+deb11u7_arm64.deb ...
2023-03-30 21:09:22,194: INFO - + Unpacking libcurl3-gnutls:arm64 (7.74.0-1.3+deb11u7) over (7.74.0-1.3+deb11u3) ...
2023-03-30 21:09:22,508: INFO - + Setting up libcurl3-gnutls:arm64 (7.74.0-1.3+deb11u7) ...
2023-03-30 21:09:22,787: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:22,792: DEBUG - Preparing to unpack .../libpcre2-8-0_10.40-1+0~20220713.16+debian11~1.gbpb6cec5_arm64.deb ...
2023-03-30 21:09:22,816: INFO - + Unpacking libpcre2-8-0:arm64 (10.40-1+0~20220713.16+debian11~1.gbpb6cec5) over (10.36-2+deb11u1) ...
2023-03-30 21:09:22,995: INFO - + Setting up libpcre2-8-0:arm64 (10.40-1+0~20220713.16+debian11~1.gbpb6cec5) ...
2023-03-30 21:09:23,198: DEBUG - (Reading database ... 50253 files and directories currently installed.)
2023-03-30 21:09:23,203: DEBUG - Preparing to unpack .../git_1%3a2.30.2-1+deb11u2_arm64.deb ...
2023-03-30 21:09:23,304: INFO - + Unpacking git (1:2.30.2-1+deb11u2) over (1:2.30.2-1) ...
2023-03-30 21:09:25,772: INFO - + Setting up git (1:2.30.2-1+deb11u2) ...
2023-03-30 21:09:26,222: DEBUG - (Reading database ... 50254 files and directories currently installed.)
2023-03-30 21:09:26,228: DEBUG - Preparing to unpack .../libcurl4_7.74.0-1.3+deb11u7_arm64.deb ...
2023-03-30 21:09:26,270: INFO - + Unpacking libcurl4:arm64 (7.74.0-1.3+deb11u7) over (7.74.0-1.3+deb11u3) ...
2023-03-30 21:09:26,454: INFO - + Setting up libcurl4:arm64 (7.74.0-1.3+deb11u7) ...
2023-03-30 21:09:26,641: DEBUG - (Reading database ... 50254 files and directories currently installed.)
2023-03-30 21:09:26,646: DEBUG - Preparing to unpack .../curl_7.74.0-1.3+deb11u7_arm64.deb ...
2023-03-30 21:09:26,668: INFO - + Unpacking curl (7.74.0-1.3+deb11u7) over (7.74.0-1.3+deb11u3) ...
2023-03-30 21:09:26,837: INFO - + Setting up curl (7.74.0-1.3+deb11u7) ...
2023-03-30 21:09:27,038: DEBUG - (Reading database ... 50254 files and directories currently installed.)
2023-03-30 21:09:27,043: DEBUG - Preparing to unpack .../yunohost_11.1.15_all.deb ...
2023-03-30 21:09:27,307: INFO - + Unpacking yunohost (11.1.15) over (11.0.10.2) ...
2023-03-30 21:09:27,758: INFO - + Setting up yunohost (11.1.15) ...
2023-03-30 21:09:27,777: DEBUG - Installing new version of config file /etc/bash_completion.d/yunohost ...
2023-03-30 21:09:27,807: INFO - + Regenerating configuration, this might take a while...
2023-03-30 21:10:06,231: INFO - + Configuration updated for 'ssh'
2023-03-30 21:10:06,329: INFO - + Configuration updated for 'slapd'
2023-03-30 21:10:06,491: INFO - + Configuration updated for 'metronome'
2023-03-30 21:10:06,594: INFO - + Configuration updated for 'nginx'
2023-03-30 21:10:06,694: INFO - + Configuration updated for 'postfix'
2023-03-30 21:10:06,790: INFO - + Configuration updated for 'dovecot'
2023-03-30 21:10:06,883: INFO - + Configuration updated for 'rspamd'
2023-03-30 21:10:07,015: INFO - + Configuration updated for 'dnsmasq'
2023-03-30 21:10:07,143: INFO - + Configuration updated for 'fail2ban'
2023-03-30 21:10:27,280: DEBUG - insserv: warning: current start runlevel(s) (empty) of script `mariadb' overrides LSB defaults (2 3 4 5).
2023-03-30 21:10:27,281: DEBUG - insserv: warning: current stop runlevel(s) (0 1 2 3 4 5 6) of script `mariadb' overrides LSB defaults (0 1 6).
2023-03-30 21:10:28,268: DEBUG - insserv: warning: current start runlevel(s) (empty) of script `mariadb' overrides LSB defaults (2 3 4 5).
2023-03-30 21:10:28,269: DEBUG - insserv: warning: current stop runlevel(s) (0 1 2 3 4 5 6) of script `mariadb' overrides LSB defaults (0 1 6).
2023-03-30 21:10:38,672: INFO - + Launching migrations...
2023-03-30 21:10:39,155: INFO - + Running migration 0025_global_settings_to_configpanel...
2023-03-30 21:10:39,157: INFO - + Migration 0025_global_settings_to_configpanel completed
2023-03-30 21:10:39,197: INFO - + Running migration 0026_new_admins_group...
2023-03-30 21:10:39,199: INFO - + Creating a backup of LDAP database and apps settings prior to the actual migration.
2023-03-30 21:10:39,623: INFO - + Updating aliases for group 'admins'
2023-03-30 21:10:39,648: INFO - + Group 'admins' updated
2023-03-30 21:10:39,804: INFO - + Group 'admins' updated
2023-03-30 21:10:39,826: INFO - + Migration 0026_new_admins_group completed
2023-03-30 21:10:39,973: INFO - + Re-diagnosing server health...
2023-03-30 21:10:41,761: INFO - + Everything looks OK for Base system!
2023-03-30 21:10:45,854: WARNING - Found 1 item(s) that could be improved for Internet connectivity.
2023-03-30 21:11:09,229: WARNING - Found 1 significant issue(s) related to DNS records!
2023-03-30 21:11:13,643: WARNING - Found 1 significant issue(s) related to Ports exposure!
2023-03-30 21:11:15,052: INFO - + Everything looks OK for Web!
2023-03-30 21:11:32,337: WARNING - Found 2 significant issue(s) related to Email!
2023-03-30 21:11:33,527: INFO - + Everything looks OK for Services status check!
2023-03-30 21:11:33,550: INFO - + Everything looks OK for System resources!
2023-03-30 21:11:33,604: INFO - + Everything looks OK for System configurations!
2023-03-30 21:11:33,609: INFO - + Everything looks OK for Applications!
2023-03-30 21:11:33,611: WARNING - To see the issues found, you can go to the Diagnosis section of the webadmin, or run 'yunohost diagnosis show --issues --human-readable' from the command-line.
2023-03-30 21:11:33,876: INFO - + Refreshing app catalog...
2023-03-30 21:11:34,309: INFO - + Updating application catalog...
2023-03-30 21:11:39,328: INFO - + (Will fetch 411 logos, this may take a couple minutes)
2023-03-30 21:12:47,538: INFO - + The application catalog has been updated!
2023-03-30 21:12:47,541: INFO - + Nothing to do. Everything is already up-to-date.
2023-03-30 21:12:47,712: INFO - + (Delaying the restart of yunohost-api, this should automatically happen after the end of this upgrade)
2023-03-30 21:12:48,894: DEBUG - (Reading database ... 50275 files and directories currently installed.)
2023-03-30 21:12:48,899: DEBUG - Preparing to unpack .../nftables_0.9.8-3.1+deb11u1_arm64.deb ...
2023-03-30 21:12:49,177: INFO - + Unpacking nftables (0.9.8-3.1+deb11u1) over (0.9.8-3.1) ...
2023-03-30 21:12:49,391: DEBUG - Preparing to unpack .../libnftables1_0.9.8-3.1+deb11u1_arm64.deb ...
2023-03-30 21:12:49,414: INFO - + Unpacking libnftables1:arm64 (0.9.8-3.1+deb11u1) over (0.9.8-3.1) ...
2023-03-30 21:12:49,575: DEBUG - Preparing to unpack .../mariadb-common_1%3a10.5.18-0+deb11u1_all.deb ...
2023-03-30 21:12:49,603: INFO - + Unpacking mariadb-common (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:12:49,755: INFO - + Setting up mariadb-common (1:10.5.18-0+deb11u1) ...
2023-03-30 21:12:49,977: DEBUG - (Reading database ... 50275 files and directories currently installed.)
2023-03-30 21:12:49,983: DEBUG - Preparing to unpack .../libmariadb3_1%3a10.5.18-0+deb11u1_arm64.deb ...
2023-03-30 21:12:50,007: INFO - + Unpacking libmariadb3:arm64 (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:12:50,180: INFO - + Setting up libmariadb3:arm64 (1:10.5.18-0+deb11u1) ...
2023-03-30 21:12:50,471: DEBUG - (Reading database ... 50275 files and directories currently installed.)
2023-03-30 21:12:50,477: DEBUG - Preparing to unpack .../mariadb-client-core-10.5_1%3a10.5.18-0+deb11u1_arm64.deb ...
2023-03-30 21:12:50,527: INFO - + Unpacking mariadb-client-core-10.5 (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:12:51,205: DEBUG - Preparing to unpack .../mariadb-client-10.5_1%3a10.5.18-0+deb11u1_arm64.deb ...
2023-03-30 21:12:51,259: INFO - + Unpacking mariadb-client-10.5 (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:12:52,566: DEBUG - Preparing to unpack .../mariadb-server-core-10.5_1%3a10.5.18-0+deb11u1_arm64.deb ...
2023-03-30 21:12:52,587: INFO - + Unpacking mariadb-server-core-10.5 (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:12:55,409: DEBUG - Preparing to unpack .../mariadb-server-10.5_1%3a10.5.18-0+deb11u1_arm64.deb ...
2023-03-30 21:12:56,185: WARNING - /var/lib/mysql: found previous version 10.5
2023-03-30 21:12:56,462: INFO - + Unpacking mariadb-server-10.5 (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:13:00,878: DEBUG - Preparing to unpack .../tzdata_2021a-1+deb11u9_all.deb ...
2023-03-30 21:13:00,932: INFO - + Unpacking tzdata (2021a-1+deb11u9) over (2021a-1+deb11u8) ...
2023-03-30 21:13:02,766: INFO - + Setting up tzdata (2021a-1+deb11u9) ...
2023-03-30 21:13:03,147: DEBUG - 
2023-03-30 21:13:03,148: WARNING - Current default time zone: 'Europe/London'
2023-03-30 21:13:03,154: WARNING - Local time is now:      Thu Mar 30 21:13:03 BST 2023.
2023-03-30 21:13:03,156: WARNING - Universal Time is now:  Thu Mar 30 20:13:03 UTC 2023.
2023-03-30 21:13:03,157: WARNING - Run 'dpkg-reconfigure tzdata' if you wish to change it.
2023-03-30 21:13:03,158: DEBUG - 
2023-03-30 21:13:03,486: DEBUG - (Reading database ... 50283 files and directories currently installed.)
2023-03-30 21:13:03,492: DEBUG - Preparing to unpack .../distro-info-data_0.51+deb11u3_all.deb ...
2023-03-30 21:13:03,515: INFO - + Unpacking distro-info-data (0.51+deb11u3) over (0.51+deb11u2) ...
2023-03-30 21:13:03,651: INFO - + Setting up distro-info-data (0.51+deb11u3) ...
2023-03-30 21:13:03,907: DEBUG - Selecting previously unselected package libabsl20200923:arm64.
2023-03-30 21:13:03,973: DEBUG - (Reading database ... 50283 files and directories currently installed.)
2023-03-30 21:13:03,979: DEBUG - Preparing to unpack .../libabsl20200923_0~20200923.3-2_arm64.deb ...
2023-03-30 21:13:03,997: INFO - + Unpacking libabsl20200923:arm64 (0~20200923.3-2) ...
2023-03-30 21:13:04,288: INFO - + Setting up libabsl20200923:arm64 (0~20200923.3-2) ...
2023-03-30 21:13:04,424: DEBUG - Selecting previously unselected package libaom0:arm64.
2023-03-30 21:13:04,490: DEBUG - (Reading database ... 50407 files and directories currently installed.)
2023-03-30 21:13:04,495: DEBUG - Preparing to unpack .../libaom0_1.0.0.errata1-3_arm64.deb ...
2023-03-30 21:13:04,505: INFO - + Unpacking libaom0:arm64 (1.0.0.errata1-3) ...
2023-03-30 21:13:04,799: INFO - + Setting up libaom0:arm64 (1.0.0.errata1-3) ...
2023-03-30 21:13:04,928: DEBUG - Selecting previously unselected package libdav1d4:arm64.
2023-03-30 21:13:04,995: DEBUG - (Reading database ... 50412 files and directories currently installed.)
2023-03-30 21:13:05,001: DEBUG - Preparing to unpack .../libdav1d4_0.7.1-3_arm64.deb ...
2023-03-30 21:13:05,010: INFO - + Unpacking libdav1d4:arm64 (0.7.1-3) ...
2023-03-30 21:13:05,188: INFO - + Setting up libdav1d4:arm64 (0.7.1-3) ...
2023-03-30 21:13:05,320: DEBUG - Selecting previously unselected package libgav1-0:arm64.
2023-03-30 21:13:05,385: DEBUG - (Reading database ... 50418 files and directories currently installed.)
2023-03-30 21:13:05,390: DEBUG - Preparing to unpack .../libgav1-0_0.16.0-5_arm64.deb ...
2023-03-30 21:13:05,400: INFO - + Unpacking libgav1-0:arm64 (0.16.0-5) ...
2023-03-30 21:13:05,599: INFO - + Setting up libgav1-0:arm64 (0.16.0-5) ...
2023-03-30 21:13:05,728: DEBUG - Selecting previously unselected package libavif9:arm64.
2023-03-30 21:13:05,792: DEBUG - (Reading database ... 50422 files and directories currently installed.)
2023-03-30 21:13:05,798: DEBUG - Preparing to unpack .../libavif9_0.8.4-2+deb11u1_arm64.deb ...
2023-03-30 21:13:05,807: INFO - + Unpacking libavif9:arm64 (0.8.4-2+deb11u1) ...
2023-03-30 21:13:05,943: INFO - + Setting up libavif9:arm64 (0.8.4-2+deb11u1) ...
2023-03-30 21:13:06,075: DEBUG - Selecting previously unselected package libde265-0:arm64.
2023-03-30 21:13:06,195: DEBUG - (Reading database ... 50429 files and directories currently installed.)
2023-03-30 21:13:06,202: DEBUG - Preparing to unpack .../libde265-0_1.0.11-0+deb11u1_arm64.deb ...
2023-03-30 21:13:06,211: INFO - + Unpacking libde265-0:arm64 (1.0.11-0+deb11u1) ...
2023-03-30 21:13:06,512: INFO - + Setting up libde265-0:arm64 (1.0.11-0+deb11u1) ...
2023-03-30 21:13:06,736: DEBUG - Selecting previously unselected package libnuma1:arm64.
2023-03-30 21:13:06,802: DEBUG - (Reading database ... 50435 files and directories currently installed.)
2023-03-30 21:13:06,807: DEBUG - Preparing to unpack .../libnuma1_2.0.12-1+b1_arm64.deb ...
2023-03-30 21:13:06,825: INFO - + Unpacking libnuma1:arm64 (2.0.12-1+b1) ...
2023-03-30 21:13:07,033: INFO - + Setting up libnuma1:arm64 (2.0.12-1+b1) ...
2023-03-30 21:13:07,256: DEBUG - Selecting previously unselected package libx265-192:arm64.
2023-03-30 21:13:07,320: DEBUG - (Reading database ... 50442 files and directories currently installed.)
2023-03-30 21:13:07,325: DEBUG - Preparing to unpack .../libx265-192_3.4-2_arm64.deb ...
2023-03-30 21:13:07,343: INFO - + Unpacking libx265-192:arm64 (3.4-2) ...
2023-03-30 21:13:08,109: INFO - + Setting up libx265-192:arm64 (3.4-2) ...
2023-03-30 21:13:08,244: DEBUG - Selecting previously unselected package libheif1:arm64.
2023-03-30 21:13:08,309: DEBUG - (Reading database ... 50447 files and directories currently installed.)
2023-03-30 21:13:08,314: DEBUG - Preparing to unpack .../libheif1_1.11.0-1_arm64.deb ...
2023-03-30 21:13:08,324: INFO - + Unpacking libheif1:arm64 (1.11.0-1) ...
2023-03-30 21:13:08,486: INFO - + Setting up libheif1:arm64 (1.11.0-1) ...
2023-03-30 21:13:08,685: DEBUG - (Reading database ... 50452 files and directories currently installed.)
2023-03-30 21:13:08,691: DEBUG - Preparing to unpack .../libtiff5_4.2.0-1+deb11u4_arm64.deb ...
2023-03-30 21:13:08,715: INFO - + Unpacking libtiff5:arm64 (4.2.0-1+deb11u4) over (4.2.0-1+deb11u1) ...
2023-03-30 21:13:08,891: INFO - + Setting up libtiff5:arm64 (4.2.0-1+deb11u4) ...
2023-03-30 21:13:09,089: DEBUG - (Reading database ... 50452 files and directories currently installed.)
2023-03-30 21:13:09,095: DEBUG - Preparing to unpack .../libgd3_2.3.3-9+0~20230207.13+debian11~1.gbp649015_arm64.deb ...
2023-03-30 21:13:09,118: INFO - + Unpacking libgd3:arm64 (2.3.3-9+0~20230207.13+debian11~1.gbp649015) over (2.3.0-2) ...
2023-03-30 21:13:09,294: INFO - + Setting up libgd3:arm64 (2.3.3-9+0~20230207.13+debian11~1.gbp649015) ...
2023-03-30 21:13:09,636: DEBUG - (Reading database ... 50452 files and directories currently installed.)
2023-03-30 21:13:09,642: DEBUG - Preparing to unpack .../libksba8_1.5.0-3+deb11u2_arm64.deb ...
2023-03-30 21:13:09,701: INFO - + Unpacking libksba8:arm64 (1.5.0-3+deb11u2) over (1.5.0-3+deb11u1) ...
2023-03-30 21:13:09,937: INFO - + Setting up libksba8:arm64 (1.5.0-3+deb11u2) ...
2023-03-30 21:13:10,151: DEBUG - (Reading database ... 50452 files and directories currently installed.)
2023-03-30 21:13:10,156: DEBUG - Preparing to unpack .../linux-libc-dev_1%3a1.20230317-1_arm64.deb ...
2023-03-30 21:13:10,178: INFO - + Unpacking linux-libc-dev:arm64 (1:1.20230317-1) over (1:1.20221104-1) ...
2023-03-30 21:13:11,535: INFO - + Setting up linux-libc-dev:arm64 (1:1.20230317-1) ...
2023-03-30 21:13:11,813: DEBUG - (Reading database ... 50465 files and directories currently installed.)
2023-03-30 21:13:11,818: DEBUG - Preparing to unpack .../00-nano_5.4-2+deb11u2_arm64.deb ...
2023-03-30 21:13:11,867: INFO - + Unpacking nano (5.4-2+deb11u2) over (5.4-2+deb11u1) ...
2023-03-30 21:13:12,157: DEBUG - Preparing to unpack .../01-bluez-firmware_1.2-4+rpt10_all.deb ...
2023-03-30 21:13:12,178: INFO - + Unpacking bluez-firmware (1.2-4+rpt10) over (1.2-4+rpt9) ...
2023-03-30 21:13:12,317: DEBUG - Preparing to unpack .../02-libnss3_2%3a3.61-1+deb11u3_arm64.deb ...
2023-03-30 21:13:12,341: INFO - + Unpacking libnss3:arm64 (2:3.61-1+deb11u3) over (2:3.61-1+deb11u2) ...
2023-03-30 21:13:12,800: DEBUG - Preparing to unpack .../03-libraspberrypi-dev_1%3a2+git20220616~133208+6e8f786-1_arm64.deb ...
2023-03-30 21:13:12,850: INFO - + Unpacking libraspberrypi-dev (1:2+git20220616~133208+6e8f786-1) over (1:2+git20220324~090146+c4fd1b8-1) ...
2023-03-30 21:13:13,181: DEBUG - Preparing to unpack .../04-raspberrypi-kernel_1%3a1.20230317-1_arm64.deb ...
2023-03-30 21:13:13,238: INFO - + Leaving 'diversion of /boot/kernel.img to /usr/share/rpikernelhack/kernel.img by rpikernelhack'
2023-03-30 21:13:13,262: INFO - + Leaving 'diversion of /boot/kernel7.img to /usr/share/rpikernelhack/kernel7.img by rpikernelhack'
2023-03-30 21:13:13,286: INFO - + Leaving 'diversion of /boot/kernel7l.img to /usr/share/rpikernelhack/kernel7l.img by rpikernelhack'
2023-03-30 21:13:13,309: INFO - + Adding 'diversion of /boot/kernel8.img to /usr/share/rpikernelhack/kernel8.img by rpikernelhack'
2023-03-30 21:13:13,753: INFO - + Leaving 'diversion of /boot/bcm2708-rpi-b-plus.dtb to /usr/share/rpikernelhack/bcm2708-rpi-b-plus.dtb by rpikernelhack'
2023-03-30 21:13:13,776: INFO - + Leaving 'diversion of /boot/bcm2708-rpi-b-rev1.dtb to /usr/share/rpikernelhack/bcm2708-rpi-b-rev1.dtb by rpikernelhack'
2023-03-30 21:13:13,800: INFO - + Leaving 'diversion of /boot/bcm2708-rpi-b.dtb to /usr/share/rpikernelhack/bcm2708-rpi-b.dtb by rpikernelhack'
2023-03-30 21:13:13,823: INFO - + Leaving 'diversion of /boot/bcm2708-rpi-cm.dtb to /usr/share/rpikernelhack/bcm2708-rpi-cm.dtb by rpikernelhack'
2023-03-30 21:13:13,847: INFO - + Leaving 'diversion of /boot/bcm2708-rpi-zero-w.dtb to /usr/share/rpikernelhack/bcm2708-rpi-zero-w.dtb by rpikernelhack'
2023-03-30 21:13:13,870: INFO - + Leaving 'diversion of /boot/bcm2708-rpi-zero.dtb to /usr/share/rpikernelhack/bcm2708-rpi-zero.dtb by rpikernelhack'
2023-03-30 21:13:13,894: INFO - + Leaving 'diversion of /boot/bcm2709-rpi-2-b.dtb to /usr/share/rpikernelhack/bcm2709-rpi-2-b.dtb by rpikernelhack'
2023-03-30 21:13:13,917: INFO - + Leaving 'diversion of /boot/bcm2709-rpi-cm2.dtb to /usr/share/rpikernelhack/bcm2709-rpi-cm2.dtb by rpikernelhack'
2023-03-30 21:13:13,941: INFO - + Adding 'diversion of /boot/bcm2710-rpi-2-b.dtb to /usr/share/rpikernelhack/bcm2710-rpi-2-b.dtb by rpikernelhack'
2023-03-30 21:13:13,986: INFO - + Adding 'diversion of /boot/bcm2710-rpi-3-b-plus.dtb to /usr/share/rpikernelhack/bcm2710-rpi-3-b-plus.dtb by rpikernelhack'
2023-03-30 21:13:14,031: INFO - + Adding 'diversion of /boot/bcm2710-rpi-3-b.dtb to /usr/share/rpikernelhack/bcm2710-rpi-3-b.dtb by rpikernelhack'
2023-03-30 21:13:14,076: INFO - + Adding 'diversion of /boot/bcm2710-rpi-cm3.dtb to /usr/share/rpikernelhack/bcm2710-rpi-cm3.dtb by rpikernelhack'
2023-03-30 21:13:14,121: INFO - + Adding 'diversion of /boot/bcm2710-rpi-zero-2-w.dtb to /usr/share/rpikernelhack/bcm2710-rpi-zero-2-w.dtb by rpikernelhack'
2023-03-30 21:13:14,166: INFO - + Adding 'diversion of /boot/bcm2710-rpi-zero-2.dtb to /usr/share/rpikernelhack/bcm2710-rpi-zero-2.dtb by rpikernelhack'
2023-03-30 21:13:14,211: INFO - + Adding 'diversion of /boot/bcm2711-rpi-4-b.dtb to /usr/share/rpikernelhack/bcm2711-rpi-4-b.dtb by rpikernelhack'
2023-03-30 21:13:14,257: INFO - + Adding 'diversion of /boot/bcm2711-rpi-400.dtb to /usr/share/rpikernelhack/bcm2711-rpi-400.dtb by rpikernelhack'
2023-03-30 21:13:14,304: INFO - + Adding 'diversion of /boot/bcm2711-rpi-cm4-io.dtb to /usr/share/rpikernelhack/bcm2711-rpi-cm4-io.dtb by rpikernelhack'
2023-03-30 21:13:14,335: INFO - + Adding 'diversion of /boot/bcm2711-rpi-cm4.dtb to /usr/share/rpikernelhack/bcm2711-rpi-cm4.dtb by rpikernelhack'
2023-03-30 21:13:14,381: INFO - + Adding 'diversion of /boot/bcm2711-rpi-cm4s.dtb to /usr/share/rpikernelhack/bcm2711-rpi-cm4s.dtb by rpikernelhack'
2023-03-30 21:13:14,427: INFO - + Adding 'diversion of /boot/COPYING.linux to /usr/share/rpikernelhack/COPYING.linux by rpikernelhack'
2023-03-30 21:13:14,472: INFO - + Adding 'diversion of /boot/overlays/README to /usr/share/rpikernelhack/overlays/README by rpikernelhack'
2023-03-30 21:13:14,528: INFO - + Adding 'diversion of /boot/overlays/act-led.dtbo to /usr/share/rpikernelhack/overlays/act-led.dtbo by rpikernelhack'
2023-03-30 21:13:14,572: INFO - + Adding 'diversion of /boot/overlays/adafruit-st7735r.dtbo to /usr/share/rpikernelhack/overlays/adafruit-st7735r.dtbo by rpikernelhack'
2023-03-30 21:13:14,616: INFO - + Adding 'diversion of /boot/overlays/adafruit18.dtbo to /usr/share/rpikernelhack/overlays/adafruit18.dtbo by rpikernelhack'
2023-03-30 21:13:14,660: INFO - + Adding 'diversion of /boot/overlays/adau1977-adc.dtbo to /usr/share/rpikernelhack/overlays/adau1977-adc.dtbo by rpikernelhack'
2023-03-30 21:13:14,704: INFO - + Adding 'diversion of /boot/overlays/adau7002-simple.dtbo to /usr/share/rpikernelhack/overlays/adau7002-simple.dtbo by rpikernelhack'
2023-03-30 21:13:14,748: INFO - + Adding 'diversion of /boot/overlays/ads1015.dtbo to /usr/share/rpikernelhack/overlays/ads1015.dtbo by rpikernelhack'
2023-03-30 21:13:14,792: INFO - + Adding 'diversion of /boot/overlays/ads1115.dtbo to /usr/share/rpikernelhack/overlays/ads1115.dtbo by rpikernelhack'
2023-03-30 21:13:14,836: INFO - + Adding 'diversion of /boot/overlays/ads7846.dtbo to /usr/share/rpikernelhack/overlays/ads7846.dtbo by rpikernelhack'
2023-03-30 21:13:14,880: INFO - + Adding 'diversion of /boot/overlays/adv7282m.dtbo to /usr/share/rpikernelhack/overlays/adv7282m.dtbo by rpikernelhack'
2023-03-30 21:13:14,924: INFO - + Adding 'diversion of /boot/overlays/adv728x-m.dtbo to /usr/share/rpikernelhack/overlays/adv728x-m.dtbo by rpikernelhack'
2023-03-30 21:13:14,968: INFO - + Adding 'diversion of /boot/overlays/akkordion-iqdacplus.dtbo to /usr/share/rpikernelhack/overlays/akkordion-iqdacplus.dtbo by rpikernelhack'
2023-03-30 21:13:15,012: INFO - + Adding 'diversion of /boot/overlays/allo-boss-dac-pcm512x-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-boss-dac-pcm512x-audio.dtbo by rpikernelhack'
2023-03-30 21:13:15,056: INFO - + Adding 'diversion of /boot/overlays/allo-boss2-dac-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-boss2-dac-audio.dtbo by rpikernelhack'
2023-03-30 21:13:15,100: INFO - + Adding 'diversion of /boot/overlays/allo-digione.dtbo to /usr/share/rpikernelhack/overlays/allo-digione.dtbo by rpikernelhack'
2023-03-30 21:13:15,144: INFO - + Adding 'diversion of /boot/overlays/allo-katana-dac-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-katana-dac-audio.dtbo by rpikernelhack'
2023-03-30 21:13:15,188: INFO - + Adding 'diversion of /boot/overlays/allo-piano-dac-pcm512x-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-piano-dac-pcm512x-audio.dtbo by rpikernelhack'
2023-03-30 21:13:15,232: INFO - + Adding 'diversion of /boot/overlays/allo-piano-dac-plus-pcm512x-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-piano-dac-plus-pcm512x-audio.dtbo by rpikernelhack'
2023-03-30 21:13:15,276: INFO - + Adding 'diversion of /boot/overlays/anyspi.dtbo to /usr/share/rpikernelhack/overlays/anyspi.dtbo by rpikernelhack'
2023-03-30 21:13:15,320: INFO - + Adding 'diversion of /boot/overlays/apds9960.dtbo to /usr/share/rpikernelhack/overlays/apds9960.dtbo by rpikernelhack'
2023-03-30 21:13:15,366: INFO - + Adding 'diversion of /boot/overlays/applepi-dac.dtbo to /usr/share/rpikernelhack/overlays/applepi-dac.dtbo by rpikernelhack'
2023-03-30 21:13:15,411: INFO - + Adding 'diversion of /boot/overlays/arducam-64mp.dtbo to /usr/share/rpikernelhack/overlays/arducam-64mp.dtbo by rpikernelhack'
2023-03-30 21:13:15,455: INFO - + Adding 'diversion of /boot/overlays/arducam-pivariety.dtbo to /usr/share/rpikernelhack/overlays/arducam-pivariety.dtbo by rpikernelhack'
2023-03-30 21:13:15,499: INFO - + Adding 'diversion of /boot/overlays/at86rf233.dtbo to /usr/share/rpikernelhack/overlays/at86rf233.dtbo by rpikernelhack'
2023-03-30 21:13:15,543: INFO - + Adding 'diversion of /boot/overlays/audioinjector-addons.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-addons.dtbo by rpikernelhack'
2023-03-30 21:13:15,587: INFO - + Adding 'diversion of /boot/overlays/audioinjector-bare-i2s.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-bare-i2s.dtbo by rpikernelhack'
2023-03-30 21:13:15,632: INFO - + Adding 'diversion of /boot/overlays/audioinjector-isolated-soundcard.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-isolated-soundcard.dtbo by rpikernelhack'
2023-03-30 21:13:15,676: INFO - + Adding 'diversion of /boot/overlays/audioinjector-ultra.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-ultra.dtbo by rpikernelhack'
2023-03-30 21:13:15,720: INFO - + Adding 'diversion of /boot/overlays/audioinjector-wm8731-audio.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-wm8731-audio.dtbo by rpikernelhack'
2023-03-30 21:13:15,765: INFO - + Adding 'diversion of /boot/overlays/audiosense-pi.dtbo to /usr/share/rpikernelhack/overlays/audiosense-pi.dtbo by rpikernelhack'
2023-03-30 21:13:15,809: INFO - + Adding 'diversion of /boot/overlays/audremap.dtbo to /usr/share/rpikernelhack/overlays/audremap.dtbo by rpikernelhack'
2023-03-30 21:13:15,853: INFO - + Adding 'diversion of /boot/overlays/balena-fin.dtbo to /usr/share/rpikernelhack/overlays/balena-fin.dtbo by rpikernelhack'
2023-03-30 21:13:15,897: INFO - + Adding 'diversion of /boot/overlays/camera-mux-2port.dtbo to /usr/share/rpikernelhack/overlays/camera-mux-2port.dtbo by rpikernelhack'
2023-03-30 21:13:15,942: INFO - + Adding 'diversion of /boot/overlays/camera-mux-4port.dtbo to /usr/share/rpikernelhack/overlays/camera-mux-4port.dtbo by rpikernelhack'
2023-03-30 21:13:15,988: INFO - + Adding 'diversion of /boot/overlays/cap1106.dtbo to /usr/share/rpikernelhack/overlays/cap1106.dtbo by rpikernelhack'
2023-03-30 21:13:16,033: INFO - + Adding 'diversion of /boot/overlays/chipdip-dac.dtbo to /usr/share/rpikernelhack/overlays/chipdip-dac.dtbo by rpikernelhack'
2023-03-30 21:13:16,077: INFO - + Adding 'diversion of /boot/overlays/cirrus-wm5102.dtbo to /usr/share/rpikernelhack/overlays/cirrus-wm5102.dtbo by rpikernelhack'
2023-03-30 21:13:16,121: INFO - + Adding 'diversion of /boot/overlays/cm-swap-i2c0.dtbo to /usr/share/rpikernelhack/overlays/cm-swap-i2c0.dtbo by rpikernelhack'
2023-03-30 21:13:16,154: INFO - + Adding 'diversion of /boot/overlays/cma.dtbo to /usr/share/rpikernelhack/overlays/cma.dtbo by rpikernelhack'
2023-03-30 21:13:16,198: INFO - + Adding 'diversion of /boot/overlays/crystalfontz-cfa050_pi_m.dtbo to /usr/share/rpikernelhack/overlays/crystalfontz-cfa050_pi_m.dtbo by rpikernelhack'
2023-03-30 21:13:16,230: INFO - + Adding 'diversion of /boot/overlays/cutiepi-panel.dtbo to /usr/share/rpikernelhack/overlays/cutiepi-panel.dtbo by rpikernelhack'
2023-03-30 21:13:16,275: INFO - + Adding 'diversion of /boot/overlays/dacberry400.dtbo to /usr/share/rpikernelhack/overlays/dacberry400.dtbo by rpikernelhack'
2023-03-30 21:13:16,336: INFO - + Adding 'diversion of /boot/overlays/dht11.dtbo to /usr/share/rpikernelhack/overlays/dht11.dtbo by rpikernelhack'
2023-03-30 21:13:16,391: INFO - + Adding 'diversion of /boot/overlays/dionaudio-kiwi.dtbo to /usr/share/rpikernelhack/overlays/dionaudio-kiwi.dtbo by rpikernelhack'
2023-03-30 21:13:16,435: INFO - + Adding 'diversion of /boot/overlays/dionaudio-loco-v2.dtbo to /usr/share/rpikernelhack/overlays/dionaudio-loco-v2.dtbo by rpikernelhack'
2023-03-30 21:13:16,479: INFO - + Adding 'diversion of /boot/overlays/dionaudio-loco.dtbo to /usr/share/rpikernelhack/overlays/dionaudio-loco.dtbo by rpikernelhack'
2023-03-30 21:13:16,523: INFO - + Adding 'diversion of /boot/overlays/disable-bt.dtbo to /usr/share/rpikernelhack/overlays/disable-bt.dtbo by rpikernelhack'
2023-03-30 21:13:16,567: INFO - + Adding 'diversion of /boot/overlays/disable-emmc2.dtbo to /usr/share/rpikernelhack/overlays/disable-emmc2.dtbo by rpikernelhack'
2023-03-30 21:13:16,599: INFO - + Adding 'diversion of /boot/overlays/disable-wifi.dtbo to /usr/share/rpikernelhack/overlays/disable-wifi.dtbo by rpikernelhack'
2023-03-30 21:13:16,644: INFO - + Adding 'diversion of /boot/overlays/dpi18.dtbo to /usr/share/rpikernelhack/overlays/dpi18.dtbo by rpikernelhack'
2023-03-30 21:13:16,687: INFO - + Adding 'diversion of /boot/overlays/dpi18cpadhi.dtbo to /usr/share/rpikernelhack/overlays/dpi18cpadhi.dtbo by rpikernelhack'
2023-03-30 21:13:16,731: INFO - + Adding 'diversion of /boot/overlays/dpi24.dtbo to /usr/share/rpikernelhack/overlays/dpi24.dtbo by rpikernelhack'
2023-03-30 21:13:16,776: INFO - + Adding 'diversion of /boot/overlays/draws.dtbo to /usr/share/rpikernelhack/overlays/draws.dtbo by rpikernelhack'
2023-03-30 21:13:16,820: INFO - + Adding 'diversion of /boot/overlays/dwc-otg.dtbo to /usr/share/rpikernelhack/overlays/dwc-otg.dtbo by rpikernelhack'
2023-03-30 21:13:16,864: INFO - + Adding 'diversion of /boot/overlays/dwc2.dtbo to /usr/share/rpikernelhack/overlays/dwc2.dtbo by rpikernelhack'
2023-03-30 21:13:16,908: INFO - + Adding 'diversion of /boot/overlays/edt-ft5406.dtbo to /usr/share/rpikernelhack/overlays/edt-ft5406.dtbo by rpikernelhack'
2023-03-30 21:13:16,952: INFO - + Adding 'diversion of /boot/overlays/enc28j60-spi2.dtbo to /usr/share/rpikernelhack/overlays/enc28j60-spi2.dtbo by rpikernelhack'
2023-03-30 21:13:16,997: INFO - + Adding 'diversion of /boot/overlays/enc28j60.dtbo to /usr/share/rpikernelhack/overlays/enc28j60.dtbo by rpikernelhack'
2023-03-30 21:13:17,041: INFO - + Adding 'diversion of /boot/overlays/exc3000.dtbo to /usr/share/rpikernelhack/overlays/exc3000.dtbo by rpikernelhack'
2023-03-30 21:13:17,085: INFO - + Adding 'diversion of /boot/overlays/fbtft.dtbo to /usr/share/rpikernelhack/overlays/fbtft.dtbo by rpikernelhack'
2023-03-30 21:13:17,216: INFO - + Adding 'diversion of /boot/overlays/fe-pi-audio.dtbo to /usr/share/rpikernelhack/overlays/fe-pi-audio.dtbo by rpikernelhack'
2023-03-30 21:13:17,295: INFO - + Adding 'diversion of /boot/overlays/fsm-demo.dtbo to /usr/share/rpikernelhack/overlays/fsm-demo.dtbo by rpikernelhack'
2023-03-30 21:13:17,353: INFO - + Adding 'diversion of /boot/overlays/gc9a01.dtbo to /usr/share/rpikernelhack/overlays/gc9a01.dtbo by rpikernelhack'
2023-03-30 21:13:17,410: INFO - + Adding 'diversion of /boot/overlays/ghost-amp.dtbo to /usr/share/rpikernelhack/overlays/ghost-amp.dtbo by rpikernelhack'
2023-03-30 21:13:17,465: INFO - + Adding 'diversion of /boot/overlays/goodix.dtbo to /usr/share/rpikernelhack/overlays/goodix.dtbo by rpikernelhack'
2023-03-30 21:13:17,509: INFO - + Adding 'diversion of /boot/overlays/googlevoicehat-soundcard.dtbo to /usr/share/rpikernelhack/overlays/googlevoicehat-soundcard.dtbo by rpikernelhack'
2023-03-30 21:13:17,554: INFO - + Adding 'diversion of /boot/overlays/gpio-fan.dtbo to /usr/share/rpikernelhack/overlays/gpio-fan.dtbo by rpikernelhack'
2023-03-30 21:13:17,598: INFO - + Adding 'diversion of /boot/overlays/gpio-hog.dtbo to /usr/share/rpikernelhack/overlays/gpio-hog.dtbo by rpikernelhack'
2023-03-30 21:13:17,643: INFO - + Adding 'diversion of /boot/overlays/gpio-ir-tx.dtbo to /usr/share/rpikernelhack/overlays/gpio-ir-tx.dtbo by rpikernelhack'
2023-03-30 21:13:17,687: INFO - + Adding 'diversion of /boot/overlays/gpio-ir.dtbo to /usr/share/rpikernelhack/overlays/gpio-ir.dtbo by rpikernelhack'
2023-03-30 21:13:17,732: INFO - + Adding 'diversion of /boot/overlays/gpio-key.dtbo to /usr/share/rpikernelhack/overlays/gpio-key.dtbo by rpikernelhack'
2023-03-30 21:13:17,776: INFO - + Adding 'diversion of /boot/overlays/gpio-led.dtbo to /usr/share/rpikernelhack/overlays/gpio-led.dtbo by rpikernelhack'
2023-03-30 21:13:17,821: INFO - + Adding 'diversion of /boot/overlays/gpio-no-bank0-irq.dtbo to /usr/share/rpikernelhack/overlays/gpio-no-bank0-irq.dtbo by rpikernelhack'
2023-03-30 21:13:17,865: INFO - + Adding 'diversion of /boot/overlays/gpio-no-irq.dtbo to /usr/share/rpikernelhack/overlays/gpio-no-irq.dtbo by rpikernelhack'
2023-03-30 21:13:17,910: INFO - + Adding 'diversion of /boot/overlays/gpio-poweroff.dtbo to /usr/share/rpikernelhack/overlays/gpio-poweroff.dtbo by rpikernelhack'
2023-03-30 21:13:17,955: INFO - + Adding 'diversion of /boot/overlays/gpio-shutdown.dtbo to /usr/share/rpikernelhack/overlays/gpio-shutdown.dtbo by rpikernelhack'
2023-03-30 21:13:17,999: INFO - + Adding 'diversion of /boot/overlays/hd44780-lcd.dtbo to /usr/share/rpikernelhack/overlays/hd44780-lcd.dtbo by rpikernelhack'
2023-03-30 21:13:18,044: INFO - + Adding 'diversion of /boot/overlays/hdmi-backlight-hwhack-gpio.dtbo to /usr/share/rpikernelhack/overlays/hdmi-backlight-hwhack-gpio.dtbo by rpikernelhack'
2023-03-30 21:13:18,089: INFO - + Adding 'diversion of /boot/overlays/hifiberry-amp.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-amp.dtbo by rpikernelhack'
2023-03-30 21:13:18,133: INFO - + Adding 'diversion of /boot/overlays/hifiberry-amp100.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-amp100.dtbo by rpikernelhack'
2023-03-30 21:13:18,178: INFO - + Adding 'diversion of /boot/overlays/hifiberry-amp3.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-amp3.dtbo by rpikernelhack'
2023-03-30 21:13:18,223: INFO - + Adding 'diversion of /boot/overlays/hifiberry-dac.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dac.dtbo by rpikernelhack'
2023-03-30 21:13:18,441: INFO - + Adding 'diversion of /boot/overlays/hifiberry-dacplus.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplus.dtbo by rpikernelhack'
2023-03-30 21:13:18,488: INFO - + Adding 'diversion of /boot/overlays/hifiberry-dacplusadc.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplusadc.dtbo by rpikernelhack'
2023-03-30 21:13:18,533: INFO - + Adding 'diversion of /boot/overlays/hifiberry-dacplusadcpro.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplusadcpro.dtbo by rpikernelhack'
2023-03-30 21:13:18,578: INFO - + Adding 'diversion of /boot/overlays/hifiberry-dacplusdsp.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplusdsp.dtbo by rpikernelhack'
2023-03-30 21:13:18,623: INFO - + Adding 'diversion of /boot/overlays/hifiberry-dacplushd.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplushd.dtbo by rpikernelhack'
2023-03-30 21:13:18,670: INFO - + Adding 'diversion of /boot/overlays/hifiberry-digi-pro.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-digi-pro.dtbo by rpikernelhack'
2023-03-30 21:13:18,715: INFO - + Adding 'diversion of /boot/overlays/hifiberry-digi.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-digi.dtbo by rpikernelhack'
2023-03-30 21:13:18,760: INFO - + Adding 'diversion of /boot/overlays/highperi.dtbo to /usr/share/rpikernelhack/overlays/highperi.dtbo by rpikernelhack'
2023-03-30 21:13:18,804: INFO - + Adding 'diversion of /boot/overlays/hy28a.dtbo to /usr/share/rpikernelhack/overlays/hy28a.dtbo by rpikernelhack'
2023-03-30 21:13:18,849: INFO - + Adding 'diversion of /boot/overlays/hy28b-2017.dtbo to /usr/share/rpikernelhack/overlays/hy28b-2017.dtbo by rpikernelhack'
2023-03-30 21:13:18,893: INFO - + Adding 'diversion of /boot/overlays/hy28b.dtbo to /usr/share/rpikernelhack/overlays/hy28b.dtbo by rpikernelhack'
2023-03-30 21:13:18,939: INFO - + Adding 'diversion of /boot/overlays/i-sabre-q2m.dtbo to /usr/share/rpikernelhack/overlays/i-sabre-q2m.dtbo by rpikernelhack'
2023-03-30 21:13:18,983: INFO - + Adding 'diversion of /boot/overlays/i2c-bcm2708.dtbo to /usr/share/rpikernelhack/overlays/i2c-bcm2708.dtbo by rpikernelhack'
2023-03-30 21:13:19,028: INFO - + Adding 'diversion of /boot/overlays/i2c-fan.dtbo to /usr/share/rpikernelhack/overlays/i2c-fan.dtbo by rpikernelhack'
2023-03-30 21:13:19,073: INFO - + Adding 'diversion of /boot/overlays/i2c-gpio.dtbo to /usr/share/rpikernelhack/overlays/i2c-gpio.dtbo by rpikernelhack'
2023-03-30 21:13:19,118: INFO - + Adding 'diversion of /boot/overlays/i2c-mux.dtbo to /usr/share/rpikernelhack/overlays/i2c-mux.dtbo by rpikernelhack'
2023-03-30 21:13:19,163: INFO - + Adding 'diversion of /boot/overlays/i2c-pwm-pca9685a.dtbo to /usr/share/rpikernelhack/overlays/i2c-pwm-pca9685a.dtbo by rpikernelhack'
2023-03-30 21:13:19,208: INFO - + Adding 'diversion of /boot/overlays/i2c-rtc-gpio.dtbo to /usr/share/rpikernelhack/overlays/i2c-rtc-gpio.dtbo by rpikernelhack'
2023-03-30 21:13:19,253: INFO - + Adding 'diversion of /boot/overlays/i2c-rtc.dtbo to /usr/share/rpikernelhack/overlays/i2c-rtc.dtbo by rpikernelhack'
2023-03-30 21:13:19,298: INFO - + Adding 'diversion of /boot/overlays/i2c-sensor.dtbo to /usr/share/rpikernelhack/overlays/i2c-sensor.dtbo by rpikernelhack'
2023-03-30 21:13:19,344: INFO - + Adding 'diversion of /boot/overlays/i2c0.dtbo to /usr/share/rpikernelhack/overlays/i2c0.dtbo by rpikernelhack'
2023-03-30 21:13:19,388: INFO - + Adding 'diversion of /boot/overlays/i2c1.dtbo to /usr/share/rpikernelhack/overlays/i2c1.dtbo by rpikernelhack'
2023-03-30 21:13:19,433: INFO - + Adding 'diversion of /boot/overlays/i2c3.dtbo to /usr/share/rpikernelhack/overlays/i2c3.dtbo by rpikernelhack'
2023-03-30 21:13:19,478: INFO - + Adding 'diversion of /boot/overlays/i2c4.dtbo to /usr/share/rpikernelhack/overlays/i2c4.dtbo by rpikernelhack'
2023-03-30 21:13:19,523: INFO - + Adding 'diversion of /boot/overlays/i2c5.dtbo to /usr/share/rpikernelhack/overlays/i2c5.dtbo by rpikernelhack'
2023-03-30 21:13:19,567: INFO - + Adding 'diversion of /boot/overlays/i2c6.dtbo to /usr/share/rpikernelhack/overlays/i2c6.dtbo by rpikernelhack'
2023-03-30 21:13:19,612: INFO - + Adding 'diversion of /boot/overlays/i2s-dac.dtbo to /usr/share/rpikernelhack/overlays/i2s-dac.dtbo by rpikernelhack'
2023-03-30 21:13:19,657: INFO - + Adding 'diversion of /boot/overlays/i2s-gpio28-31.dtbo to /usr/share/rpikernelhack/overlays/i2s-gpio28-31.dtbo by rpikernelhack'
2023-03-30 21:13:19,702: INFO - + Adding 'diversion of /boot/overlays/ilitek251x.dtbo to /usr/share/rpikernelhack/overlays/ilitek251x.dtbo by rpikernelhack'
2023-03-30 21:13:19,746: INFO - + Adding 'diversion of /boot/overlays/imx219.dtbo to /usr/share/rpikernelhack/overlays/imx219.dtbo by rpikernelhack'
2023-03-30 21:13:19,791: INFO - + Adding 'diversion of /boot/overlays/imx258.dtbo to /usr/share/rpikernelhack/overlays/imx258.dtbo by rpikernelhack'
2023-03-30 21:13:19,836: INFO - + Adding 'diversion of /boot/overlays/imx290.dtbo to /usr/share/rpikernelhack/overlays/imx290.dtbo by rpikernelhack'
2023-03-30 21:13:19,881: INFO - + Adding 'diversion of /boot/overlays/imx296.dtbo to /usr/share/rpikernelhack/overlays/imx296.dtbo by rpikernelhack'
2023-03-30 21:13:19,926: INFO - + Adding 'diversion of /boot/overlays/imx327.dtbo to /usr/share/rpikernelhack/overlays/imx327.dtbo by rpikernelhack'
2023-03-30 21:13:19,971: INFO - + Adding 'diversion of /boot/overlays/imx378.dtbo to /usr/share/rpikernelhack/overlays/imx378.dtbo by rpikernelhack'
2023-03-30 21:13:20,016: INFO - + Adding 'diversion of /boot/overlays/imx462.dtbo to /usr/share/rpikernelhack/overlays/imx462.dtbo by rpikernelhack'
2023-03-30 21:13:20,061: INFO - + Adding 'diversion of /boot/overlays/imx477.dtbo to /usr/share/rpikernelhack/overlays/imx477.dtbo by rpikernelhack'
2023-03-30 21:13:20,106: INFO - + Adding 'diversion of /boot/overlays/imx519.dtbo to /usr/share/rpikernelhack/overlays/imx519.dtbo by rpikernelhack'
2023-03-30 21:13:20,152: INFO - + Adding 'diversion of /boot/overlays/imx708.dtbo to /usr/share/rpikernelhack/overlays/imx708.dtbo by rpikernelhack'
2023-03-30 21:13:20,185: INFO - + Adding 'diversion of /boot/overlays/iqaudio-codec.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-codec.dtbo by rpikernelhack'
2023-03-30 21:13:20,230: INFO - + Adding 'diversion of /boot/overlays/iqaudio-dac.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-dac.dtbo by rpikernelhack'
2023-03-30 21:13:20,275: INFO - + Adding 'diversion of /boot/overlays/iqaudio-dacplus.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-dacplus.dtbo by rpikernelhack'
2023-03-30 21:13:20,319: INFO - + Adding 'diversion of /boot/overlays/iqaudio-digi-wm8804-audio.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-digi-wm8804-audio.dtbo by rpikernelhack'
2023-03-30 21:13:20,364: INFO - + Adding 'diversion of /boot/overlays/iqs550.dtbo to /usr/share/rpikernelhack/overlays/iqs550.dtbo by rpikernelhack'
2023-03-30 21:13:20,410: INFO - + Adding 'diversion of /boot/overlays/irs1125.dtbo to /usr/share/rpikernelhack/overlays/irs1125.dtbo by rpikernelhack'
2023-03-30 21:13:20,454: INFO - + Adding 'diversion of /boot/overlays/jedec-spi-nor.dtbo to /usr/share/rpikernelhack/overlays/jedec-spi-nor.dtbo by rpikernelhack'
2023-03-30 21:13:20,499: INFO - + Adding 'diversion of /boot/overlays/justboom-both.dtbo to /usr/share/rpikernelhack/overlays/justboom-both.dtbo by rpikernelhack'
2023-03-30 21:13:20,545: INFO - + Adding 'diversion of /boot/overlays/justboom-dac.dtbo to /usr/share/rpikernelhack/overlays/justboom-dac.dtbo by rpikernelhack'
2023-03-30 21:13:20,589: INFO - + Adding 'diversion of /boot/overlays/justboom-digi.dtbo to /usr/share/rpikernelhack/overlays/justboom-digi.dtbo by rpikernelhack'
2023-03-30 21:13:20,634: INFO - + Adding 'diversion of /boot/overlays/ltc294x.dtbo to /usr/share/rpikernelhack/overlays/ltc294x.dtbo by rpikernelhack'
2023-03-30 21:13:20,679: INFO - + Adding 'diversion of /boot/overlays/max98357a.dtbo to /usr/share/rpikernelhack/overlays/max98357a.dtbo by rpikernelhack'
2023-03-30 21:13:20,724: INFO - + Adding 'diversion of /boot/overlays/maxtherm.dtbo to /usr/share/rpikernelhack/overlays/maxtherm.dtbo by rpikernelhack'
2023-03-30 21:13:20,768: INFO - + Adding 'diversion of /boot/overlays/mbed-dac.dtbo to /usr/share/rpikernelhack/overlays/mbed-dac.dtbo by rpikernelhack'
2023-03-30 21:13:20,813: INFO - + Adding 'diversion of /boot/overlays/mcp23017.dtbo to /usr/share/rpikernelhack/overlays/mcp23017.dtbo by rpikernelhack'
2023-03-30 21:13:20,858: INFO - + Adding 'diversion of /boot/overlays/mcp23s17.dtbo to /usr/share/rpikernelhack/overlays/mcp23s17.dtbo by rpikernelhack'
2023-03-30 21:13:20,904: INFO - + Adding 'diversion of /boot/overlays/mcp2515-can0.dtbo to /usr/share/rpikernelhack/overlays/mcp2515-can0.dtbo by rpikernelhack'
2023-03-30 21:13:20,949: INFO - + Adding 'diversion of /boot/overlays/mcp2515-can1.dtbo to /usr/share/rpikernelhack/overlays/mcp2515-can1.dtbo by rpikernelhack'
2023-03-30 21:13:20,993: INFO - + Adding 'diversion of /boot/overlays/mcp2515.dtbo to /usr/share/rpikernelhack/overlays/mcp2515.dtbo by rpikernelhack'
2023-03-30 21:13:21,038: INFO - + Adding 'diversion of /boot/overlays/mcp251xfd.dtbo to /usr/share/rpikernelhack/overlays/mcp251xfd.dtbo by rpikernelhack'
2023-03-30 21:13:21,083: INFO - + Adding 'diversion of /boot/overlays/mcp3008.dtbo to /usr/share/rpikernelhack/overlays/mcp3008.dtbo by rpikernelhack'
2023-03-30 21:13:21,128: INFO - + Adding 'diversion of /boot/overlays/mcp3202.dtbo to /usr/share/rpikernelhack/overlays/mcp3202.dtbo by rpikernelhack'
2023-03-30 21:13:21,172: INFO - + Adding 'diversion of /boot/overlays/mcp342x.dtbo to /usr/share/rpikernelhack/overlays/mcp342x.dtbo by rpikernelhack'
2023-03-30 21:13:21,217: INFO - + Adding 'diversion of /boot/overlays/media-center.dtbo to /usr/share/rpikernelhack/overlays/media-center.dtbo by rpikernelhack'
2023-03-30 21:13:21,262: INFO - + Adding 'diversion of /boot/overlays/merus-amp.dtbo to /usr/share/rpikernelhack/overlays/merus-amp.dtbo by rpikernelhack'
2023-03-30 21:13:21,307: INFO - + Adding 'diversion of /boot/overlays/midi-uart0.dtbo to /usr/share/rpikernelhack/overlays/midi-uart0.dtbo by rpikernelhack'
2023-03-30 21:13:21,351: INFO - + Adding 'diversion of /boot/overlays/midi-uart1.dtbo to /usr/share/rpikernelhack/overlays/midi-uart1.dtbo by rpikernelhack'
2023-03-30 21:13:21,396: INFO - + Adding 'diversion of /boot/overlays/midi-uart2.dtbo to /usr/share/rpikernelhack/overlays/midi-uart2.dtbo by rpikernelhack'
2023-03-30 21:13:21,445: INFO - + Adding 'diversion of /boot/overlays/midi-uart3.dtbo to /usr/share/rpikernelhack/overlays/midi-uart3.dtbo by rpikernelhack'
2023-03-30 21:13:21,489: INFO - + Adding 'diversion of /boot/overlays/midi-uart4.dtbo to /usr/share/rpikernelhack/overlays/midi-uart4.dtbo by rpikernelhack'
2023-03-30 21:13:21,534: INFO - + Adding 'diversion of /boot/overlays/midi-uart5.dtbo to /usr/share/rpikernelhack/overlays/midi-uart5.dtbo by rpikernelhack'
2023-03-30 21:13:21,579: INFO - + Adding 'diversion of /boot/overlays/minipitft13.dtbo to /usr/share/rpikernelhack/overlays/minipitft13.dtbo by rpikernelhack'
2023-03-30 21:13:21,624: INFO - + Adding 'diversion of /boot/overlays/miniuart-bt.dtbo to /usr/share/rpikernelhack/overlays/miniuart-bt.dtbo by rpikernelhack'
2023-03-30 21:13:21,668: INFO - + Adding 'diversion of /boot/overlays/mipi-dbi-spi.dtbo to /usr/share/rpikernelhack/overlays/mipi-dbi-spi.dtbo by rpikernelhack'
2023-03-30 21:13:21,715: INFO - + Adding 'diversion of /boot/overlays/mlx90640.dtbo to /usr/share/rpikernelhack/overlays/mlx90640.dtbo by rpikernelhack'
2023-03-30 21:13:21,760: INFO - + Adding 'diversion of /boot/overlays/mmc.dtbo to /usr/share/rpikernelhack/overlays/mmc.dtbo by rpikernelhack'
2023-03-30 21:13:21,805: INFO - + Adding 'diversion of /boot/overlays/mpu6050.dtbo to /usr/share/rpikernelhack/overlays/mpu6050.dtbo by rpikernelhack'
2023-03-30 21:13:21,850: INFO - + Adding 'diversion of /boot/overlays/mz61581.dtbo to /usr/share/rpikernelhack/overlays/mz61581.dtbo by rpikernelhack'
2023-03-30 21:13:21,899: INFO - + Adding 'diversion of /boot/overlays/ov2311.dtbo to /usr/share/rpikernelhack/overlays/ov2311.dtbo by rpikernelhack'
2023-03-30 21:13:21,944: INFO - + Adding 'diversion of /boot/overlays/ov5647.dtbo to /usr/share/rpikernelhack/overlays/ov5647.dtbo by rpikernelhack'
2023-03-30 21:13:21,989: INFO - + Adding 'diversion of /boot/overlays/ov7251.dtbo to /usr/share/rpikernelhack/overlays/ov7251.dtbo by rpikernelhack'
2023-03-30 21:13:22,034: INFO - + Adding 'diversion of /boot/overlays/ov9281.dtbo to /usr/share/rpikernelhack/overlays/ov9281.dtbo by rpikernelhack'
2023-03-30 21:13:22,080: INFO - + Adding 'diversion of /boot/overlays/overlay_map.dtb to /usr/share/rpikernelhack/overlays/overlay_map.dtb by rpikernelhack'
2023-03-30 21:13:22,125: INFO - + Adding 'diversion of /boot/overlays/papirus.dtbo to /usr/share/rpikernelhack/overlays/papirus.dtbo by rpikernelhack'
2023-03-30 21:13:22,171: INFO - + Adding 'diversion of /boot/overlays/pca953x.dtbo to /usr/share/rpikernelhack/overlays/pca953x.dtbo by rpikernelhack'
2023-03-30 21:13:22,216: INFO - + Adding 'diversion of /boot/overlays/pcie-32bit-dma.dtbo to /usr/share/rpikernelhack/overlays/pcie-32bit-dma.dtbo by rpikernelhack'
2023-03-30 21:13:22,260: INFO - + Adding 'diversion of /boot/overlays/pibell.dtbo to /usr/share/rpikernelhack/overlays/pibell.dtbo by rpikernelhack'
2023-03-30 21:13:22,305: INFO - + Adding 'diversion of /boot/overlays/pifacedigital.dtbo to /usr/share/rpikernelhack/overlays/pifacedigital.dtbo by rpikernelhack'
2023-03-30 21:13:22,350: INFO - + Adding 'diversion of /boot/overlays/pifi-40.dtbo to /usr/share/rpikernelhack/overlays/pifi-40.dtbo by rpikernelhack'
2023-03-30 21:13:22,395: INFO - + Adding 'diversion of /boot/overlays/pifi-dac-hd.dtbo to /usr/share/rpikernelhack/overlays/pifi-dac-hd.dtbo by rpikernelhack'
2023-03-30 21:13:22,443: INFO - + Adding 'diversion of /boot/overlays/pifi-dac-zero.dtbo to /usr/share/rpikernelhack/overlays/pifi-dac-zero.dtbo by rpikernelhack'
2023-03-30 21:13:22,489: INFO - + Adding 'diversion of /boot/overlays/pifi-mini-210.dtbo to /usr/share/rpikernelhack/overlays/pifi-mini-210.dtbo by rpikernelhack'
2023-03-30 21:13:22,534: INFO - + Adding 'diversion of /boot/overlays/piglow.dtbo to /usr/share/rpikernelhack/overlays/piglow.dtbo by rpikernelhack'
2023-03-30 21:13:22,579: INFO - + Adding 'diversion of /boot/overlays/piscreen.dtbo to /usr/share/rpikernelhack/overlays/piscreen.dtbo by rpikernelhack'
2023-03-30 21:13:22,624: INFO - + Adding 'diversion of /boot/overlays/piscreen2r.dtbo to /usr/share/rpikernelhack/overlays/piscreen2r.dtbo by rpikernelhack'
2023-03-30 21:13:22,669: INFO - + Adding 'diversion of /boot/overlays/pisound.dtbo to /usr/share/rpikernelhack/overlays/pisound.dtbo by rpikernelhack'
2023-03-30 21:13:22,715: INFO - + Adding 'diversion of /boot/overlays/pitft22.dtbo to /usr/share/rpikernelhack/overlays/pitft22.dtbo by rpikernelhack'
2023-03-30 21:13:22,761: INFO - + Adding 'diversion of /boot/overlays/pitft28-capacitive.dtbo to /usr/share/rpikernelhack/overlays/pitft28-capacitive.dtbo by rpikernelhack'
2023-03-30 21:13:22,805: INFO - + Adding 'diversion of /boot/overlays/pitft28-resistive.dtbo to /usr/share/rpikernelhack/overlays/pitft28-resistive.dtbo by rpikernelhack'
2023-03-30 21:13:22,851: INFO - + Adding 'diversion of /boot/overlays/pitft35-resistive.dtbo to /usr/share/rpikernelhack/overlays/pitft35-resistive.dtbo by rpikernelhack'
2023-03-30 21:13:22,896: INFO - + Adding 'diversion of /boot/overlays/pps-gpio.dtbo to /usr/share/rpikernelhack/overlays/pps-gpio.dtbo by rpikernelhack'
2023-03-30 21:13:22,942: INFO - + Adding 'diversion of /boot/overlays/proto-codec.dtbo to /usr/share/rpikernelhack/overlays/proto-codec.dtbo by rpikernelhack'
2023-03-30 21:13:22,987: INFO - + Adding 'diversion of /boot/overlays/pwm-2chan.dtbo to /usr/share/rpikernelhack/overlays/pwm-2chan.dtbo by rpikernelhack'
2023-03-30 21:13:23,032: INFO - + Adding 'diversion of /boot/overlays/pwm-ir-tx.dtbo to /usr/share/rpikernelhack/overlays/pwm-ir-tx.dtbo by rpikernelhack'
2023-03-30 21:13:23,080: INFO - + Adding 'diversion of /boot/overlays/pwm.dtbo to /usr/share/rpikernelhack/overlays/pwm.dtbo by rpikernelhack'
2023-03-30 21:13:23,125: INFO - + Adding 'diversion of /boot/overlays/pwm1.dtbo to /usr/share/rpikernelhack/overlays/pwm1.dtbo by rpikernelhack'
2023-03-30 21:13:23,159: INFO - + Adding 'diversion of /boot/overlays/qca7000-uart0.dtbo to /usr/share/rpikernelhack/overlays/qca7000-uart0.dtbo by rpikernelhack'
2023-03-30 21:13:23,205: INFO - + Adding 'diversion of /boot/overlays/qca7000.dtbo to /usr/share/rpikernelhack/overlays/qca7000.dtbo by rpikernelhack'
2023-03-30 21:13:23,251: INFO - + Adding 'diversion of /boot/overlays/ramoops-pi4.dtbo to /usr/share/rpikernelhack/overlays/ramoops-pi4.dtbo by rpikernelhack'
2023-03-30 21:13:23,296: INFO - + Adding 'diversion of /boot/overlays/ramoops.dtbo to /usr/share/rpikernelhack/overlays/ramoops.dtbo by rpikernelhack'
2023-03-30 21:13:23,341: INFO - + Adding 'diversion of /boot/overlays/rotary-encoder.dtbo to /usr/share/rpikernelhack/overlays/rotary-encoder.dtbo by rpikernelhack'
2023-03-30 21:13:23,403: INFO - + Adding 'diversion of /boot/overlays/rpi-backlight.dtbo to /usr/share/rpikernelhack/overlays/rpi-backlight.dtbo by rpikernelhack'
2023-03-30 21:13:23,448: INFO - + Adding 'diversion of /boot/overlays/rpi-codeczero.dtbo to /usr/share/rpikernelhack/overlays/rpi-codeczero.dtbo by rpikernelhack'
2023-03-30 21:13:23,494: INFO - + Adding 'diversion of /boot/overlays/rpi-dacplus.dtbo to /usr/share/rpikernelhack/overlays/rpi-dacplus.dtbo by rpikernelhack'
2023-03-30 21:13:23,539: INFO - + Adding 'diversion of /boot/overlays/rpi-dacpro.dtbo to /usr/share/rpikernelhack/overlays/rpi-dacpro.dtbo by rpikernelhack'
2023-03-30 21:13:23,584: INFO - + Adding 'diversion of /boot/overlays/rpi-digiampplus.dtbo to /usr/share/rpikernelhack/overlays/rpi-digiampplus.dtbo by rpikernelhack'
2023-03-30 21:13:23,632: INFO - + Adding 'diversion of /boot/overlays/rpi-ft5406.dtbo to /usr/share/rpikernelhack/overlays/rpi-ft5406.dtbo by rpikernelhack'
2023-03-30 21:13:23,677: INFO - + Adding 'diversion of /boot/overlays/rpi-poe-plus.dtbo to /usr/share/rpikernelhack/overlays/rpi-poe-plus.dtbo by rpikernelhack'
2023-03-30 21:13:23,724: INFO - + Adding 'diversion of /boot/overlays/rpi-poe.dtbo to /usr/share/rpikernelhack/overlays/rpi-poe.dtbo by rpikernelhack'
2023-03-30 21:13:23,770: INFO - + Adding 'diversion of /boot/overlays/rpi-sense-v2.dtbo to /usr/share/rpikernelhack/overlays/rpi-sense-v2.dtbo by rpikernelhack'
2023-03-30 21:13:23,815: INFO - + Adding 'diversion of /boot/overlays/rpi-sense.dtbo to /usr/share/rpikernelhack/overlays/rpi-sense.dtbo by rpikernelhack'
2023-03-30 21:13:23,860: INFO - + Adding 'diversion of /boot/overlays/rpi-tv.dtbo to /usr/share/rpikernelhack/overlays/rpi-tv.dtbo by rpikernelhack'
2023-03-30 21:13:23,906: INFO - + Adding 'diversion of /boot/overlays/rra-digidac1-wm8741-audio.dtbo to /usr/share/rpikernelhack/overlays/rra-digidac1-wm8741-audio.dtbo by rpikernelhack'
2023-03-30 21:13:23,952: INFO - + Adding 'diversion of /boot/overlays/sainsmart18.dtbo to /usr/share/rpikernelhack/overlays/sainsmart18.dtbo by rpikernelhack'
2023-03-30 21:13:24,089: INFO - + Adding 'diversion of /boot/overlays/sc16is750-i2c.dtbo to /usr/share/rpikernelhack/overlays/sc16is750-i2c.dtbo by rpikernelhack'
2023-03-30 21:13:24,149: INFO - + Adding 'diversion of /boot/overlays/sc16is752-i2c.dtbo to /usr/share/rpikernelhack/overlays/sc16is752-i2c.dtbo by rpikernelhack'
2023-03-30 21:13:24,206: INFO - + Adding 'diversion of /boot/overlays/sc16is752-spi0.dtbo to /usr/share/rpikernelhack/overlays/sc16is752-spi0.dtbo by rpikernelhack'
2023-03-30 21:13:24,263: INFO - + Adding 'diversion of /boot/overlays/sc16is752-spi1.dtbo to /usr/share/rpikernelhack/overlays/sc16is752-spi1.dtbo by rpikernelhack'
2023-03-30 21:13:24,320: INFO - + Adding 'diversion of /boot/overlays/sdhost.dtbo to /usr/share/rpikernelhack/overlays/sdhost.dtbo by rpikernelhack'
2023-03-30 21:13:24,379: INFO - + Adding 'diversion of /boot/overlays/sdio.dtbo to /usr/share/rpikernelhack/overlays/sdio.dtbo by rpikernelhack'
2023-03-30 21:13:24,438: INFO - + Adding 'diversion of /boot/overlays/seeed-can-fd-hat-v1.dtbo to /usr/share/rpikernelhack/overlays/seeed-can-fd-hat-v1.dtbo by rpikernelhack'
2023-03-30 21:13:24,502: INFO - + Adding 'diversion of /boot/overlays/seeed-can-fd-hat-v2.dtbo to /usr/share/rpikernelhack/overlays/seeed-can-fd-hat-v2.dtbo by rpikernelhack'
2023-03-30 21:13:24,560: INFO - + Adding 'diversion of /boot/overlays/sh1106-spi.dtbo to /usr/share/rpikernelhack/overlays/sh1106-spi.dtbo by rpikernelhack'
2023-03-30 21:13:24,620: INFO - + Adding 'diversion of /boot/overlays/si446x-spi0.dtbo to /usr/share/rpikernelhack/overlays/si446x-spi0.dtbo by rpikernelhack'
2023-03-30 21:13:24,675: INFO - + Adding 'diversion of /boot/overlays/smi-dev.dtbo to /usr/share/rpikernelhack/overlays/smi-dev.dtbo by rpikernelhack'
2023-03-30 21:13:24,730: INFO - + Adding 'diversion of /boot/overlays/smi-nand.dtbo to /usr/share/rpikernelhack/overlays/smi-nand.dtbo by rpikernelhack'
2023-03-30 21:13:24,788: INFO - + Adding 'diversion of /boot/overlays/smi.dtbo to /usr/share/rpikernelhack/overlays/smi.dtbo by rpikernelhack'
2023-03-30 21:13:24,850: INFO - + Adding 'diversion of /boot/overlays/spi-gpio35-39.dtbo to /usr/share/rpikernelhack/overlays/spi-gpio35-39.dtbo by rpikernelhack'
2023-03-30 21:13:24,906: INFO - + Adding 'diversion of /boot/overlays/spi-gpio40-45.dtbo to /usr/share/rpikernelhack/overlays/spi-gpio40-45.dtbo by rpikernelhack'
2023-03-30 21:13:24,962: INFO - + Adding 'diversion of /boot/overlays/spi-rtc.dtbo to /usr/share/rpikernelhack/overlays/spi-rtc.dtbo by rpikernelhack'
2023-03-30 21:13:25,019: INFO - + Adding 'diversion of /boot/overlays/spi0-0cs.dtbo to /usr/share/rpikernelhack/overlays/spi0-0cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,075: INFO - + Adding 'diversion of /boot/overlays/spi0-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi0-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,121: INFO - + Adding 'diversion of /boot/overlays/spi0-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi0-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,165: INFO - + Adding 'diversion of /boot/overlays/spi1-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi1-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,212: INFO - + Adding 'diversion of /boot/overlays/spi1-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi1-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,257: INFO - + Adding 'diversion of /boot/overlays/spi1-3cs.dtbo to /usr/share/rpikernelhack/overlays/spi1-3cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,302: INFO - + Adding 'diversion of /boot/overlays/spi2-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi2-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,347: INFO - + Adding 'diversion of /boot/overlays/spi2-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi2-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,393: INFO - + Adding 'diversion of /boot/overlays/spi2-3cs.dtbo to /usr/share/rpikernelhack/overlays/spi2-3cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,438: INFO - + Adding 'diversion of /boot/overlays/spi3-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi3-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,483: INFO - + Adding 'diversion of /boot/overlays/spi3-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi3-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,529: INFO - + Adding 'diversion of /boot/overlays/spi4-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi4-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,575: INFO - + Adding 'diversion of /boot/overlays/spi4-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi4-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,620: INFO - + Adding 'diversion of /boot/overlays/spi5-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi5-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,666: INFO - + Adding 'diversion of /boot/overlays/spi5-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi5-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,711: INFO - + Adding 'diversion of /boot/overlays/spi6-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi6-1cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,757: INFO - + Adding 'diversion of /boot/overlays/spi6-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi6-2cs.dtbo by rpikernelhack'
2023-03-30 21:13:25,803: INFO - + Adding 'diversion of /boot/overlays/ssd1306-spi.dtbo to /usr/share/rpikernelhack/overlays/ssd1306-spi.dtbo by rpikernelhack'
2023-03-30 21:13:25,848: INFO - + Adding 'diversion of /boot/overlays/ssd1306.dtbo to /usr/share/rpikernelhack/overlays/ssd1306.dtbo by rpikernelhack'
2023-03-30 21:13:25,894: INFO - + Adding 'diversion of /boot/overlays/ssd1331-spi.dtbo to /usr/share/rpikernelhack/overlays/ssd1331-spi.dtbo by rpikernelhack'
2023-03-30 21:13:25,939: INFO - + Adding 'diversion of /boot/overlays/ssd1351-spi.dtbo to /usr/share/rpikernelhack/overlays/ssd1351-spi.dtbo by rpikernelhack'
2023-03-30 21:13:25,985: INFO - + Adding 'diversion of /boot/overlays/superaudioboard.dtbo to /usr/share/rpikernelhack/overlays/superaudioboard.dtbo by rpikernelhack'
2023-03-30 21:13:26,031: INFO - + Adding 'diversion of /boot/overlays/sx150x.dtbo to /usr/share/rpikernelhack/overlays/sx150x.dtbo by rpikernelhack'
2023-03-30 21:13:26,079: INFO - + Adding 'diversion of /boot/overlays/tc358743-audio.dtbo to /usr/share/rpikernelhack/overlays/tc358743-audio.dtbo by rpikernelhack'
2023-03-30 21:13:26,125: INFO - + Adding 'diversion of /boot/overlays/tc358743.dtbo to /usr/share/rpikernelhack/overlays/tc358743.dtbo by rpikernelhack'
2023-03-30 21:13:26,170: INFO - + Adding 'diversion of /boot/overlays/tinylcd35.dtbo to /usr/share/rpikernelhack/overlays/tinylcd35.dtbo by rpikernelhack'
2023-03-30 21:13:26,216: INFO - + Adding 'diversion of /boot/overlays/tpm-slb9670.dtbo to /usr/share/rpikernelhack/overlays/tpm-slb9670.dtbo by rpikernelhack'
2023-03-30 21:13:26,261: INFO - + Adding 'diversion of /boot/overlays/tpm-slb9673.dtbo to /usr/share/rpikernelhack/overlays/tpm-slb9673.dtbo by rpikernelhack'
2023-03-30 21:13:26,296: INFO - + Adding 'diversion of /boot/overlays/uart0.dtbo to /usr/share/rpikernelhack/overlays/uart0.dtbo by rpikernelhack'
2023-03-30 21:13:26,341: INFO - + Adding 'diversion of /boot/overlays/uart1.dtbo to /usr/share/rpikernelhack/overlays/uart1.dtbo by rpikernelhack'
2023-03-30 21:13:26,393: INFO - + Adding 'diversion of /boot/overlays/uart2.dtbo to /usr/share/rpikernelhack/overlays/uart2.dtbo by rpikernelhack'
2023-03-30 21:13:26,457: INFO - + Adding 'diversion of /boot/overlays/uart3.dtbo to /usr/share/rpikernelhack/overlays/uart3.dtbo by rpikernelhack'
2023-03-30 21:13:26,518: INFO - + Adding 'diversion of /boot/overlays/uart4.dtbo to /usr/share/rpikernelhack/overlays/uart4.dtbo by rpikernelhack'
2023-03-30 21:13:26,578: INFO - + Adding 'diversion of /boot/overlays/uart5.dtbo to /usr/share/rpikernelhack/overlays/uart5.dtbo by rpikernelhack'
2023-03-30 21:13:26,637: INFO - + Adding 'diversion of /boot/overlays/udrc.dtbo to /usr/share/rpikernelhack/overlays/udrc.dtbo by rpikernelhack'
2023-03-30 21:13:26,692: INFO - + Adding 'diversion of /boot/overlays/ugreen-dabboard.dtbo to /usr/share/rpikernelhack/overlays/ugreen-dabboard.dtbo by rpikernelhack'
2023-03-30 21:13:26,738: INFO - + Adding 'diversion of /boot/overlays/upstream-pi4.dtbo to /usr/share/rpikernelhack/overlays/upstream-pi4.dtbo by rpikernelhack'
2023-03-30 21:13:26,784: INFO - + Adding 'diversion of /boot/overlays/upstream.dtbo to /usr/share/rpikernelhack/overlays/upstream.dtbo by rpikernelhack'
2023-03-30 21:13:26,829: INFO - + Adding 'diversion of /boot/overlays/vc4-fkms-v3d-pi4.dtbo to /usr/share/rpikernelhack/overlays/vc4-fkms-v3d-pi4.dtbo by rpikernelhack'
2023-03-30 21:13:26,875: INFO - + Adding 'diversion of /boot/overlays/vc4-fkms-v3d.dtbo to /usr/share/rpikernelhack/overlays/vc4-fkms-v3d.dtbo by rpikernelhack'
2023-03-30 21:13:26,921: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dpi-generic.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-generic.dtbo by rpikernelhack'
2023-03-30 21:13:26,971: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dpi-hyperpixel2r.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-hyperpixel2r.dtbo by rpikernelhack'
2023-03-30 21:13:27,018: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dpi-hyperpixel4.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-hyperpixel4.dtbo by rpikernelhack'
2023-03-30 21:13:27,063: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dpi-hyperpixel4sq.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-hyperpixel4sq.dtbo by rpikernelhack'
2023-03-30 21:13:27,110: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dpi-panel.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-panel.dtbo by rpikernelhack'
2023-03-30 21:13:27,156: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dsi-7inch.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dsi-7inch.dtbo by rpikernelhack'
2023-03-30 21:13:27,202: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dsi-lt070me05000-v2.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dsi-lt070me05000-v2.dtbo by rpikernelhack'
2023-03-30 21:13:27,247: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-dsi-lt070me05000.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dsi-lt070me05000.dtbo by rpikernelhack'
2023-03-30 21:13:27,294: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-kippah-7inch.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-kippah-7inch.dtbo by rpikernelhack'
2023-03-30 21:13:27,340: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-v3d-pi4.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-v3d-pi4.dtbo by rpikernelhack'
2023-03-30 21:13:27,385: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-v3d.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-v3d.dtbo by rpikernelhack'
2023-03-30 21:13:27,430: INFO - + Adding 'diversion of /boot/overlays/vc4-kms-vga666.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-vga666.dtbo by rpikernelhack'
2023-03-30 21:13:27,476: INFO - + Adding 'diversion of /boot/overlays/vga666.dtbo to /usr/share/rpikernelhack/overlays/vga666.dtbo by rpikernelhack'
2023-03-30 21:13:27,524: INFO - + Adding 'diversion of /boot/overlays/vl805.dtbo to /usr/share/rpikernelhack/overlays/vl805.dtbo by rpikernelhack'
2023-03-30 21:13:27,576: INFO - + Adding 'diversion of /boot/overlays/w1-gpio-pullup.dtbo to /usr/share/rpikernelhack/overlays/w1-gpio-pullup.dtbo by rpikernelhack'
2023-03-30 21:13:27,629: INFO - + Adding 'diversion of /boot/overlays/w1-gpio.dtbo to /usr/share/rpikernelhack/overlays/w1-gpio.dtbo by rpikernelhack'
2023-03-30 21:13:27,675: INFO - + Adding 'diversion of /boot/overlays/w5500.dtbo to /usr/share/rpikernelhack/overlays/w5500.dtbo by rpikernelhack'
2023-03-30 21:13:27,721: INFO - + Adding 'diversion of /boot/overlays/watterott-display.dtbo to /usr/share/rpikernelhack/overlays/watterott-display.dtbo by rpikernelhack'
2023-03-30 21:13:27,767: INFO - + Adding 'diversion of /boot/overlays/waveshare-can-fd-hat-mode-a.dtbo to /usr/share/rpikernelhack/overlays/waveshare-can-fd-hat-mode-a.dtbo by rpikernelhack'
2023-03-30 21:13:27,813: INFO - + Adding 'diversion of /boot/overlays/waveshare-can-fd-hat-mode-b.dtbo to /usr/share/rpikernelhack/overlays/waveshare-can-fd-hat-mode-b.dtbo by rpikernelhack'
2023-03-30 21:13:27,859: INFO - + Adding 'diversion of /boot/overlays/wittypi.dtbo to /usr/share/rpikernelhack/overlays/wittypi.dtbo by rpikernelhack'
2023-03-30 21:13:27,905: INFO - + Adding 'diversion of /boot/overlays/wm8960-soundcard.dtbo to /usr/share/rpikernelhack/overlays/wm8960-soundcard.dtbo by rpikernelhack'
2023-03-30 21:13:27,931: INFO - + Unpacking raspberrypi-kernel (1:1.20230317-1) over (1:1.20221104-1) ...
2023-03-30 21:13:30,788: WARNING - run-parts: executing /etc/kernel/postrm.d/initramfs-tools 5.15.76+ /boot/kernel.img
2023-03-30 21:13:30,792: WARNING - run-parts: executing /etc/kernel/postrm.d/initramfs-tools 5.15.76-v7+ /boot/kernel7.img
2023-03-30 21:13:30,797: WARNING - run-parts: executing /etc/kernel/postrm.d/initramfs-tools 5.15.76-v7l+ /boot/kernel7l.img
2023-03-30 21:13:30,800: WARNING - run-parts: executing /etc/kernel/postrm.d/initramfs-tools 5.15.76-v8+ /boot/kernel8.img
2023-03-30 21:13:31,482: DEBUG - Preparing to unpack .../05-raspberrypi-bootloader_1%3a1.20230317-1_arm64.deb ...
2023-03-30 21:13:31,569: INFO - + Adding 'diversion of /boot/start.elf to /usr/share/rpikernelhack/start.elf by rpikernelhack'
2023-03-30 21:13:31,809: INFO - + Adding 'diversion of /boot/start_cd.elf to /usr/share/rpikernelhack/start_cd.elf by rpikernelhack'
2023-03-30 21:13:31,924: INFO - + Adding 'diversion of /boot/start_db.elf to /usr/share/rpikernelhack/start_db.elf by rpikernelhack'
2023-03-30 21:13:32,313: INFO - + Adding 'diversion of /boot/start_x.elf to /usr/share/rpikernelhack/start_x.elf by rpikernelhack'
2023-03-30 21:13:32,590: INFO - + Adding 'diversion of /boot/fixup.dat to /usr/share/rpikernelhack/fixup.dat by rpikernelhack'
2023-03-30 21:13:32,649: INFO - + Adding 'diversion of /boot/fixup_cd.dat to /usr/share/rpikernelhack/fixup_cd.dat by rpikernelhack'
2023-03-30 21:13:32,708: INFO - + Adding 'diversion of /boot/fixup_db.dat to /usr/share/rpikernelhack/fixup_db.dat by rpikernelhack'
2023-03-30 21:13:32,767: INFO - + Adding 'diversion of /boot/fixup_x.dat to /usr/share/rpikernelhack/fixup_x.dat by rpikernelhack'
2023-03-30 21:13:32,814: INFO - + Adding 'diversion of /boot/bootcode.bin to /usr/share/rpikernelhack/bootcode.bin by rpikernelhack'
2023-03-30 21:13:32,863: INFO - + Adding 'diversion of /boot/start4.elf to /usr/share/rpikernelhack/start4.elf by rpikernelhack'
2023-03-30 21:13:33,239: INFO - + Adding 'diversion of /boot/start4cd.elf to /usr/share/rpikernelhack/start4cd.elf by rpikernelhack'
2023-03-30 21:13:33,353: INFO - + Adding 'diversion of /boot/start4db.elf to /usr/share/rpikernelhack/start4db.elf by rpikernelhack'
2023-03-30 21:13:33,658: INFO - + Adding 'diversion of /boot/start4x.elf to /usr/share/rpikernelhack/start4x.elf by rpikernelhack'
2023-03-30 21:13:34,003: INFO - + Adding 'diversion of /boot/fixup4.dat to /usr/share/rpikernelhack/fixup4.dat by rpikernelhack'
2023-03-30 21:13:34,052: INFO - + Adding 'diversion of /boot/fixup4cd.dat to /usr/share/rpikernelhack/fixup4cd.dat by rpikernelhack'
2023-03-30 21:13:34,097: INFO - + Adding 'diversion of /boot/fixup4db.dat to /usr/share/rpikernelhack/fixup4db.dat by rpikernelhack'
2023-03-30 21:13:34,143: INFO - + Adding 'diversion of /boot/fixup4x.dat to /usr/share/rpikernelhack/fixup4x.dat by rpikernelhack'
2023-03-30 21:13:34,191: INFO - + Adding 'diversion of /boot/LICENCE.broadcom to /usr/share/rpikernelhack/LICENCE.broadcom by rpikernelhack'
2023-03-30 21:13:34,214: INFO - + Unpacking raspberrypi-bootloader (1:1.20230317-1) over (1:1.20221104-1) ...
2023-03-30 21:13:35,221: DEBUG - Preparing to unpack .../06-libraspberrypi-bin_1%3a2+git20220616~133208+6e8f786-1_arm64.deb ...
2023-03-30 21:13:35,252: INFO - + Unpacking libraspberrypi-bin (1:2+git20220616~133208+6e8f786-1) over (1:2+git20220324~090146+c4fd1b8-1) ...
2023-03-30 21:13:35,380: DEBUG - Preparing to unpack .../07-libraspberrypi0_1%3a2+git20220616~133208+6e8f786-1_arm64.deb ...
2023-03-30 21:13:35,415: INFO - + Unpacking libraspberrypi0:arm64 (1:2+git20220616~133208+6e8f786-1) over (1:2+git20220324~090146+c4fd1b8-1) ...
2023-03-30 21:13:35,608: DEBUG - Preparing to unpack .../08-libraspberrypi-doc_1%3a2+git20220616~133208+6e8f786-1_all.deb ...
2023-03-30 21:13:35,716: INFO - + Unpacking libraspberrypi-doc (1:2+git20220616~133208+6e8f786-1) over (1:2+git20220324~090146+c4fd1b8-1) ...
2023-03-30 21:13:35,802: DEBUG - Preparing to unpack .../09-mariadb-server_1%3a10.5.18-0+deb11u1_all.deb ...
2023-03-30 21:13:35,831: INFO - + Unpacking mariadb-server (1:10.5.18-0+deb11u1) over (1:10.5.15-0+deb11u1) ...
2023-03-30 21:13:35,953: DEBUG - Preparing to unpack .../10-php-common_2%3a93+0~20221211.45+debian11~1.gbpdb4dcc_all.deb ...
2023-03-30 21:13:35,982: INFO - + Unpacking php-common (2:93+0~20221211.45+debian11~1.gbpdb4dcc) over (2:76) ...
2023-03-30 21:13:37,076: DEBUG - Preparing to unpack .../11-php7.4-xml_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:37,759: INFO - + Unpacking php7.4-xml (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:37,909: DEBUG - Preparing to unpack .../12-php7.4-readline_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:38,068: INFO - + Unpacking php7.4-readline (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:38,195: DEBUG - Preparing to unpack .../13-php7.4-opcache_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:38,458: INFO - + Unpacking php7.4-opcache (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:38,712: DEBUG - Preparing to unpack .../14-php7.4-mysql_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:39,610: INFO - + Unpacking php7.4-mysql (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:39,889: DEBUG - Preparing to unpack .../15-php7.4-mbstring_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:40,064: INFO - + Unpacking php7.4-mbstring (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:40,364: DEBUG - Preparing to unpack .../16-php7.4-ldap_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:40,531: INFO - + Unpacking php7.4-ldap (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:40,718: DEBUG - Preparing to unpack .../17-php7.4-json_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:40,858: INFO - + Unpacking php7.4-json (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:40,978: DEBUG - Preparing to unpack .../18-php7.4-intl_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:41,117: INFO - + Unpacking php7.4-intl (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:41,260: DEBUG - Preparing to unpack .../19-php7.4-gd_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:41,399: INFO - + Unpacking php7.4-gd (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:41,524: DEBUG - Preparing to unpack .../20-php7.4-fpm_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:41,572: INFO - + Unpacking php7.4-fpm (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:42,384: DEBUG - Preparing to unpack .../21-php7.4-curl_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:42,547: INFO - + Unpacking php7.4-curl (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:42,667: DEBUG - Preparing to unpack .../22-php7.4-cli_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:42,695: INFO - + Unpacking php7.4-cli (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:43,313: DEBUG - Preparing to unpack .../23-php7.4-common_1%3a7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f_arm64.deb ...
2023-03-30 21:13:45,408: INFO - + Unpacking php7.4-common (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) over (7.4.33-1+deb11u1) ...
2023-03-30 21:13:45,826: DEBUG - Preparing to unpack .../24-raspi-config_20230214_all.deb ...
2023-03-30 21:13:45,854: INFO - + Unpacking raspi-config (20230214) over (20221018) ...
2023-03-30 21:13:45,957: DEBUG - Preparing to unpack .../25-raspinfo_20230123-1_all.deb ...
2023-03-30 21:13:45,980: INFO - + Unpacking raspinfo (20230123-1) over (20190624-1) ...
2023-03-30 21:13:46,059: DEBUG - Selecting previously unselected package raspi-utils.
2023-03-30 21:13:46,069: DEBUG - Preparing to unpack .../26-raspi-utils_20230123-1_arm64.deb ...
2023-03-30 21:13:46,079: INFO - + Unpacking raspi-utils (20230123-1) ...
2023-03-30 21:13:46,179: DEBUG - Preparing to unpack .../27-rpi-eeprom_16.0-1_arm64.deb ...
2023-03-30 21:13:46,206: INFO - + Unpacking rpi-eeprom (16.0-1) over (14.0-1) ...
2023-03-30 21:13:47,617: DEBUG - Preparing to unpack .../28-yunohost-admin_11.1.8_all.deb ...
2023-03-30 21:13:47,669: INFO - + Unpacking yunohost-admin (11.1.8) over (11.0.11) ...
2023-03-30 21:13:48,757: INFO - + Setting up mariadb-server-core-10.5 (1:10.5.18-0+deb11u1) ...
2023-03-30 21:13:48,781: INFO - + Setting up bluez-firmware (1.2-4+rpt10) ...
2023-03-30 21:13:48,801: INFO - + Setting up php-common (2:93+0~20221211.45+debian11~1.gbpdb4dcc) ...
2023-03-30 21:13:50,127: INFO - + Setting up libnftables1:arm64 (0.9.8-3.1+deb11u1) ...
2023-03-30 21:13:50,147: INFO - + Setting up nftables (0.9.8-3.1+deb11u1) ...
2023-03-30 21:13:50,704: INFO - + Setting up php7.4-common (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:04,648: INFO - + Setting up php7.4-curl (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:05,445: INFO - + Setting up php7.4-mysql (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:07,743: INFO - + Setting up php7.4-readline (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:08,744: INFO - + Setting up php7.4-mbstring (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:10,426: INFO - + Setting up libnss3:arm64 (2:3.61-1+deb11u3) ...
2023-03-30 21:14:10,445: INFO - + Setting up yunohost-admin (11.1.8) ...
2023-03-30 21:14:10,489: INFO - + Setting up raspberrypi-kernel (1:1.20230317-1) ...
2023-03-30 21:14:10,561: INFO - + Removing 'diversion of /boot/kernel8.img to /usr/share/rpikernelhack/kernel8.img by rpikernelhack'
2023-03-30 21:14:11,483: INFO - + Removing 'diversion of /boot/bcm2710-rpi-2-b.dtb to /usr/share/rpikernelhack/bcm2710-rpi-2-b.dtb by rpikernelhack'
2023-03-30 21:14:11,548: INFO - + Removing 'diversion of /boot/bcm2710-rpi-3-b-plus.dtb to /usr/share/rpikernelhack/bcm2710-rpi-3-b-plus.dtb by rpikernelhack'
2023-03-30 21:14:11,616: INFO - + Removing 'diversion of /boot/bcm2710-rpi-3-b.dtb to /usr/share/rpikernelhack/bcm2710-rpi-3-b.dtb by rpikernelhack'
2023-03-30 21:14:11,682: INFO - + Removing 'diversion of /boot/bcm2710-rpi-cm3.dtb to /usr/share/rpikernelhack/bcm2710-rpi-cm3.dtb by rpikernelhack'
2023-03-30 21:14:11,748: INFO - + Removing 'diversion of /boot/bcm2710-rpi-zero-2-w.dtb to /usr/share/rpikernelhack/bcm2710-rpi-zero-2-w.dtb by rpikernelhack'
2023-03-30 21:14:11,812: INFO - + Removing 'diversion of /boot/bcm2710-rpi-zero-2.dtb to /usr/share/rpikernelhack/bcm2710-rpi-zero-2.dtb by rpikernelhack'
2023-03-30 21:14:11,878: INFO - + Removing 'diversion of /boot/bcm2711-rpi-4-b.dtb to /usr/share/rpikernelhack/bcm2711-rpi-4-b.dtb by rpikernelhack'
2023-03-30 21:14:11,946: INFO - + Removing 'diversion of /boot/bcm2711-rpi-400.dtb to /usr/share/rpikernelhack/bcm2711-rpi-400.dtb by rpikernelhack'
2023-03-30 21:14:12,012: INFO - + Removing 'diversion of /boot/bcm2711-rpi-cm4-io.dtb to /usr/share/rpikernelhack/bcm2711-rpi-cm4-io.dtb by rpikernelhack'
2023-03-30 21:14:12,078: INFO - + Removing 'diversion of /boot/bcm2711-rpi-cm4.dtb to /usr/share/rpikernelhack/bcm2711-rpi-cm4.dtb by rpikernelhack'
2023-03-30 21:14:12,146: INFO - + Removing 'diversion of /boot/bcm2711-rpi-cm4s.dtb to /usr/share/rpikernelhack/bcm2711-rpi-cm4s.dtb by rpikernelhack'
2023-03-30 21:14:12,212: INFO - + Removing 'diversion of /boot/COPYING.linux to /usr/share/rpikernelhack/COPYING.linux by rpikernelhack'
2023-03-30 21:14:12,277: INFO - + Removing 'diversion of /boot/overlays/README to /usr/share/rpikernelhack/overlays/README by rpikernelhack'
2023-03-30 21:14:12,351: INFO - + Removing 'diversion of /boot/overlays/act-led.dtbo to /usr/share/rpikernelhack/overlays/act-led.dtbo by rpikernelhack'
2023-03-30 21:14:12,420: INFO - + Removing 'diversion of /boot/overlays/adafruit-st7735r.dtbo to /usr/share/rpikernelhack/overlays/adafruit-st7735r.dtbo by rpikernelhack'
2023-03-30 21:14:12,485: INFO - + Removing 'diversion of /boot/overlays/adafruit18.dtbo to /usr/share/rpikernelhack/overlays/adafruit18.dtbo by rpikernelhack'
2023-03-30 21:14:12,552: INFO - + Removing 'diversion of /boot/overlays/adau1977-adc.dtbo to /usr/share/rpikernelhack/overlays/adau1977-adc.dtbo by rpikernelhack'
2023-03-30 21:14:12,621: INFO - + Removing 'diversion of /boot/overlays/adau7002-simple.dtbo to /usr/share/rpikernelhack/overlays/adau7002-simple.dtbo by rpikernelhack'
2023-03-30 21:14:12,692: INFO - + Removing 'diversion of /boot/overlays/ads1015.dtbo to /usr/share/rpikernelhack/overlays/ads1015.dtbo by rpikernelhack'
2023-03-30 21:14:12,760: INFO - + Removing 'diversion of /boot/overlays/ads1115.dtbo to /usr/share/rpikernelhack/overlays/ads1115.dtbo by rpikernelhack'
2023-03-30 21:14:12,828: INFO - + Removing 'diversion of /boot/overlays/ads7846.dtbo to /usr/share/rpikernelhack/overlays/ads7846.dtbo by rpikernelhack'
2023-03-30 21:14:12,896: INFO - + Removing 'diversion of /boot/overlays/adv7282m.dtbo to /usr/share/rpikernelhack/overlays/adv7282m.dtbo by rpikernelhack'
2023-03-30 21:14:12,963: INFO - + Removing 'diversion of /boot/overlays/adv728x-m.dtbo to /usr/share/rpikernelhack/overlays/adv728x-m.dtbo by rpikernelhack'
2023-03-30 21:14:13,031: INFO - + Removing 'diversion of /boot/overlays/akkordion-iqdacplus.dtbo to /usr/share/rpikernelhack/overlays/akko  ssh-keygen -f "/root/.ssh/known_hosts" -R "yunohost.local"
rdion-iqdacplus.dtbo by rpikernelhack'
2023-03-30 21:14:13,099: INFO - + Removing 'diversion of /boot/overlays/allo-boss-dac-pcm512x-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-boss-dac-pcm512x-audio.dtbo by rpikernelhack'
2023-03-30 21:14:13,164: INFO - + Removing 'diversion of /boot/overlays/allo-boss2-dac-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-boss2-dac-audio.dtbo by rpikernelhack'
2023-03-30 21:14:13,231: INFO - + Removing 'diversion of /boot/overlays/allo-digione.dtbo to /usr/share/rpikernelhack/overlays/allo-digione.dtbo by rpikernelhack'
2023-03-30 21:14:13,298: INFO - + Removing 'diversion of /boot/overlays/allo-katana-dac-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-katana-dac-audio.dtbo by rpikernelhack'
2023-03-30 21:14:13,367: INFO - + Removing 'diversion of /boot/overlays/allo-piano-dac-pcm512x-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-piano-dac-pcm512x-audio.dtbo by rpikernelhack'
2023-03-30 21:14:13,437: INFO - + Removing 'diversion of /boot/overlays/allo-piano-dac-plus-pcm512x-audio.dtbo to /usr/share/rpikernelhack/overlays/allo-piano-dac-plus-pcm512x-audio.dtbo by rpikernelhack'
2023-03-30 21:14:13,506: INFO - + Removing 'diversion of /boot/overlays/anyspi.dtbo to /usr/share/rpikernelhack/overlays/anyspi.dtbo by rpikernelhack'
2023-03-30 21:14:13,577: INFO - + Removing 'diversion of /boot/overlays/apds9960.dtbo to /usr/share/rpikernelhack/overlays/apds9960.dtbo by rpikernelhack'
2023-03-30 21:14:13,645: INFO - + Removing 'diversion of /boot/overlays/applepi-dac.dtbo to /usr/share/rpikernelhack/overlays/applepi-dac.dtbo by rpikernelhack'
2023-03-30 21:14:13,713: INFO - + Removing 'diversion of /boot/overlays/arducam-64mp.dtbo to /usr/share/rpikernelhack/overlays/arducam-64mp.dtbo by rpikernelhack'
2023-03-30 21:14:13,781: INFO - + Removing 'diversion of /boot/overlays/arducam-pivariety.dtbo to /usr/share/rpikernelhack/overlays/arducam-pivariety.dtbo by rpikernelhack'
2023-03-30 21:14:13,849: INFO - + Removing 'diversion of /boot/overlays/at86rf233.dtbo to /usr/share/rpikernelhack/overlays/at86rf233.dtbo by rpikernelhack'
2023-03-30 21:14:13,916: INFO - + Removing 'diversion of /boot/overlays/audioinjector-addons.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-addons.dtbo by rpikernelhack'
2023-03-30 21:14:14,013: INFO - + Removing 'diversion of /boot/overlays/audioinjector-bare-i2s.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-bare-i2s.dtbo by rpikernelhack'
2023-03-30 21:14:14,081: INFO - + Removing 'diversion of /boot/overlays/audioinjector-isolated-soundcard.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-isolated-soundcard.dtbo by rpikernelhack'
2023-03-30 21:14:14,147: INFO - + Removing 'diversion of /boot/overlays/audioinjector-ultra.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-ultra.dtbo by rpikernelhack'
2023-03-30 21:14:14,215: INFO - + Removing 'diversion of /boot/overlays/audioinjector-wm8731-audio.dtbo to /usr/share/rpikernelhack/overlays/audioinjector-wm8731-audio.dtbo by rpikernelhack'
2023-03-30 21:14:14,282: INFO - + Removing 'diversion of /boot/overlays/audiosense-pi.dtbo to /usr/share/rpikernelhack/overlays/audiosense-pi.dtbo by rpikernelhack'
2023-03-30 21:14:14,452: INFO - + Removing 'diversion of /boot/overlays/audremap.dtbo to /usr/share/rpikernelhack/overlays/audremap.dtbo by rpikernelhack'
2023-03-30 21:14:14,573: INFO - + Removing 'diversion of /boot/overlays/balena-fin.dtbo to /usr/share/rpikernelhack/overlays/balena-fin.dtbo by rpikernelhack'
2023-03-30 21:14:14,689: INFO - + Removing 'diversion of /boot/overlays/camera-mux-2port.dtbo to /usr/share/rpikernelhack/overlays/camera-mux-2port.dtbo by rpikernelhack'
2023-03-30 21:14:14,822: INFO - + Removing 'diversion of /boot/overlays/camera-mux-4port.dtbo to /usr/share/rpikernelhack/overlays/camera-mux-4port.dtbo by rpikernelhack'
2023-03-30 21:14:14,972: INFO - + Removing 'diversion of /boot/overlays/cap1106.dtbo to /usr/share/rpikernelhack/overlays/cap1106.dtbo by rpikernelhack'
2023-03-30 21:14:15,113: INFO - + Removing 'diversion of /boot/overlays/chipdip-dac.dtbo to /usr/share/rpikernelhack/overlays/chipdip-dac.dtbo by rpikernelhack'
2023-03-30 21:14:15,224: INFO - + Removing 'diversion of /boot/overlays/cirrus-wm5102.dtbo to /usr/share/rpikernelhack/overlays/cirrus-wm5102.dtbo by rpikernelhack'
2023-03-30 21:14:15,339: INFO - + Removing 'diversion of /boot/overlays/cm-swap-i2c0.dtbo to /usr/share/rpikernelhack/overlays/cm-swap-i2c0.dtbo by rpikernelhack'
2023-03-30 21:14:15,459: INFO - + Removing 'diversion of /boot/overlays/cma.dtbo to /usr/share/rpikernelhack/overlays/cma.dtbo by rpikernelhack'
2023-03-30 21:14:15,575: INFO - + Removing 'diversion of /boot/overlays/crystalfontz-cfa050_pi_m.dtbo to /usr/share/rpikernelhack/overlays/crystalfontz-cfa050_pi_m.dtbo by rpikernelhack'
2023-03-30 21:14:15,697: INFO - + Removing 'diversion of /boot/overlays/cutiepi-panel.dtbo to /usr/share/rpikernelhack/overlays/cutiepi-panel.dtbo by rpikernelhack'
2023-03-30 21:14:15,811: INFO - + Removing 'diversion of /boot/overlays/dacberry400.dtbo to /usr/share/rpikernelhack/overlays/dacberry400.dtbo by rpikernelhack'
2023-03-30 21:14:15,876: INFO - + Removing 'diversion of /boot/overlays/dht11.dtbo to /usr/share/rpikernelhack/overlays/dht11.dtbo by rpikernelhack'
2023-03-30 21:14:15,942: INFO - + Removing 'diversion of /boot/overlays/dionaudio-kiwi.dtbo to /usr/share/rpikernelhack/overlays/dionaudio-kiwi.dtbo by rpikernelhack'
2023-03-30 21:14:16,014: INFO - + Removing 'diversion of /boot/overlays/dionaudio-loco-v2.dtbo to /usr/share/rpikernelhack/overlays/dionaudio-loco-v2.dtbo by rpikernelhack'
2023-03-30 21:14:16,082: INFO - + Removing 'diversion of /boot/overlays/dionaudio-loco.dtbo to /usr/share/rpikernelhack/overlays/dionaudio-loco.dtbo by rpikernelhack'
2023-03-30 21:14:16,150: INFO - + Removing 'diversion of /boot/overlays/disable-bt.dtbo to /usr/share/rpikernelhack/overlays/disable-bt.dtbo by rpikernelhack'
2023-03-30 21:14:16,218: INFO - + Removing 'diversion of /boot/overlays/disable-emmc2.dtbo to /usr/share/rpikernelhack/overlays/disable-emmc2.dtbo by rpikernelhack'
2023-03-30 21:14:16,284: INFO - + Removing 'diversion of /boot/overlays/disable-wifi.dtbo to /usr/share/rpikernelhack/overlays/disable-wifi.dtbo by rpikernelhack'
2023-03-30 21:14:16,349: INFO - + Removing 'diversion of /boot/overlays/dpi18.dtbo to /usr/share/rpikernelhack/overlays/dpi18.dtbo by rpikernelhack'
2023-03-30 21:14:16,417: INFO - + Removing 'diversion of /boot/overlays/dpi18cpadhi.dtbo to /usr/share/rpikernelhack/overlays/dpi18cpadhi.dtbo by rpikernelhack'
2023-03-30 21:14:16,483: INFO - + Removing 'diversion of /boot/overlays/dpi24.dtbo to /usr/share/rpikernelhack/overlays/dpi24.dtbo by rpikernelhack'
2023-03-30 21:14:16,548: INFO - + Removing 'diversion of /boot/overlays/draws.dtbo to /usr/share/rpikernelhack/overlays/draws.dtbo by rpikernelhack'
2023-03-30 21:14:16,617: INFO - + Removing 'diversion of /boot/overlays/dwc-otg.dtbo to /usr/share/rpikernelhack/overlays/dwc-otg.dtbo by rpikernelhack'
2023-03-30 21:14:16,687: INFO - + Removing 'diversion of /boot/overlays/dwc2.dtbo to /usr/share/rpikernelhack/overlays/dwc2.dtbo by rpikernelhack'
2023-03-30 21:14:16,752: INFO - + Removing 'diversion of /boot/overlays/edt-ft5406.dtbo to /usr/share/rpikernelhack/overlays/edt-ft5406.dtbo by rpikernelhack'
2023-03-30 21:14:16,819: INFO - + Removing 'diversion of /boot/overlays/enc28j60-spi2.dtbo to /usr/share/rpikernelhack/overlays/enc28j60-spi2.dtbo by rpikernelhack'
2023-03-30 21:14:16,887: INFO - + Removing 'diversion of /boot/overlays/enc28j60.dtbo to /usr/share/rpikernelhack/overlays/enc28j60.dtbo by rpikernelhack'
2023-03-30 21:14:16,954: INFO - + Removing 'diversion of /boot/overlays/exc3000.dtbo to /usr/share/rpikernelhack/overlays/exc3000.dtbo by rpikernelhack'
2023-03-30 21:14:17,022: INFO - + Removing 'diversion of /boot/overlays/fbtft.dtbo to /usr/share/rpikernelhack/overlays/fbtft.dtbo by rpikernelhack'
2023-03-30 21:14:17,092: INFO - + Removing 'diversion of /boot/overlays/fe-pi-audio.dtbo to /usr/share/rpikernelhack/overlays/fe-pi-audio.dtbo by rpikernelhack'
2023-03-30 21:14:17,160: INFO - + Removing 'diversion of /boot/overlays/fsm-demo.dtbo to /usr/share/rpikernelhack/overlays/fsm-demo.dtbo by rpikernelhack'
2023-03-30 21:14:17,225: INFO - + Removing 'diversion of /boot/overlays/gc9a01.dtbo to /usr/share/rpikernelhack/overlays/gc9a01.dtbo by rpikernelhack'
2023-03-30 21:14:17,292: INFO - + Removing 'diversion of /boot/overlays/ghost-amp.dtbo to /usr/share/rpikernelhack/overlays/ghost-amp.dtbo by rpikernelhack'
2023-03-30 21:14:17,365: INFO - + Removing 'diversion of /boot/overlays/goodix.dtbo to /usr/share/rpikernelhack/overlays/goodix.dtbo by rpikernelhack'
2023-03-30 21:14:17,433: INFO - + Removing 'diversion of /boot/overlays/googlevoicehat-soundcard.dtbo to /usr/share/rpikernelhack/overlays/googlevoicehat-soundcard.dtbo by rpikernelhack'
2023-03-30 21:14:17,505: INFO - + Removing 'diversion of /boot/overlays/gpio-fan.dtbo to /usr/share/rpikernelhack/overlays/gpio-fan.dtbo by rpikernelhack'
2023-03-30 21:14:17,572: INFO - + Removing 'diversion of /boot/overlays/gpio-hog.dtbo to /usr/share/rpikernelhack/overlays/gpio-hog.dtbo by rpikernelhack'
2023-03-30 21:14:17,641: INFO - + Removing 'diversion of /boot/overlays/gpio-ir-tx.dtbo to /usr/share/rpikernelhack/overlays/gpio-ir-tx.dtbo by rpikernelhack'
2023-03-30 21:14:17,709: INFO - + Removing 'diversion of /boot/overlays/gpio-ir.dtbo to /usr/share/rpikernelhack/overlays/gpio-ir.dtbo by rpikernelhack'
2023-03-30 21:14:17,777: INFO - + Removing 'diversion of /boot/overlays/gpio-key.dtbo to /usr/share/rpikernelhack/overlays/gpio-key.dtbo by rpikernelhack'
2023-03-30 21:14:17,845: INFO - + Removing 'diversion of /boot/overlays/gpio-led.dtbo to /usr/share/rpikernelhack/overlays/gpio-led.dtbo by rpikernelhack'
2023-03-30 21:14:17,913: INFO - + Removing 'diversion of /boot/overlays/gpio-no-bank0-irq.dtbo to /usr/share/rpikernelhack/overlays/gpio-no-bank0-irq.dtbo by rpikernelhack'
2023-03-30 21:14:17,982: INFO - + Removing 'diversion of /boot/overlays/gpio-no-irq.dtbo to /usr/share/rpikernelhack/overlays/gpio-no-irq.dtbo by rpikernelhack'
2023-03-30 21:14:18,048: INFO - + Removing 'diversion of /boot/overlays/gpio-poweroff.dtbo to /usr/share/rpikernelhack/overlays/gpio-poweroff.dtbo by rpikernelhack'
2023-03-30 21:14:18,119: INFO - + Removing 'diversion of /boot/overlays/gpio-shutdown.dtbo to /usr/share/rpikernelhack/overlays/gpio-shutdown.dtbo by rpikernelhack'
2023-03-30 21:14:18,187: INFO - + Removing 'diversion of /boot/overlays/hd44780-lcd.dtbo to /usr/share/rpikernelhack/overlays/hd44780-lcd.dtbo by rpikernelhack'
2023-03-30 21:14:18,257: INFO - + Removing 'diversion of /boot/overlays/hdmi-backlight-hwhack-gpio.dtbo to /usr/share/rpikernelhack/overlays/hdmi-backlight-hwhack-gpio.dtbo by rpikernelhack'
2023-03-30 21:14:18,323: INFO - + Removing 'diversion of /boot/overlays/hifiberry-amp.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-amp.dtbo by rpikernelhack'
2023-03-30 21:14:18,391: INFO - + Removing 'diversion of /boot/overlays/hifiberry-amp100.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-amp100.dtbo by rpikernelhack'
2023-03-30 21:14:18,462: INFO - + Removing 'diversion of /boot/overlays/hifiberry-amp3.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-amp3.dtbo by rpikernelhack'
2023-03-30 21:14:18,530: INFO - + Removing 'diversion of /boot/overlays/hifiberry-dac.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dac.dtbo by rpikernelhack'
2023-03-30 21:14:18,596: INFO - + Removing 'diversion of /boot/overlays/hifiberry-dacplus.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplus.dtbo by rpikernelhack'
2023-03-30 21:14:18,667: INFO - + Removing 'diversion of /boot/overlays/hifiberry-dacplusadc.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplusadc.dtbo by rpikernelhack'
2023-03-30 21:14:18,737: INFO - + Removing 'diversion of /boot/overlays/hifiberry-dacplusadcpro.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplusadcpro.dtbo by rpikernelhack'
2023-03-30 21:14:18,803: INFO - + Removing 'diversion of /boot/overlays/hifiberry-dacplusdsp.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplusdsp.dtbo by rpikernelhack'
2023-03-30 21:14:18,870: INFO - + Removing 'diversion of /boot/overlays/hifiberry-dacplushd.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-dacplushd.dtbo by rpikernelhack'
2023-03-30 21:14:18,938: INFO - + Removing 'diversion of /boot/overlays/hifiberry-digi-pro.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-digi-pro.dtbo by rpikernelhack'
2023-03-30 21:14:19,007: INFO - + Removing 'diversion of /boot/overlays/hifiberry-digi.dtbo to /usr/share/rpikernelhack/overlays/hifiberry-digi.dtbo by rpikernelhack'
2023-03-30 21:14:19,104: INFO - + Removing 'diversion of /boot/overlays/highperi.dtbo to /usr/share/rpikernelhack/overlays/highperi.dtbo by rpikernelhack'
2023-03-30 21:14:19,216: INFO - + Removing 'diversion of /boot/overlays/hy28a.dtbo to /usr/share/rpikernelhack/overlays/hy28a.dtbo by rpikernelhack'
2023-03-30 21:14:19,303: INFO - + Removing 'diversion of /boot/overlays/hy28b-2017.dtbo to /usr/share/rpikernelhack/overlays/hy28b-2017.dtbo by rpikernelhack'
2023-03-30 21:14:19,374: INFO - + Removing 'diversion of /boot/overlays/hy28b.dtbo to /usr/share/rpikernelhack/overlays/hy28b.dtbo by rpikernelhack'
2023-03-30 21:14:19,443: INFO - + Removing 'diversion of /boot/overlays/i-sabre-q2m.dtbo to /usr/share/rpikernelhack/overlays/i-sabre-q2m.dtbo by rpikernelhack'
2023-03-30 21:14:19,511: INFO - + Removing 'diversion of /boot/overlays/i2c-bcm2708.dtbo to /usr/share/rpikernelhack/overlays/i2c-bcm2708.dtbo by rpikernelhack'
2023-03-30 21:14:19,581: INFO - + Removing 'diversion of /boot/overlays/i2c-fan.dtbo to /usr/share/rpikernelhack/overlays/i2c-fan.dtbo by rpikernelhack'
2023-03-30 21:14:19,650: INFO - + Removing 'diversion of /boot/overlays/i2c-gpio.dtbo to /usr/share/rpikernelhack/overlays/i2c-gpio.dtbo by rpikernelhack'
2023-03-30 21:14:19,718: INFO - + Removing 'diversion of /boot/overlays/i2c-mux.dtbo to /usr/share/rpikernelhack/overlays/i2c-mux.dtbo by rpikernelhack'
2023-03-30 21:14:19,788: INFO - + Removing 'diversion of /boot/overlays/i2c-pwm-pca9685a.dtbo to /usr/share/rpikernelhack/overlays/i2c-pwm-pca9685a.dtbo by rpikernelhack'
2023-03-30 21:14:19,857: INFO - + Removing 'diversion of /boot/overlays/i2c-rtc-gpio.dtbo to /usr/share/rpikernelhack/overlays/i2c-rtc-gpio.dtbo by rpikernelhack'
2023-03-30 21:14:19,926: INFO - + Removing 'diversion of /boot/overlays/i2c-rtc.dtbo to /usr/share/rpikernelhack/overlays/i2c-rtc.dtbo by rpikernelhack'
2023-03-30 21:14:20,118: INFO - + Removing 'diversion of /boot/overlays/i2c-sensor.dtbo to /usr/share/rpikernelhack/overlays/i2c-sensor.dtbo by rpikernelhack'
2023-03-30 21:14:20,233: INFO - + Removing 'diversion of /boot/overlays/i2c0.dtbo to /usr/share/rpikernelhack/overlays/i2c0.dtbo by rpikernelhack'
2023-03-30 21:14:20,356: INFO - + Removing 'diversion of /boot/overlays/i2c1.dtbo to /usr/share/rpikernelhack/overlays/i2c1.dtbo by rpikernelhack'
2023-03-30 21:14:20,434: INFO - + Removing 'diversion of /boot/overlays/i2c3.dtbo to /usr/share/rpikernelhack/overlays/i2c3.dtbo by rpikernelhack'
2023-03-30 21:14:20,502: INFO - + Removing 'diversion of /boot/overlays/i2c4.dtbo to /usr/share/rpikernelhack/overlays/i2c4.dtbo by rpikernelhack'
2023-03-30 21:14:20,570: INFO - + Removing 'diversion of /boot/overlays/i2c5.dtbo to /usr/share/rpikernelhack/overlays/i2c5.dtbo by rpikernelhack'
2023-03-30 21:14:20,636: INFO - + Removing 'diversion of /boot/overlays/i2c6.dtbo to /usr/share/rpikernelhack/overlays/i2c6.dtbo by rpikernelhack'
2023-03-30 21:14:20,706: INFO - + Removing 'diversion of /boot/overlays/i2s-dac.dtbo to /usr/share/rpikernelhack/overlays/i2s-dac.dtbo by rpikernelhack'
2023-03-30 21:14:20,771: INFO - + Removing 'diversion of /boot/overlays/i2s-gpio28-31.dtbo to /usr/share/rpikernelhack/overlays/i2s-gpio28-31.dtbo by rpikernelhack'
2023-03-30 21:14:20,839: INFO - + Removing 'diversion of /boot/overlays/ilitek251x.dtbo to /usr/share/rpikernelhack/overlays/ilitek251x.dtbo by rpikernelhack'
2023-03-30 21:14:20,904: INFO - + Removing 'diversion of /boot/overlays/imx219.dtbo to /usr/share/rpikernelhack/overlays/imx219.dtbo by rpikernelhack'
2023-03-30 21:14:20,971: INFO - + Removing 'diversion of /boot/overlays/imx258.dtbo to /usr/share/rpikernelhack/overlays/imx258.dtbo by rpikernelhack'
2023-03-30 21:14:21,037: INFO - + Removing 'diversion of /boot/overlays/imx290.dtbo to /usr/share/rpikernelhack/overlays/imx290.dtbo by rpikernelhack'
2023-03-30 21:14:21,105: INFO - + Removing 'diversion of /boot/overlays/imx296.dtbo to /usr/share/rpikernelhack/overlays/imx296.dtbo by rpikernelhack'
2023-03-30 21:14:21,170: INFO - + Removing 'diversion of /boot/overlays/imx327.dtbo to /usr/share/rpikernelhack/overlays/imx327.dtbo by rpikernelhack'
2023-03-30 21:14:21,241: INFO - + Removing 'diversion of /boot/overlays/imx378.dtbo to /usr/share/rpikernelhack/overlays/imx378.dtbo by rpikernelhack'
2023-03-30 21:14:21,307: INFO - + Removing 'diversion of /boot/overlays/imx462.dtbo to /usr/share/rpikernelhack/overlays/imx462.dtbo by rpikernelhack'
2023-03-30 21:14:21,375: INFO - + Removing 'diversion of /boot/overlays/imx477.dtbo to /usr/share/rpikernelhack/overlays/imx477.dtbo by rpikernelhack'
2023-03-30 21:14:21,444: INFO - + Removing 'diversion of /boot/overlays/imx519.dtbo to /usr/share/rpikernelhack/overlays/imx519.dtbo by rpikernelhack'
2023-03-30 21:14:21,512: INFO - + Removing 'diversion of /boot/overlays/imx708.dtbo to /usr/share/rpikernelhack/overlays/imx708.dtbo by rpikernelhack'
2023-03-30 21:14:21,580: INFO - + Removing 'diversion of /boot/overlays/iqaudio-codec.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-codec.dtbo by rpikernelhack'
2023-03-30 21:14:21,647: INFO - + Removing 'diversion of /boot/overlays/iqaudio-dac.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-dac.dtbo by rpikernelhack'
2023-03-30 21:14:21,717: INFO - + Removing 'diversion of /boot/overlays/iqaudio-dacplus.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-dacplus.dtbo by rpikernelhack'
2023-03-30 21:14:21,786: INFO - + Removing 'diversion of /boot/overlays/iqaudio-digi-wm8804-audio.dtbo to /usr/share/rpikernelhack/overlays/iqaudio-digi-wm8804-audio.dtbo by rpikernelhack'
2023-03-30 21:14:21,853: INFO - + Removing 'diversion of /boot/overlays/iqs550.dtbo to /usr/share/rpikernelhack/overlays/iqs550.dtbo by rpikernelhack'
2023-03-30 21:14:21,919: INFO - + Removing 'diversion of /boot/overlays/irs1125.dtbo to /usr/share/rpikernelhack/overlays/irs1125.dtbo by rpikernelhack'
2023-03-30 21:14:21,987: INFO - + Removing 'diversion of /boot/overlays/jedec-spi-nor.dtbo to /usr/share/rpikernelhack/overlays/jedec-spi-nor.dtbo by rpikernelhack'
2023-03-30 21:14:22,055: INFO - + Removing 'diversion of /boot/overlays/justboom-both.dtbo to /usr/share/rpikernelhack/overlays/justboom-both.dtbo by rpikernelhack'
2023-03-30 21:14:22,121: INFO - + Removing 'diversion of /boot/overlays/justboom-dac.dtbo to /usr/share/rpikernelhack/overlays/justboom-dac.dtbo by rpikernelhack'
2023-03-30 21:14:22,189: INFO - + Removing 'diversion of /boot/overlays/justboom-digi.dtbo to /usr/share/rpikernelhack/overlays/justboom-digi.dtbo by rpikernelhack'
2023-03-30 21:14:22,255: INFO - + Removing 'diversion of /boot/overlays/ltc294x.dtbo to /usr/share/rpikernelhack/overlays/ltc294x.dtbo by rpikernelhack'
2023-03-30 21:14:22,323: INFO - + Removing 'diversion of /boot/overlays/max98357a.dtbo to /usr/share/rpikernelhack/overlays/max98357a.dtbo by rpikernelhack'
2023-03-30 21:14:22,390: INFO - + Removing 'diversion of /boot/overlays/maxtherm.dtbo to /usr/share/rpikernelhack/overlays/maxtherm.dtbo by rpikernelhack'
2023-03-30 21:14:22,694: INFO - + Removing 'diversion of /boot/overlays/mbed-dac.dtbo to /usr/share/rpikernelhack/overlays/mbed-dac.dtbo by rpikernelhack'
2023-03-30 21:14:22,811: INFO - + Removing 'diversion of /boot/overlays/mcp23017.dtbo to /usr/share/rpikernelhack/overlays/mcp23017.dtbo by rpikernelhack'
2023-03-30 21:14:22,929: INFO - + Removing 'diversion of /boot/overlays/mcp23s17.dtbo to /usr/share/rpikernelhack/overlays/mcp23s17.dtbo by rpikernelhack'
2023-03-30 21:14:22,996: INFO - + Removing 'diversion of /boot/overlays/mcp2515-can0.dtbo to /usr/share/rpikernelhack/overlays/mcp2515-can0.dtbo by rpikernelhack'
2023-03-30 21:14:23,063: INFO - + Removing 'diversion of /boot/overlays/mcp2515-can1.dtbo to /usr/share/rpikernelhack/overlays/mcp2515-can1.dtbo by rpikernelhack'
2023-03-30 21:14:23,129: INFO - + Removing 'diversion of /boot/overlays/mcp2515.dtbo to /usr/share/rpikernelhack/overlays/mcp2515.dtbo by rpikernelhack'
2023-03-30 21:14:23,194: INFO - + Removing 'diversion of /boot/overlays/mcp251xfd.dtbo to /usr/share/rpikernelhack/overlays/mcp251xfd.dtbo by rpikernelhack'
2023-03-30 21:14:23,264: INFO - + Removing 'diversion of /boot/overlays/mcp3008.dtbo to /usr/share/rpikernelhack/overlays/mcp3008.dtbo by rpikernelhack'
2023-03-30 21:14:23,333: INFO - + Removing 'diversion of /boot/overlays/mcp3202.dtbo to /usr/share/rpikernelhack/overlays/mcp3202.dtbo by rpikernelhack'
2023-03-30 21:14:23,405: INFO - + Removing 'diversion of /boot/overlays/mcp342x.dtbo to /usr/share/rpikernelhack/overlays/mcp342x.dtbo by rpikernelhack'
2023-03-30 21:14:23,474: INFO - + Removing 'diversion of /boot/overlays/media-center.dtbo to /usr/share/rpikernelhack/overlays/media-center.dtbo by rpikernelhack'
2023-03-30 21:14:23,541: INFO - + Removing 'diversion of /boot/overlays/merus-amp.dtbo to /usr/share/rpikernelhack/overlays/merus-amp.dtbo by rpikernelhack'
2023-03-30 21:14:23,608: INFO - + Removing 'diversion of /boot/overlays/midi-uart0.dtbo to /usr/share/rpikernelhack/overlays/midi-uart0.dtbo by rpikernelhack'
2023-03-30 21:14:23,677: INFO - + Removing 'diversion of /boot/overlays/midi-uart1.dtbo to /usr/share/rpikernelhack/overlays/midi-uart1.dtbo by rpikernelhack'
2023-03-30 21:14:23,745: INFO - + Removing 'diversion of /boot/overlays/midi-uart2.dtbo to /usr/share/rpikernelhack/overlays/midi-uart2.dtbo by rpikernelhack'
2023-03-30 21:14:23,813: INFO - + Removing 'diversion of /boot/overlays/midi-uart3.dtbo to /usr/share/rpikernelhack/overlays/midi-uart3.dtbo by rpikernelhack'
2023-03-30 21:14:23,879: INFO - + Removing 'diversion of /boot/overlays/midi-uart4.dtbo to /usr/share/rpikernelhack/overlays/midi-uart4.dtbo by rpikernelhack'
2023-03-30 21:14:23,947: INFO - + Removing 'diversion of /boot/overlays/midi-uart5.dtbo to /usr/share/rpikernelhack/overlays/midi-uart5.dtbo by rpikernelhack'
2023-03-30 21:14:24,016: INFO - + Removing 'diversion of /boot/overlays/minipitft13.dtbo to /usr/share/rpikernelhack/overlays/minipitft13.dtbo by rpikernelhack'
2023-03-30 21:14:24,085: INFO - + Removing 'diversion of /boot/overlays/miniuart-bt.dtbo to /usr/share/rpikernelhack/overlays/miniuart-bt.dtbo by rpikernelhack'
2023-03-30 21:14:24,153: INFO - + Removing 'diversion of /boot/overlays/mipi-dbi-spi.dtbo to /usr/share/rpikernelhack/overlays/mipi-dbi-spi.dtbo by rpikernelhack'
2023-03-30 21:14:24,221: INFO - + Removing 'diversion of /boot/overlays/mlx90640.dtbo to /usr/share/rpikernelhack/overlays/mlx90640.dtbo by rpikernelhack'
2023-03-30 21:14:24,290: INFO - + Removing 'diversion of /boot/overlays/mmc.dtbo to /usr/share/rpikernelhack/overlays/mmc.dtbo by rpikernelhack'
2023-03-30 21:14:24,388: INFO - + Removing 'diversion of /boot/overlays/mpu6050.dtbo to /usr/share/rpikernelhack/overlays/mpu6050.dtbo by rpikernelhack'
2023-03-30 21:14:24,465: INFO - + Removing 'diversion of /boot/overlays/mz61581.dtbo to /usr/share/rpikernelhack/overlays/mz61581.dtbo by rpikernelhack'
2023-03-30 21:14:24,530: INFO - + Removing 'diversion of /boot/overlays/ov2311.dtbo to /usr/share/rpikernelhack/overlays/ov2311.dtbo by rpikernelhack'
2023-03-30 21:14:24,597: INFO - + Removing 'diversion of /boot/overlays/ov5647.dtbo to /usr/share/rpikernelhack/overlays/ov5647.dtbo by rpikernelhack'
2023-03-30 21:14:24,665: INFO - + Removing 'diversion of /boot/overlays/ov7251.dtbo to /usr/share/rpikernelhack/overlays/ov7251.dtbo by rpikernelhack'
2023-03-30 21:14:24,732: INFO - + Removing 'diversion of /boot/overlays/ov9281.dtbo to /usr/share/rpikernelhack/overlays/ov9281.dtbo by rpikernelhack'
2023-03-30 21:14:24,801: INFO - + Removing 'diversion of /boot/overlays/overlay_map.dtb to /usr/share/rpikernelhack/overlays/overlay_map.dtb by rpikernelhack'
2023-03-30 21:14:24,872: INFO - + Removing 'diversion of /boot/overlays/papirus.dtbo to /usr/share/rpikernelhack/overlays/papirus.dtbo by rpikernelhack'
2023-03-30 21:14:24,939: INFO - + Removing 'diversion of /boot/overlays/pca953x.dtbo to /usr/share/rpikernelhack/overlays/pca953x.dtbo by rpikernelhack'
2023-03-30 21:14:25,005: INFO - + Removing 'diversion of /boot/overlays/pcie-32bit-dma.dtbo to /usr/share/rpikernelhack/overlays/pcie-32bit-dma.dtbo by rpikernelhack'
2023-03-30 21:14:25,073: INFO - + Removing 'diversion of /boot/overlays/pibell.dtbo to /usr/share/rpikernelhack/overlays/pibell.dtbo by rpikernelhack'
2023-03-30 21:14:25,143: INFO - + Removing 'diversion of /boot/overlays/pifacedigital.dtbo to /usr/share/rpikernelhack/overlays/pifacedigital.dtbo by rpikernelhack'
2023-03-30 21:14:25,212: INFO - + Removing 'diversion of /boot/overlays/pifi-40.dtbo to /usr/share/rpikernelhack/overlays/pifi-40.dtbo by rpikernelhack'
2023-03-30 21:14:25,281: INFO - + Removing 'diversion of /boot/overlays/pifi-dac-hd.dtbo to /usr/share/rpikernelhack/overlays/pifi-dac-hd.dtbo by rpikernelhack'
2023-03-30 21:14:25,348: INFO - + Removing 'diversion of /boot/overlays/pifi-dac-zero.dtbo to /usr/share/rpikernelhack/overlays/pifi-dac-zero.dtbo by rpikernelhack'
2023-03-30 21:14:25,416: INFO - + Removing 'diversion of /boot/overlays/pifi-mini-210.dtbo to /usr/share/rpikernelhack/overlays/pifi-mini-210.dtbo by rpikernelhack'
2023-03-30 21:14:25,486: INFO - + Removing 'diversion of /boot/overlays/piglow.dtbo to /usr/share/rpikernelhack/overlays/piglow.dtbo by rpikernelhack'
2023-03-30 21:14:25,554: INFO - + Removing 'diversion of /boot/overlays/piscreen.dtbo to /usr/share/rpikernelhack/overlays/piscreen.dtbo by rpikernelhack'
2023-03-30 21:14:25,627: INFO - + Removing 'diversion of /boot/overlays/piscreen2r.dtbo to /usr/share/rpikernelhack/overlays/piscreen2r.dtbo by rpikernelhack'
2023-03-30 21:14:25,695: INFO - + Removing 'diversion of /boot/overlays/pisound.dtbo to /usr/share/rpikernelhack/overlays/pisound.dtbo by rpikernelhack'
2023-03-30 21:14:25,769: INFO - + Removing 'diversion of /boot/overlays/pitft22.dtbo to /usr/share/rpikernelhack/overlays/pitft22.dtbo by rpikernelhack'
2023-03-30 21:14:25,847: INFO - + Removing 'diversion of /boot/overlays/pitft28-capacitive.dtbo to /usr/share/rpikernelhack/overlays/pitft28-capacitive.dtbo by rpikernelhack'
2023-03-30 21:14:25,913: INFO - + Removing 'diversion of /boot/overlays/pitft28-resistive.dtbo to /usr/share/rpikernelhack/overlays/pitft28-resistive.dtbo by rpikernelhack'
2023-03-30 21:14:25,981: INFO - + Removing 'diversion of /boot/overlays/pitft35-resistive.dtbo to /usr/share/rpikernelhack/overlays/pitft35-resistive.dtbo by rpikernelhack'
2023-03-30 21:14:26,049: INFO - + Removing 'diversion of /boot/overlays/pps-gpio.dtbo to /usr/share/rpikernelhack/overlays/pps-gpio.dtbo by rpikernelhack'
2023-03-30 21:14:26,117: INFO - + Removing 'diversion of /boot/overlays/proto-codec.dtbo to /usr/share/rpikernelhack/overlays/proto-codec.dtbo by rpikernelhack'
2023-03-30 21:14:26,188: INFO - + Removing 'diversion of /boot/overlays/pwm-2chan.dtbo to /usr/share/rpikernelhack/overlays/pwm-2chan.dtbo by rpikernelhack'
2023-03-30 21:14:26,256: INFO - + Removing 'diversion of /boot/overlays/pwm-ir-tx.dtbo to /usr/share/rpikernelhack/overlays/pwm-ir-tx.dtbo by rpikernelhack'
2023-03-30 21:14:26,324: INFO - + Removing 'diversion of /boot/overlays/pwm.dtbo to /usr/share/rpikernelhack/overlays/pwm.dtbo by rpikernelhack'
2023-03-30 21:14:26,392: INFO - + Removing 'diversion of /boot/overlays/pwm1.dtbo to /usr/share/rpikernelhack/overlays/pwm1.dtbo by rpikernelhack'
2023-03-30 21:14:26,463: INFO - + Removing 'diversion of /boot/overlays/qca7000-uart0.dtbo to /usr/share/rpikernelhack/overlays/qca7000-uart0.dtbo by rpikernelhack'
2023-03-30 21:14:26,534: INFO - + Removing 'diversion of /boot/overlays/qca7000.dtbo to /usr/share/rpikernelhack/overlays/qca7000.dtbo by rpikernelhack'
2023-03-30 21:14:26,603: INFO - + Removing 'diversion of /boot/overlays/ramoops-pi4.dtbo to /usr/share/rpikernelhack/overlays/ramoops-pi4.dtbo by rpikernelhack'
2023-03-30 21:14:26,669: INFO - + Removing 'diversion of /boot/overlays/ramoops.dtbo to /usr/share/rpikernelhack/overlays/ramoops.dtbo by rpikernelhack'
2023-03-30 21:14:26,738: INFO - + Removing 'diversion of /boot/overlays/rotary-encoder.dtbo to /usr/share/rpikernelhack/overlays/rotary-encoder.dtbo by rpikernelhack'
2023-03-30 21:14:26,806: INFO - + Removing 'diversion of /boot/overlays/rpi-backlight.dtbo to /usr/share/rpikernelhack/overlays/rpi-backlight.dtbo by rpikernelhack'
2023-03-30 21:14:26,873: INFO - + Removing 'diversion of /boot/overlays/rpi-codeczero.dtbo to /usr/share/rpikernelhack/overlays/rpi-codeczero.dtbo by rpikernelhack'
2023-03-30 21:14:26,943: INFO - + Removing 'diversion of /boot/overlays/rpi-dacplus.dtbo to /usr/share/rpikernelhack/overlays/rpi-dacplus.dtbo by rpikernelhack'
2023-03-30 21:14:27,010: INFO - + Removing 'diversion of /boot/overlays/rpi-dacpro.dtbo to /usr/share/rpikernelhack/overlays/rpi-dacpro.dtbo by rpikernelhack'
2023-03-30 21:14:27,075: INFO - + Removing 'diversion of /boot/overlays/rpi-digiampplus.dtbo to /usr/share/rpikernelhack/overlays/rpi-digiampplus.dtbo by rpikernelhack'
2023-03-30 21:14:27,143: INFO - + Removing 'diversion of /boot/overlays/rpi-ft5406.dtbo to /usr/share/rpikernelhack/overlays/rpi-ft5406.dtbo by rpikernelhack'
2023-03-30 21:14:27,210: INFO - + Removing 'diversion of /boot/overlays/rpi-poe-plus.dtbo to /usr/share/rpikernelhack/overlays/rpi-poe-plus.dtbo by rpikernelhack'
2023-03-30 21:14:27,277: INFO - + Removing 'diversion of /boot/overlays/rpi-poe.dtbo to /usr/share/rpikernelhack/overlays/rpi-poe.dtbo by rpikernelhack'
2023-03-30 21:14:27,344: INFO - + Removing 'diversion of /boot/overlays/rpi-sense-v2.dtbo to /usr/share/rpikernelhack/overlays/rpi-sense-v2.dtbo by rpikernelhack'
2023-03-30 21:14:27,411: INFO - + Removing 'diversion of /boot/overlays/rpi-sense.dtbo to /usr/share/rpikernelhack/overlays/rpi-sense.dtbo by rpikernelhack'
2023-03-30 21:14:27,479: INFO - + Removing 'diversion of /boot/overlays/rpi-tv.dtbo to /usr/share/rpikernelhack/overlays/rpi-tv.dtbo by rpikernelhack'
2023-03-30 21:14:27,549: INFO - + Removing 'diversion of /boot/overlays/rra-digidac1-wm8741-audio.dtbo to /usr/share/rpikernelhack/overlays/rra-digidac1-wm8741-audio.dtbo by rpikernelhack'
2023-03-30 21:14:27,615: INFO - + Removing 'diversion of /boot/overlays/sainsmart18.dtbo to /usr/share/rpikernelhack/overlays/sainsmart18.dtbo by rpikernelhack'
2023-03-30 21:14:27,681: INFO - + Removing 'diversion of /boot/overlays/sc16is750-i2c.dtbo to /usr/share/rpikernelhack/overlays/sc16is750-i2c.dtbo by rpikernelhack'
2023-03-30 21:14:27,748: INFO - + Removing 'diversion of /boot/overlays/sc16is752-i2c.dtbo to /usr/share/rpikernelhack/overlays/sc16is752-i2c.dtbo by rpikernelhack'
2023-03-30 21:14:27,812: INFO - + Removing 'diversion of /boot/overlays/sc16is752-spi0.dtbo to /usr/share/rpikernelhack/overlays/sc16is752-spi0.dtbo by rpikernelhack'
2023-03-30 21:14:27,879: INFO - + Removing 'diversion of /boot/overlays/sc16is752-spi1.dtbo to /usr/share/rpikernelhack/overlays/sc16is752-spi1.dtbo by rpikernelhack'
2023-03-30 21:14:27,946: INFO - + Removing 'diversion of /boot/overlays/sdhost.dtbo to /usr/share/rpikernelhack/overlays/sdhost.dtbo by rpikernelhack'
2023-03-30 21:14:28,014: INFO - + Removing 'diversion of /boot/overlays/sdio.dtbo to /usr/share/rpikernelhack/overlays/sdio.dtbo by rpikernelhack'
2023-03-30 21:14:28,079: INFO - + Removing 'diversion of /boot/overlays/seeed-can-fd-hat-v1.dtbo to /usr/share/rpikernelhack/overlays/seeed-can-fd-hat-v1.dtbo by rpikernelhack'
2023-03-30 21:14:28,144: INFO - + Removing 'diversion of /boot/overlays/seeed-can-fd-hat-v2.dtbo to /usr/share/rpikernelhack/overlays/seeed-can-fd-hat-v2.dtbo by rpikernelhack'
2023-03-30 21:14:28,210: INFO - + Removing 'diversion of /boot/overlays/sh1106-spi.dtbo to /usr/share/rpikernelhack/overlays/sh1106-spi.dtbo by rpikernelhack'
2023-03-30 21:14:28,278: INFO - + Removing 'diversion of /boot/overlays/si446x-spi0.dtbo to /usr/share/rpikernelhack/overlays/si446x-spi0.dtbo by rpikernelhack'
2023-03-30 21:14:28,344: INFO - + Removing 'diversion of /boot/overlays/smi-dev.dtbo to /usr/share/rpikernelhack/overlays/smi-dev.dtbo by rpikernelhack'
2023-03-30 21:14:28,410: INFO - + Removing 'diversion of /boot/overlays/smi-nand.dtbo to /usr/share/rpikernelhack/overlays/smi-nand.dtbo by rpikernelhack'
2023-03-30 21:14:28,478: INFO - + Removing 'diversion of /boot/overlays/smi.dtbo to /usr/share/rpikernelhack/overlays/smi.dtbo by rpikernelhack'
2023-03-30 21:14:28,545: INFO - + Removing 'diversion of /boot/overlays/spi-gpio35-39.dtbo to /usr/share/rpikernelhack/overlays/spi-gpio35-39.dtbo by rpikernelhack'
2023-03-30 21:14:28,617: INFO - + Removing 'diversion of /boot/overlays/spi-gpio40-45.dtbo to /usr/share/rpikernelhack/overlays/spi-gpio40-45.dtbo by rpikernelhack'
2023-03-30 21:14:28,684: INFO - + Removing 'diversion of /boot/overlays/spi-rtc.dtbo to /usr/share/rpikernelhack/overlays/spi-rtc.dtbo by rpikernelhack'
2023-03-30 21:14:28,751: INFO - + Removing 'diversion of /boot/overlays/spi0-0cs.dtbo to /usr/share/rpikernelhack/overlays/spi0-0cs.dtbo by rpikernelhack'
2023-03-30 21:14:28,819: INFO - + Removing 'diversion of /boot/overlays/spi0-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi0-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:28,889: INFO - + Removing 'diversion of /boot/overlays/spi0-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi0-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:28,958: INFO - + Removing 'diversion of /boot/overlays/spi1-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi1-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,025: INFO - + Removing 'diversion of /boot/overlays/spi1-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi1-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,092: INFO - + Removing 'diversion of /boot/overlays/spi1-3cs.dtbo to /usr/share/rpikernelhack/overlays/spi1-3cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,159: INFO - + Removing 'diversion of /boot/overlays/spi2-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi2-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,224: INFO - + Removing 'diversion of /boot/overlays/spi2-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi2-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,290: INFO - + Removing 'diversion of /boot/overlays/spi2-3cs.dtbo to /usr/share/rpikernelhack/overlays/spi2-3cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,355: INFO - + Removing 'diversion of /boot/overlays/spi3-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi3-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,432: INFO - + Removing 'diversion of /boot/overlays/spi3-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi3-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,527: INFO - + Removing 'diversion of /boot/overlays/spi4-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi4-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,616: INFO - + Removing 'diversion of /boot/overlays/spi4-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi4-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,684: INFO - + Removing 'diversion of /boot/overlays/spi5-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi5-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,751: INFO - + Removing 'diversion of /boot/overlays/spi5-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi5-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,819: INFO - + Removing 'diversion of /boot/overlays/spi6-1cs.dtbo to /usr/share/rpikernelhack/overlays/spi6-1cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,886: INFO - + Removing 'diversion of /boot/overlays/spi6-2cs.dtbo to /usr/share/rpikernelhack/overlays/spi6-2cs.dtbo by rpikernelhack'
2023-03-30 21:14:29,953: INFO - + Removing 'diversion of /boot/overlays/ssd1306-spi.dtbo to /usr/share/rpikernelhack/overlays/ssd1306-spi.dtbo by rpikernelhack'
2023-03-30 21:14:30,018: INFO - + Removing 'diversion of /boot/overlays/ssd1306.dtbo to /usr/share/rpikernelhack/overlays/ssd1306.dtbo by rpikernelhack'
2023-03-30 21:14:30,083: INFO - + Removing 'diversion of /boot/overlays/ssd1331-spi.dtbo to /usr/share/rpikernelhack/overlays/ssd1331-spi.dtbo by rpikernelhack'
2023-03-30 21:14:30,150: INFO - + Removing 'diversion of /boot/overlays/ssd1351-spi.dtbo to /usr/share/rpikernelhack/overlays/ssd1351-spi.dtbo by rpikernelhack'
2023-03-30 21:14:30,217: INFO - + Removing 'diversion of /boot/overlays/superaudioboard.dtbo to /usr/share/rpikernelhack/overlays/superaudioboard.dtbo by rpikernelhack'
2023-03-30 21:14:30,285: INFO - + Removing 'diversion of /boot/overlays/sx150x.dtbo to /usr/share/rpikernelhack/overlays/sx150x.dtbo by rpikernelhack'
2023-03-30 21:14:30,354: INFO - + Removing 'diversion of /boot/overlays/tc358743-audio.dtbo to /usr/share/rpikernelhack/overlays/tc358743-audio.dtbo by rpikernelhack'
2023-03-30 21:14:30,429: INFO - + Removing 'diversion of /boot/overlays/tc358743.dtbo to /usr/share/rpikernelhack/overlays/tc358743.dtbo by rpikernelhack'
2023-03-30 21:14:30,528: INFO - + Removing 'diversion of /boot/overlays/tinylcd35.dtbo to /usr/share/rpikernelhack/overlays/tinylcd35.dtbo by rpikernelhack'
2023-03-30 21:14:30,597: INFO - + Removing 'diversion of /boot/overlays/tpm-slb9670.dtbo to /usr/share/rpikernelhack/overlays/tpm-slb9670.dtbo by rpikernelhack'
2023-03-30 21:14:30,661: INFO - + Removing 'diversion of /boot/overlays/tpm-slb9673.dtbo to /usr/share/rpikernelhack/overlays/tpm-slb9673.dtbo by rpikernelhack'
2023-03-30 21:14:30,728: INFO - + Removing 'diversion of /boot/overlays/uart0.dtbo to /usr/share/rpikernelhack/overlays/uart0.dtbo by rpikernelhack'
2023-03-30 21:14:30,797: INFO - + Removing 'diversion of /boot/overlays/uart1.dtbo to /usr/share/rpikernelhack/overlays/uart1.dtbo by rpikernelhack'
2023-03-30 21:14:30,861: INFO - + Removing 'diversion of /boot/overlays/uart2.dtbo to /usr/share/rpikernelhack/overlays/uart2.dtbo by rpikernelhack'
2023-03-30 21:14:30,926: INFO - + Removing 'diversion of /boot/overlays/uart3.dtbo to /usr/share/rpikernelhack/overlays/uart3.dtbo by rpikernelhack'
2023-03-30 21:14:30,992: INFO - + Removing 'diversion of /boot/overlays/uart4.dtbo to /usr/share/rpikernelhack/overlays/uart4.dtbo by rpikernelhack'
2023-03-30 21:14:31,059: INFO - + Removing 'diversion of /boot/overlays/uart5.dtbo to /usr/share/rpikernelhack/overlays/uart5.dtbo by rpikernelhack'
2023-03-30 21:14:31,167: INFO - + Removing 'diversion of /boot/overlays/udrc.dtbo to /usr/share/rpikernelhack/overlays/udrc.dtbo by rpikernelhack'
2023-03-30 21:14:31,234: INFO - + Removing 'diversion of /boot/overlays/ugreen-dabboard.dtbo to /usr/share/rpikernelhack/overlays/ugreen-dabboard.dtbo by rpikernelhack'
2023-03-30 21:14:31,300: INFO - + Removing 'diversion of /boot/overlays/upstream-pi4.dtbo to /usr/share/rpikernelhack/overlays/upstream-pi4.dtbo by rpikernelhack'
2023-03-30 21:14:31,369: INFO - + Removing 'diversion of /boot/overlays/upstream.dtbo to /usr/share/rpikernelhack/overlays/upstream.dtbo by rpikernelhack'
2023-03-30 21:14:31,435: INFO - + Removing 'diversion of /boot/overlays/vc4-fkms-v3d-pi4.dtbo to /usr/share/rpikernelhack/overlays/vc4-fkms-v3d-pi4.dtbo by rpikernelhack'
2023-03-30 21:14:31,505: INFO - + Removing 'diversion of /boot/overlays/vc4-fkms-v3d.dtbo to /usr/share/rpikernelhack/overlays/vc4-fkms-v3d.dtbo by rpikernelhack'
2023-03-30 21:14:31,573: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dpi-generic.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-generic.dtbo by rpikernelhack'
2023-03-30 21:14:31,639: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dpi-hyperpixel2r.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-hyperpixel2r.dtbo by rpikernelhack'
2023-03-30 21:14:31,708: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dpi-hyperpixel4.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-hyperpixel4.dtbo by rpikernelhack'
2023-03-30 21:14:31,774: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dpi-hyperpixel4sq.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-hyperpixel4sq.dtbo by rpikernelhack'
2023-03-30 21:14:31,840: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dpi-panel.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dpi-panel.dtbo by rpikernelhack'
2023-03-30 21:14:31,910: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dsi-7inch.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dsi-7inch.dtbo by rpikernelhack'
2023-03-30 21:14:31,979: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dsi-lt070me05000-v2.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dsi-lt070me05000-v2.dtbo by rpikernelhack'
2023-03-30 21:14:32,047: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-dsi-lt070me05000.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-dsi-lt070me05000.dtbo by rpikernelhack'
2023-03-30 21:14:32,116: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-kippah-7inch.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-kippah-7inch.dtbo by rpikernelhack'
2023-03-30 21:14:32,187: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-v3d-pi4.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-v3d-pi4.dtbo by rpikernelhack'
2023-03-30 21:14:32,255: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-v3d.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-v3d.dtbo by rpikernelhack'
2023-03-30 21:14:32,324: INFO - + Removing 'diversion of /boot/overlays/vc4-kms-vga666.dtbo to /usr/share/rpikernelhack/overlays/vc4-kms-vga666.dtbo by rpikernelhack'
2023-03-30 21:14:32,392: INFO - + Removing 'diversion of /boot/overlays/vga666.dtbo to /usr/share/rpikernelhack/overlays/vga666.dtbo by rpikernelhack'
2023-03-30 21:14:32,464: INFO - + Removing 'diversion of /boot/overlays/vl805.dtbo to /usr/share/rpikernelhack/overlays/vl805.dtbo by rpikernelhack'
2023-03-30 21:14:32,529: INFO - + Removing 'diversion of /boot/overlays/w1-gpio-pullup.dtbo to /usr/share/rpikernelhack/overlays/w1-gpio-pullup.dtbo by rpikernelhack'
2023-03-30 21:14:32,596: INFO - + Removing 'diversion of /boot/overlays/w1-gpio.dtbo to /usr/share/rpikernelhack/overlays/w1-gpio.dtbo by rpikernelhack'
2023-03-30 21:14:32,662: INFO - + Removing 'diversion of /boot/overlays/w5500.dtbo to /usr/share/rpikernelhack/overlays/w5500.dtbo by rpikernelhack'
2023-03-30 21:14:32,728: INFO - + Removing 'diversion of /boot/overlays/watterott-display.dtbo to /usr/share/rpikernelhack/overlays/watterott-display.dtbo by rpikernelhack'
2023-03-30 21:14:32,795: INFO - + Removing 'diversion of /boot/overlays/waveshare-can-fd-hat-mode-a.dtbo to /usr/share/rpikernelhack/overlays/waveshare-can-fd-hat-mode-a.dtbo by rpikernelhack'
2023-03-30 21:14:32,861: INFO - + Removing 'diversion of /boot/overlays/waveshare-can-fd-hat-mode-b.dtbo to /usr/share/rpikernelhack/overlays/waveshare-can-fd-hat-mode-b.dtbo by rpikernelhack'
2023-03-30 21:14:32,930: INFO - + Removing 'diversion of /boot/overlays/wittypi.dtbo to /usr/share/rpikernelhack/overlays/wittypi.dtbo by rpikernelhack'
2023-03-30 21:14:32,998: INFO - + Removing 'diversion of /boot/overlays/wm8960-soundcard.dtbo to /usr/share/rpikernelhack/overlays/wm8960-soundcard.dtbo by rpikernelhack'
2023-03-30 21:14:33,041: WARNING - run-parts: executing /etc/kernel/postinst.d/apt-auto-removal 6.1.19+ /boot/kernel.img
2023-03-30 21:14:33,064: WARNING - run-parts: executing /etc/kernel/postinst.d/initramfs-tools 6.1.19+ /boot/kernel.img
2023-03-30 21:14:33,066: WARNING - run-parts: executing /etc/kernel/postinst.d/unattended-upgrades 6.1.19+ /boot/kernel.img
2023-03-30 21:14:33,074: WARNING - run-parts: executing /etc/kernel/postinst.d/apt-auto-removal 6.1.19-v7+ /boot/kernel7.img
2023-03-30 21:14:33,096: WARNING - run-parts: executing /etc/kernel/postinst.d/initramfs-tools 6.1.19-v7+ /boot/kernel7.img
2023-03-30 21:14:33,098: WARNING - run-parts: executing /etc/kernel/postinst.d/unattended-upgrades 6.1.19-v7+ /boot/kernel7.img
2023-03-30 21:14:33,104: WARNING - run-parts: executing /etc/kernel/postinst.d/apt-auto-removal 6.1.19-v7l+ /boot/kernel7l.img
2023-03-30 21:14:33,126: WARNING - run-parts: executing /etc/kernel/postinst.d/initramfs-tools 6.1.19-v7l+ /boot/kernel7l.img
2023-03-30 21:14:33,128: WARNING - run-parts: executing /etc/kernel/postinst.d/unattended-upgrades 6.1.19-v7l+ /boot/kernel7l.img
2023-03-30 21:14:33,135: WARNING - run-parts: executing /etc/kernel/postinst.d/apt-auto-removal 6.1.19-v8+ /boot/kernel8.img
2023-03-30 21:14:33,156: WARNING - run-parts: executing /etc/kernel/postinst.d/initramfs-tools 6.1.19-v8+ /boot/kernel8.img
2023-03-30 21:14:33,158: WARNING - run-parts: executing /etc/kernel/postinst.d/unattended-upgrades 6.1.19-v8+ /boot/kernel8.img
2023-03-30 21:14:33,186: INFO - + Setting up php7.4-intl (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:33,938: INFO - + Setting up mariadb-client-core-10.5 (1:10.5.18-0+deb11u1) ...
2023-03-30 21:14:33,957: INFO - + Setting up raspberrypi-bootloader (1:1.20230317-1) ...
2023-03-30 21:14:34,038: INFO - + Removing 'diversion of /boot/start.elf to /usr/share/rpikernelhack/start.elf by rpikernelhack'
2023-03-30 21:14:34,257: INFO - + Removing 'diversion of /boot/start_cd.elf to /usr/share/rpikernelhack/start_cd.elf by rpikernelhack'
2023-03-30 21:14:34,351: INFO - + Removing 'diversion of /boot/start_db.elf to /usr/share/rpikernelhack/start_db.elf by rpikernelhack'
2023-03-30 21:14:34,571: INFO - + Removing 'diversion of /boot/start_x.elf to /usr/share/rpikernelhack/start_x.elf by rpikernelhack'
2023-03-30 21:14:34,802: INFO - + Removing 'diversion of /boot/fixup.dat to /usr/share/rpikernelhack/fixup.dat by rpikernelhack'
2023-03-30 21:14:34,875: INFO - + Removing 'diversion of /boot/fixup_cd.dat to /usr/share/rpikernelhack/fixup_cd.dat by rpikernelhack'
2023-03-30 21:14:34,940: INFO - + Removing 'diversion of /boot/fixup_db.dat to /usr/share/rpikernelhack/fixup_db.dat by rpikernelhack'
2023-03-30 21:14:35,008: INFO - + Removing 'diversion of /boot/fixup_x.dat to /usr/share/rpikernelhack/fixup_x.dat by rpikernelhack'
2023-03-30 21:14:35,072: INFO - + Removing 'diversion of /boot/bootcode.bin to /usr/share/rpikernelhack/bootcode.bin by rpikernelhack'
2023-03-30 21:14:35,138: INFO - + Removing 'diversion of /boot/start4.elf to /usr/share/rpikernelhack/start4.elf by rpikernelhack'
2023-03-30 21:14:35,277: INFO - + Removing 'diversion of /boot/start4cd.elf to /usr/share/rpikernelhack/start4cd.elf by rpikernelhack'
2023-03-30 21:14:35,367: INFO - + Removing 'diversion of /boot/start4db.elf to /usr/share/rpikernelhack/start4db.elf by rpikernelhack'
2023-03-30 21:14:35,556: INFO - + Removing 'diversion of /boot/start4x.elf to /usr/share/rpikernelhack/start4x.elf by rpikernelhack'
2023-03-30 21:14:35,738: INFO - + Removing 'diversion of /boot/fixup4.dat to /usr/share/rpikernelhack/fixup4.dat by rpikernelhack'
2023-03-30 21:14:35,801: INFO - + Removing 'diversion of /boot/fixup4cd.dat to /usr/share/rpikernelhack/fixup4cd.dat by rpikernelhack'
2023-03-30 21:14:35,863: INFO - + Removing 'diversion of /boot/fixup4db.dat to /usr/share/rpikernelhack/fixup4db.dat by rpikernelhack'
2023-03-30 21:14:35,927: INFO - + Removing 'diversion of /boot/fixup4x.dat to /usr/share/rpikernelhack/fixup4x.dat by rpikernelhack'
2023-03-30 21:14:35,989: INFO - + Removing 'diversion of /boot/LICENCE.broadcom to /usr/share/rpikernelhack/LICENCE.broadcom by rpikernelhack'
2023-03-30 21:14:36,039: INFO - + Setting up libraspberrypi0:arm64 (1:2+git20220616~133208+6e8f786-1) ...
2023-03-30 21:14:36,059: INFO - + Setting up nano (5.4-2+deb11u2) ...
2023-03-30 21:14:36,109: INFO - + Setting up mariadb-client-10.5 (1:10.5.18-0+deb11u1) ...
2023-03-30 21:14:36,154: INFO - + Setting up php7.4-ldap (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:37,018: INFO - + Setting up php7.4-opcache (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:37,935: INFO - + Setting up raspi-config (20230214) ...
2023-03-30 21:14:37,950: DEBUG - 
2023-03-30 21:14:37,951: DEBUG - Configuration file '/etc/default/cpu_governor', does not exist on system.
2023-03-30 21:14:37,951: DEBUG - Installing new config file as you requested.
2023-03-30 21:14:37,965: DEBUG - Installing new version of config file /etc/init.d/raspi-config ...
2023-03-30 21:14:38,093: WARNING - insserv: FATAL: service mountkernfs has to be enabled to use service raspi-config
2023-03-30 21:14:38,606: INFO - + Setting up php7.4-gd (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:39,426: INFO - + Setting up php7.4-json (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:40,233: INFO - + Setting up php7.4-xml (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:46,870: INFO - + Setting up php7.4-cli (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:49,218: INFO - + Setting up mariadb-server-10.5 (1:10.5.18-0+deb11u1) ...
2023-03-30 21:14:52,264: INFO - + Setting up libraspberrypi-bin (1:2+git20220616~133208+6e8f786-1) ...
2023-03-30 21:14:52,287: INFO - + Setting up mariadb-server (1:10.5.18-0+deb11u1) ...
2023-03-30 21:14:52,310: INFO - + Setting up libraspberrypi-dev (1:2+git20220616~133208+6e8f786-1) ...
2023-03-30 21:14:52,332: INFO - + Setting up rpi-eeprom (16.0-1) ...
2023-03-30 21:14:53,379: INFO - + Setting up php7.4-fpm (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:14:53,394: DEBUG - Installing new version of config file /etc/init.d/php7.4-fpm ...
2023-03-30 21:14:56,794: INFO - + Setting up libraspberrypi-doc (1:2+git20220616~133208+6e8f786-1) ...
2023-03-30 21:14:56,813: INFO - + Setting up raspi-utils (20230123-1) ...
2023-03-30 21:14:56,833: INFO - + Setting up raspinfo (20230123-1) ...
2023-03-30 21:14:56,854: INFO - + Processing triggers for rsyslog (8.2102.0-2+deb11u1) ...
2023-03-30 21:14:56,931: INFO - + Processing triggers for man-db (2.9.4-2) ...
2023-03-30 21:15:02,426: INFO - + Processing triggers for ntp (1:4.2.8p15+dfsg-1) ...
2023-03-30 21:15:02,541: INFO - + Processing triggers for libc-bin (2.31-13+rpt2+rpi1+deb11u5) ...
2023-03-30 21:15:02,592: INFO - + Processing triggers for php7.4-cli (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:15:02,611: INFO - + Processing triggers for php7.4-fpm (1:7.4.33-5+0~20230214.77+debian11~1.gbpa1ea7f) ...
2023-03-30 21:15:03,627: SUCCESS - System upgraded
```

**update dns records at no-ip**

```sh
; Basic ipv4/ipv6 records
kirkrehn 3600 IN A 75.213.32.87

; Mail
kirkrehn 3600 IN MX 10 kirkrehn.myddns.me.
kirkrehn 3600 IN TXT "v=spf1 a mx -all"
mail._domainkey.kirkrehn 3600 IN TXT "v=DKIM1; h=sha256; k=rsa; p=MIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQC4/HFoThvldgMgsku2BHcBXvXQbjBmwpqdUWyZnmhg2ZUCHth8TQH+rbiBhbtvqp9XmMB/p4x8xTZE8KY0hBK+1rMblzWVGLkXef7jlbIZzXieMtKkLqW3wYDva3s27xltqxutKvg5vOm/GtpTW/5zZs/d28ocK8LIQwq2tUs64wIDAQAB"
_dmarc.kirkrehn 3600 IN TXT "v=DMARC1; p=none"



; Extra
*.kirkrehn 3600 IN A 75.213.32.87
kirkrehn 3600 IN CAA 0 issue "letsencrypt.org"
```

### let's encrypt certificate

```sh
args:
  force: true
  no_checks: false
ended_at: 2023-03-30 20:22:49.970550
error: null
interface: api
operation: letsencrypt_cert_install
parent: null
related_to:
- - domain
  - maindomain.tld
started_at: 2023-03-30 20:22:19.425428
success: true
yunohost_version: 11.1.15

============

2023-03-30 21:22:19,443: DEBUG - Making sure tmp folders exists...
2023-03-30 21:22:19,460: DEBUG - Fetching IP from https://ip.yunohost.org 
2023-03-30 21:22:20,852: DEBUG - IP fetched: xx.xx.xx.xx
2023-03-30 21:22:20,868: DEBUG - No default route for IPv6, so assuming there's no IP address for that version
2023-03-30 21:22:20,869: DEBUG - IP fetched: None
2023-03-30 21:22:20,870: DEBUG - Prepare key and certificate signing request (CSR) for maindomain.tld...
2023-03-30 21:22:21,225: DEBUG - Saving to /tmp/acme-challenge-private/maindomain.tld.csr.
2023-03-30 21:22:21,226: DEBUG - Now using ACME Tiny to sign the certificate...
2023-03-30 21:22:21,227: INFO - Parsing account key...
2023-03-30 21:22:21,248: INFO - Parsing CSR...
2023-03-30 21:22:21,269: INFO - Found domains: maindomain.tld
2023-03-30 21:22:21,271: INFO - Getting directory...
2023-03-30 21:22:27,728: INFO - Directory found!
2023-03-30 21:22:27,730: INFO - Registering account...
2023-03-30 21:22:28,528: INFO - Registered!
2023-03-30 21:22:28,533: INFO - Creating new order...
2023-03-30 21:22:29,419: INFO - Order created!
2023-03-30 21:22:30,060: INFO - Verifying maindomain.tld...
2023-03-30 21:22:31,311: INFO - maindomain.tld verified!
2023-03-30 21:22:31,313: INFO - Signing certificate...
2023-03-30 21:22:33,301: INFO - Certificate signed!
2023-03-30 21:22:33,303: DEBUG - Saving the key and signed certificate...
2023-03-30 21:22:33,305: DEBUG - Enabling the certificate for domain maindomain.tld ...
2023-03-30 21:22:33,306: DEBUG - Restarting services...
2023-03-30 21:22:33,484: DEBUG - Running 'systemctl restart dovecot'
2023-03-30 21:22:34,982: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nginx 7>&1']'
2023-03-30 21:22:34,997: DEBUG - + set -e
2023-03-30 21:22:34,998: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 21:22:35,000: DEBUG - +++ set +o
2023-03-30 21:22:35,001: DEBUG - +++ grep xtrace
2023-03-30 21:22:35,004: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 21:22:35,004: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 21:22:35,044: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nginx
2023-03-30 21:22:35,045: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nginx
2023-03-30 21:22:35,046: DEBUG - + cd /usr/share/yunohost/conf/nginx
2023-03-30 21:22:35,046: DEBUG - + nginx_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx
2023-03-30 21:22:35,046: DEBUG - + nginx_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:35,047: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:35,051: DEBUG - + cp plain/acme-challenge.conf.inc plain/global.conf plain/ssowat.conf plain/yunohost_http_errors.conf.inc plain/yunohost_panel.conf.inc plain/yunohost_sso.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:35,058: DEBUG - ++ yunohost settings get misc.portal.ssowat_panel_overlay_enabled
2023-03-30 21:22:35,059: DEBUG - ++ int_to_bool
2023-03-30 21:22:35,059: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-30 21:22:35,705: DEBUG - + panel_overlay=True
2023-03-30 21:22:35,706: DEBUG - + '[' True == False ']'
2023-03-30 21:22:35,706: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 21:22:35,708: DEBUG - + main_domain=maindomain.tld
2023-03-30 21:22:35,710: DEBUG - ++ yunohost settings get security.nginx.nginx_redirect_to_https
2023-03-30 21:22:35,711: DEBUG - ++ int_to_bool
2023-03-30 21:22:35,712: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-30 21:22:36,362: DEBUG - + export redirect_to_https=True
2023-03-30 21:22:36,363: DEBUG - + redirect_to_https=True
2023-03-30 21:22:36,363: DEBUG - ++ yunohost settings get security.nginx.nginx_compatibility
2023-03-30 21:22:37,005: DEBUG - + export compatibility=intermediate
2023-03-30 21:22:37,006: DEBUG - + compatibility=intermediate
2023-03-30 21:22:37,007: DEBUG - ++ yunohost settings get security.experimental.security_experimental_enabled
2023-03-30 21:22:37,008: DEBUG - ++ int_to_bool
2023-03-30 21:22:37,009: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-30 21:22:37,647: DEBUG - + export experimental=False
2023-03-30 21:22:37,648: DEBUG - + experimental=False
2023-03-30 21:22:37,648: DEBUG - + ynh_render_template security.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-30 21:22:37,649: DEBUG - + local template_path=security.conf.inc
2023-03-30 21:22:37,649: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-30 21:22:37,650: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-30 21:22:37,651: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:37,654: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:37,654: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:37,655: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:37,836: DEBUG - ++ yunohost domain cert status --json
2023-03-30 21:22:38,600: DEBUG - + cert_status='{"certificates": {"maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}}}'
2023-03-30 21:22:38,601: DEBUG - ++ yunohost domain list --features xmpp --output-as json
2023-03-30 21:22:38,602: DEBUG - ++ jq -r '.domains[]'
2023-03-30 21:22:39,307: DEBUG - + xmpp_domain_list=
2023-03-30 21:22:39,309: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-30 21:22:39,310: DEBUG - ++ jq -r '.domains[]'
2023-03-30 21:22:40,016: DEBUG - + mail_domain_list=maindomain.tld
2023-03-30 21:22:40,017: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 21:22:40,024: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-30 21:22:40,025: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-30 21:22:40,026: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-30 21:22:40,026: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-30 21:22:40,029: DEBUG - + export domain
2023-03-30 21:22:40,031: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"}}}'
2023-03-30 21:22:40,032: DEBUG - ++ jq '.certificates."maindomain.tld".CA_type'
2023-03-30 21:22:40,032: DEBUG - ++ tr -d '"'
2023-03-30 21:22:40,128: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-30 21:22:40,129: DEBUG - + domain_cert_ca=letsencrypt
2023-03-30 21:22:40,130: DEBUG - + grep -q '^maindomain.tld$'
2023-03-30 21:22:40,133: DEBUG - + export xmpp_enabled=False
2023-03-30 21:22:40,134: DEBUG - + xmpp_enabled=False
2023-03-30 21:22:40,135: DEBUG - + echo maindomain.tld
2023-03-30 21:22:40,135: DEBUG - + grep -q '^maindomain.tld$'
2023-03-30 21:22:40,138: DEBUG - + export mail_enabled=True
2023-03-30 21:22:40,139: DEBUG - + mail_enabled=True
2023-03-30 21:22:40,140: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 21:22:40,140: DEBUG - + local template_path=server.tpl.conf
2023-03-30 21:22:40,141: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 21:22:40,141: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 21:22:40,142: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:40,145: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:40,146: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:40,146: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:40,341: DEBUG - + '[' True == True ']'
2023-03-30 21:22:40,342: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-30 21:22:40,342: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-30 21:22:40,343: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-30 21:22:40,343: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-30 21:22:40,344: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail
2023-03-30 21:22:40,347: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:40,348: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:40,349: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:40,526: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf
2023-03-30 21:22:40,530: DEBUG - ++ yunohost settings get security.webadmin.webadmin_allowlist_enabled
2023-03-30 21:22:40,531: DEBUG - ++ int_to_bool
2023-03-30 21:22:40,532: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-30 21:22:41,164: DEBUG - + export webadmin_allowlist_enabled=False
2023-03-30 21:22:41,165: DEBUG - + webadmin_allowlist_enabled=False
2023-03-30 21:22:41,165: DEBUG - + '[' False == True ']'
2023-03-30 21:22:41,166: DEBUG - + ynh_render_template yunohost_admin.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-30 21:22:41,166: DEBUG - + local template_path=yunohost_admin.conf.inc
2023-03-30 21:22:41,167: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-30 21:22:41,167: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc
2023-03-30 21:22:41,168: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:41,171: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:41,172: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:41,172: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:41,354: DEBUG - + ynh_render_template yunohost_api.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-30 21:22:41,355: DEBUG - + local template_path=yunohost_api.conf.inc
2023-03-30 21:22:41,355: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-30 21:22:41,356: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc
2023-03-30 21:22:41,357: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:41,360: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:41,361: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:41,361: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:41,543: DEBUG - + ynh_render_template yunohost_admin.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-30 21:22:41,544: DEBUG - + local template_path=yunohost_admin.conf
2023-03-30 21:22:41,544: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-30 21:22:41,545: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf
2023-03-30 21:22:41,547: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-30 21:22:41,550: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:41,551: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:41,551: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:41,727: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/
2023-03-30 21:22:41,730: DEBUG - + cp redirect_to_admin.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/
2023-03-30 21:22:41,735: DEBUG - ++ ls -1 /etc/nginx/conf.d
2023-03-30 21:22:41,736: DEBUG - ++ awk '/^[^\.]+\.[^\.]+.*\.conf$/ { print $1 }'
2023-03-30 21:22:41,744: DEBUG - + conf_files=maindomain.tld.conf
2023-03-30 21:22:41,744: DEBUG - + for file in $conf_files
2023-03-30 21:22:41,745: DEBUG - + domain=maindomain.tld
2023-03-30 21:22:41,745: DEBUG - + [[ maindomain.tld =~ maindomain.tld ]]
2023-03-30 21:22:41,746: DEBUG - ++ ls -1 /var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-30 21:22:41,749: DEBUG - + autoconfig_files=/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-30 21:22:41,750: DEBUG - + for file in $autoconfig_files
2023-03-30 21:22:41,751: DEBUG - ++++ dirname /var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml
2023-03-30 21:22:41,754: DEBUG - +++ readlink -f /var/www/.well-known/maindomain.tld/autoconfig/mail/../..
2023-03-30 21:22:41,756: DEBUG - ++ basename /var/www/.well-known/maindomain.tld
2023-03-30 21:22:41,760: DEBUG - + domain=maindomain.tld
2023-03-30 21:22:41,760: DEBUG - + [[ maindomain.tld =~ maindomain.tld ]]
2023-03-30 21:22:41,761: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled
2023-03-30 21:22:41,763: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled/default
2023-03-30 21:22:42,767: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./19-postfix" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/postfix 7>&1']'
2023-03-30 21:22:42,782: DEBUG - + set -e
2023-03-30 21:22:42,783: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 21:22:42,785: DEBUG - +++ set +o
2023-03-30 21:22:42,785: DEBUG - +++ grep xtrace
2023-03-30 21:22:42,789: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 21:22:42,790: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 21:22:42,828: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/postfix
2023-03-30 21:22:42,829: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/postfix
2023-03-30 21:22:42,830: DEBUG - + cd /usr/share/yunohost/conf/postfix
2023-03-30 21:22:42,830: DEBUG - + postfix_dir=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 21:22:42,830: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 21:22:42,832: DEBUG - + default_dir=/var/cache/yunohost/regenconf/pending/postfix/etc/default/
2023-03-30 21:22:42,833: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/default/
2023-03-30 21:22:42,836: DEBUG - + cp plain/header_checks plain/ldap-accounts.cf plain/ldap-aliases.cf plain/ldap-domains.cf plain/ldap-groups.cf plain/master.cf plain/sender_canonical plain/smtp_reply_filter /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 21:22:42,841: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-30 21:22:42,843: DEBUG - + main_domain=maindomain.tld
2023-03-30 21:22:42,844: DEBUG - ++ yunohost settings get security.postfix.postfix_compatibility
2023-03-30 21:22:43,483: DEBUG - + export compatibility=intermediate
2023-03-30 21:22:43,484: DEBUG - + compatibility=intermediate
2023-03-30 21:22:43,485: DEBUG - + export relay_port=
2023-03-30 21:22:43,485: DEBUG - + relay_port=
2023-03-30 21:22:43,486: DEBUG - + export relay_user=
2023-03-30 21:22:43,487: DEBUG - + relay_user=
2023-03-30 21:22:43,488: DEBUG - + export relay_host=
2023-03-30 21:22:43,488: DEBUG - + relay_host=
2023-03-30 21:22:43,489: DEBUG - ++ yunohost settings get email.smtp.smtp_relay_enabled
2023-03-30 21:22:43,490: DEBUG - ++ int_to_bool
2023-03-30 21:22:43,490: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-30 21:22:44,120: DEBUG - + export relay_enabled=False
2023-03-30 21:22:44,121: DEBUG - + relay_enabled=False
2023-03-30 21:22:44,121: DEBUG - + '[' False == True ']'
2023-03-30 21:22:44,121: DEBUG - + export main_domain
2023-03-30 21:22:44,123: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-30 21:22:44,124: DEBUG - ++ jq -r '.domains[]'
2023-03-30 21:22:44,125: DEBUG - ++ tr '\n' ' '
2023-03-30 21:22:44,824: DEBUG - + export 'domain_list=maindomain.tld '
2023-03-30 21:22:44,825: DEBUG - + domain_list='maindomain.tld '
2023-03-30 21:22:44,825: DEBUG - + ynh_render_template main.cf /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-30 21:22:44,826: DEBUG - + local template_path=main.cf
2023-03-30 21:22:44,826: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-30 21:22:44,827: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf
2023-03-30 21:22:44,827: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 21:22:44,830: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:44,831: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:44,831: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:45,055: DEBUG - + ynh_render_template sni /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-30 21:22:45,055: DEBUG - + local template_path=sni
2023-03-30 21:22:45,056: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-30 21:22:45,057: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni
2023-03-30 21:22:45,058: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/postfix/etc/postfix
2023-03-30 21:22:45,061: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-30 21:22:45,062: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-30 21:22:45,062: DEBUG -                     ).render(os.environ));'
2023-03-30 21:22:45,241: DEBUG - + cat postsrsd
2023-03-30 21:22:45,242: DEBUG - + sed 's/{{ main_domain }}/maindomain.tld/g'
2023-03-30 21:22:45,243: DEBUG - + sed 's/{{ domain_list }}/maindomain.tld /g'
2023-03-30 21:22:45,248: DEBUG - ++ yunohost settings get email.smtp.smtp_allow_ipv6
2023-03-30 21:22:45,249: DEBUG - ++ int_to_bool
2023-03-30 21:22:45,249: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-30 21:22:45,880: DEBUG - + ipv6=True
2023-03-30 21:22:45,881: DEBUG - + '[' True == False ']'
2023-03-30 21:22:45,881: DEBUG - + '[' '!' -f /proc/net/if_inet6 ']'
2023-03-30 21:22:46,885: DEBUG - Checking pending configuration which would have been applied for category 'nginx'...
2023-03-30 21:22:46,919: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/sites-enabled/default' to system conf '/etc/nginx/sites-enabled/default'
2023-03-30 21:22:46,920: DEBUG - > system conf is already removed
2023-03-30 21:22:46,920: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc' to system conf '/etc/nginx/conf.d/security.conf.inc'
2023-03-30 21:22:46,921: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,922: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_admin.conf.inc'
2023-03-30 21:22:46,922: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,922: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_api.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_api.conf.inc'
2023-03-30 21:22:46,923: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,923: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_admin.conf' to system conf '/etc/nginx/conf.d/yunohost_admin.conf'
2023-03-30 21:22:46,924: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,924: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_http_errors.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_http_errors.conf.inc'
2023-03-30 21:22:46,925: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,925: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_panel.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_panel.conf.inc'
2023-03-30 21:22:46,926: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,926: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf' to system conf '/etc/nginx/conf.d/maindomain.tld.conf'
2023-03-30 21:22:46,927: DEBUG - Configuration file '/etc/nginx/conf.d/maindomain.tld.conf' backed up to '/var/cache/yunohost/regenconf/backup/etc/nginx/conf.d/maindomain.tld.conf-20230330.202246'
2023-03-30 21:22:46,928: DEBUG - Configuration file '/etc/nginx/conf.d/maindomain.tld.conf' updated
2023-03-30 21:22:46,929: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/ssowat.conf' to system conf '/etc/nginx/conf.d/ssowat.conf'
2023-03-30 21:22:46,930: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,930: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/acme-challenge.conf.inc' to system conf '/etc/nginx/conf.d/acme-challenge.conf.inc'
2023-03-30 21:22:46,931: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,931: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/global.conf' to system conf '/etc/nginx/conf.d/global.conf'
2023-03-30 21:22:46,931: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,932: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/yunohost_sso.conf.inc' to system conf '/etc/nginx/conf.d/yunohost_sso.conf.inc'
2023-03-30 21:22:46,932: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,933: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/default.d/redirect_to_admin.conf' to system conf '/etc/nginx/conf.d/default.d/redirect_to_admin.conf'
2023-03-30 21:22:46,933: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,934: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf' to system conf '/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf'
2023-03-30 21:22:46,934: DEBUG - > system conf is already removed
2023-03-30 21:22:46,934: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml' to system conf '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml'
2023-03-30 21:22:46,935: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:46,935: SUCCESS - Configuration updated for 'nginx'
2023-03-30 21:22:46,937: DEBUG - updating conf hashes for 'nginx' with: {'/etc/nginx/conf.d/acme-challenge.conf.inc': '6e532401262f7daf627c6482d6367f5d', '/etc/nginx/conf.d/default.d/redirect_to_admin.conf': '69b9d60d4f87f404e4d376458d9de4e1', '/etc/nginx/conf.d/global.conf': 'f8c8721f10d718546b2735080770d307', '/etc/nginx/conf.d/maindomain.tld.conf': '6dd12e595488c105e40ebcb3085f63aa', '/etc/nginx/conf.d/security.conf.inc': '2ceb56ca697e974c9021a47b7c415eb7', '/etc/nginx/conf.d/ssowat.conf': '88f0941db4a897c214f34a0661db890d', '/etc/nginx/conf.d/yunohost_admin.conf': '4f23bfc63fa5614e5b6997efcd83706c', '/etc/nginx/conf.d/yunohost_admin.conf.inc': 'e50af8d763f22816f75e6d2f5955f14c', '/etc/nginx/conf.d/yunohost_api.conf.inc': '71e89f68f5af5d83d161c54ade8d192f', '/etc/nginx/conf.d/yunohost_http_errors.conf.inc': '7bd05c30c115a0101d1fd37e66fca33d', '/etc/nginx/conf.d/yunohost_panel.conf.inc': '3de64e15d9874e6e17ab29cb6e48f188', '/etc/nginx/conf.d/yunohost_sso.conf.inc': '2230d8402c1167bea5db3f06f327e8fa', '/var/www/.well-known/maindomain.tld/autoconfig/mail/config-v1.1.xml': '5a6ed21fd8a9edbfb216ad9a00593dec', '/etc/nginx/sites-enabled/default': None, '/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf': None}
2023-03-30 21:22:46,995: DEBUG - Checking pending configuration which would have been applied for category 'postfix'...
2023-03-30 21:22:47,028: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-domains.cf' to system conf '/etc/postfix/ldap-domains.cf'
2023-03-30 21:22:47,029: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,029: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/header_checks' to system conf '/etc/postfix/header_checks'
2023-03-30 21:22:47,030: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,030: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sender_canonical' to system conf '/etc/postfix/sender_canonical'
2023-03-30 21:22:47,030: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,031: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-aliases.cf' to system conf '/etc/postfix/ldap-aliases.cf'
2023-03-30 21:22:47,031: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,032: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/master.cf' to system conf '/etc/postfix/master.cf'
2023-03-30 21:22:47,032: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,033: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/main.cf' to system conf '/etc/postfix/main.cf'
2023-03-30 21:22:47,033: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,034: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-accounts.cf' to system conf '/etc/postfix/ldap-accounts.cf'
2023-03-30 21:22:47,034: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,035: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/sni' to system conf '/etc/postfix/sni'
2023-03-30 21:22:47,035: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,035: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/smtp_reply_filter' to system conf '/etc/postfix/smtp_reply_filter'
2023-03-30 21:22:47,036: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,036: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/postfix/ldap-groups.cf' to system conf '/etc/postfix/ldap-groups.cf'
2023-03-30 21:22:47,037: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,037: DEBUG - processing pending conf '/var/cache/yunohost/regenconf/pending/postfix/etc/default/postsrsd' to system conf '/etc/default/postsrsd'
2023-03-30 21:22:47,038: DEBUG - > system conf is already up-to-date
2023-03-30 21:22:47,038: DEBUG - The configuration is already up-to-date for category 'postfix'
2023-03-30 21:22:47,040: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" post \'\' \'\' /etc/nginx/conf.d/maindomain.tld.conf 7>&1']'
2023-03-30 21:22:47,055: DEBUG - + set -e
2023-03-30 21:22:47,056: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 21:22:47,057: DEBUG - +++ set +o
2023-03-30 21:22:47,057: DEBUG - +++ grep xtrace
2023-03-30 21:22:47,060: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 21:22:47,060: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 21:22:47,099: DEBUG - + do_post_regen /etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 21:22:47,100: DEBUG - + regen_conf_files=/etc/nginx/conf.d/maindomain.tld.conf
2023-03-30 21:22:47,100: DEBUG - + '[' -z /etc/nginx/conf.d/maindomain.tld.conf ']'
2023-03-30 21:22:47,101: DEBUG - + for domain in $YNH_DOMAINS
2023-03-30 21:22:47,101: DEBUG - + mkdir -p /etc/nginx/conf.d/maindomain.tld.d
2023-03-30 21:22:47,102: DEBUG - + nginx -t
2023-03-30 21:22:47,503: DEBUG - + pgrep nginx
2023-03-30 21:22:47,528: DEBUG - 807
2023-03-30 21:22:47,528: DEBUG - 8400
2023-03-30 21:22:47,529: DEBUG - 8402
2023-03-30 21:22:47,530: DEBUG - 8403
2023-03-30 21:22:47,530: DEBUG - 8404
2023-03-30 21:22:47,530: DEBUG - + systemctl reload nginx
2023-03-30 21:22:48,533: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./19-postfix" post \'\' \'\' \'\' 7>&1']'
2023-03-30 21:22:48,549: DEBUG - + set -e
2023-03-30 21:22:48,550: DEBUG - + . /usr/share/yunohost/helpers
2023-03-30 21:22:48,551: DEBUG - +++ set +o
2023-03-30 21:22:48,551: DEBUG - +++ grep xtrace
2023-03-30 21:22:48,554: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-30 21:22:48,555: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-30 21:22:48,593: DEBUG - + do_post_regen
2023-03-30 21:22:48,593: DEBUG - + regen_conf_files=
2023-03-30 21:22:48,594: DEBUG - + chown postfix /etc/postfix
2023-03-30 21:22:48,596: DEBUG - + '[' -e /etc/postfix/sasl_passwd ']'
2023-03-30 21:22:48,596: DEBUG - + postmap -F hash:/etc/postfix/sni
2023-03-30 21:22:48,629: DEBUG - + [[ -z '' ]]
2023-03-30 21:22:49,632: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-202234-regen_conf-2_categories" style="text-decoration:underline">Regenerate system configurations '2_categories'</a>'
2023-03-30 21:22:49,828: DEBUG - Running 'systemctl reload nginx'
2023-03-30 21:22:49,966: SUCCESS - Let's Encrypt certificate now installed for the domain 'maindomain.tld'
```

### create user account kirkrehn

```sh
args:
  domain: maindomain.tld
  firstname: null
  fullname: Kirk Rehn
  lastname: null
  loginShell: /bin/bash
  mailbox_quota: '0'
  username: kirkrehn
ended_at: 2023-03-30 20:23:46.214604
error: null
interface: api
operation: user_create
parent: null
related_to:
- - user
  - kirkrehn
started_at: 2023-03-30 20:23:44.865567
success: true
yunohost_version: 11.1.15

============

2023-03-30 21:23:45,034: DEBUG - Group 'kirkrehn' created
2023-03-30 21:23:45,035: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-202344-user_group_create-kirkrehn" style="text-decoration:underline">Create 'kirkrehn' group</a>'
2023-03-30 21:23:45,114: DEBUG - The permission database has been resynchronized
2023-03-30 21:23:45,153: DEBUG - SSOwat configuration regenerated
2023-03-30 21:23:45,166: DEBUG - Group 'all_users' updated
2023-03-30 21:23:45,168: DEBUG - Full log of this operation: '<a href="#/tools/logs/20230330-202345-user_group_update-all_users" style="text-decoration:underline">Update 'all_users' group</a>'
2023-03-30 21:23:45,188: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./ynh_multimedia" kirkrehn kirkrehn@maindomain.tld 7>&1']'
2023-03-30 21:23:45,208: DEBUG - + user=kirkrehn
2023-03-30 21:23:45,209: DEBUG - + readonly MEDIA_GROUP=multimedia
2023-03-30 21:23:45,209: DEBUG - + MEDIA_GROUP=multimedia
2023-03-30 21:23:45,209: DEBUG - + readonly MEDIA_DIRECTORY=/home/yunohost.multimedia
2023-03-30 21:23:45,210: DEBUG - + MEDIA_DIRECTORY=/home/yunohost.multimedia
2023-03-30 21:23:45,210: DEBUG - + '[' -e /home/yunohost.multimedia ']'
2023-03-30 21:23:46,212: SUCCESS - User created
```

### update e-mail forward to

```sh
args:
  add_mailalias: null
  add_mailforward:
  - kirk@kirkrehn.online
  firstname: null
  fullname: null
  lastname: null
  loginShell: /bin/bash
  mail: null
  mailbox_quota: '0'
  remove_mailalias: null
  remove_mailforward: null
  username: kirkrehn
ended_at: 2023-03-30 20:24:26.734821
error: null
interface: api
operation: user_update
parent: null
related_to:
- - user
  - kirkrehn
started_at: 2023-03-30 20:24:26.338882
success: true
yunohost_version: 11.1.15

============

2023-03-30 21:24:26,475: DEBUG - SSOwat configuration regenerated
2023-03-30 21:24:26,476: SUCCESS - User info changed
```
### security settings
- ssh compatibility: modern
- ssh port: 22
	- password auth: yes
- nginx for https: yes
	- nginx compatibility: modern
- postfix compatibility: modern
- experimental security features: no