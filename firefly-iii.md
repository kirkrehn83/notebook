---
share: true
---
> [!NOTE] synopsis
> self hosted personal finance software

## faq
---
| **item** | **description** |
| --- | --- |
| url | firefly.kirkehn.online |
| root user | |
| root password | |

## logs
---
### install logs

```sh

```

### subdomain registration

```sh
args:
  domain: firefly.maindomain.tld
  dyndns: false
ended_at: 2023-03-29 04:58:01.242276
error: null
interface: api
operation: domain_add
parent: null
related_to:
- - domain
  - firefly.maindomain.tld
started_at: 2023-03-29 04:56:41.465040
success: true
yunohost_version: 11.1.15

============

2023-03-28 21:56:41,592: DEBUG - Generating a RSA private key
.+++++
...........+++++
writing new private key to '/etc/yunohost/certs//firefly.maindomain.tld-history/20230329.045641-selfsigned/key.pem'
-----

2023-03-28 21:56:41,653: DEBUG - Using configuration from /etc/yunohost/certs//firefly.maindomain.tld-history/20230329.045641-selfsigned/openssl.cnf
Check that the request matches the signature
Signature ok
Certificate Details:
        Serial Number:
            f8:9d:71:ed:54:f3:aa:18:f1:d4:e9:2b:b3:15:1c:73:35:37:d1
        Validity
            Not Before: Mar 29 04:56:41 2023 GMT
            Not After : Mar 26 04:56:41 2033 GMT
        Subject:
            commonName                = firefly.maindomain.tld
        X509v3 extensions:
            X509v3 Basic Constraints: 
                CA:FALSE
            Netscape Comment: 
                OpenSSL Generated Certificate
            X509v3 Subject Key Identifier: 
                79:CE:8E:32:16:CC:39:39:0E:7F:89:4F:FF:06:93:BB:2E:72:C9:EC
            X509v3 Authority Key Identifier: 
                keyid:C2:BF:53:08:D0:4A:24:59:99:2B:19:8D:75:43:1F:4D:B4:F1:3D:D2

            X509v3 Key Usage: 
                Digital Signature, Non Repudiation, Key Encipherment
            X509v3 Subject Alternative Name: 
                DNS:firefly.maindomain.tld, DNS:www.firefly.maindomain.tld, DNS:ns.firefly.maindomain.tld, DNS:xmpp-upload.firefly.maindomain.tld
Certificate is to be certified until Mar 26 04:56:41 2033 GMT (3650 days)

Write out database with 1 new entries
Data Base Updated

2023-03-28 21:56:41,656: DEBUG - Enabling the certificate for domain firefly.maindomain.tld ...
2023-03-28 21:56:41,656: DEBUG - Restarting services...
2023-03-28 21:56:41,889: DEBUG - Running 'systemctl restart dovecot'
2023-03-28 21:56:43,412: DEBUG - Executing command '['sh', '-c', '/bin/bash -x "./15-nginx" pre \'\' \'\' /var/cache/yunohost/regenconf/pending/nginx 7>&1']'
2023-03-28 21:56:43,428: DEBUG - + set -e
2023-03-28 21:56:43,430: DEBUG - + . /usr/share/yunohost/helpers
2023-03-28 21:56:43,431: DEBUG - +++ set +o
2023-03-28 21:56:43,432: DEBUG - +++ grep xtrace
2023-03-28 21:56:43,436: DEBUG - ++ readonly 'XTRACE_ENABLE=set -o xtrace'
2023-03-28 21:56:43,436: DEBUG - ++ XTRACE_ENABLE='set -o xtrace'
2023-03-28 21:56:43,477: DEBUG - + do_pre_regen /var/cache/yunohost/regenconf/pending/nginx
2023-03-28 21:56:43,478: DEBUG - + pending_dir=/var/cache/yunohost/regenconf/pending/nginx
2023-03-28 21:56:43,479: DEBUG - + cd /usr/share/yunohost/conf/nginx
2023-03-28 21:56:43,479: DEBUG - + nginx_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx
2023-03-28 21:56:43,480: DEBUG - + nginx_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:43,480: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:43,482: DEBUG - + cp plain/acme-challenge.conf.inc plain/global.conf plain/ssowat.conf plain/yunohost_http_errors.conf.inc plain/yunohost_panel.conf.inc plain/yunohost_sso.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:43,488: DEBUG - ++ yunohost settings get misc.portal.ssowat_panel_overlay_enabled
2023-03-28 21:56:43,489: DEBUG - ++ int_to_bool
2023-03-28 21:56:43,490: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-28 21:56:44,152: DEBUG - + panel_overlay=True
2023-03-28 21:56:44,153: DEBUG - + '[' True == False ']'
2023-03-28 21:56:44,154: DEBUG - ++ cat /etc/yunohost/current_host
2023-03-28 21:56:44,156: DEBUG - + main_domain=maindomain.tld
2023-03-28 21:56:44,158: DEBUG - ++ yunohost settings get security.nginx.nginx_redirect_to_https
2023-03-28 21:56:44,158: DEBUG - ++ int_to_bool
2023-03-28 21:56:44,159: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-28 21:56:44,872: DEBUG - + export redirect_to_https=True
2023-03-28 21:56:44,873: DEBUG - + redirect_to_https=True
2023-03-28 21:56:44,874: DEBUG - ++ yunohost settings get security.nginx.nginx_compatibility
2023-03-28 21:56:45,537: DEBUG - + export compatibility=intermediate
2023-03-28 21:56:45,538: DEBUG - + compatibility=intermediate
2023-03-28 21:56:45,539: DEBUG - ++ yunohost settings get security.experimental.security_experimental_enabled
2023-03-28 21:56:45,540: DEBUG - ++ int_to_bool
2023-03-28 21:56:45,541: DEBUG - ++ sed -e 's/^1$/True/g' -e 's/^0$/False/g'
2023-03-28 21:56:46,200: DEBUG - + export experimental=False
2023-03-28 21:56:46,201: DEBUG - + experimental=False
2023-03-28 21:56:46,202: DEBUG - + ynh_render_template security.conf.inc /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-28 21:56:46,203: DEBUG - + local template_path=security.conf.inc
2023-03-28 21:56:46,203: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-28 21:56:46,204: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/security.conf.inc
2023-03-28 21:56:46,205: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:46,208: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:46,209: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:46,209: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:46,401: DEBUG - ++ yunohost domain cert status --json
2023-03-28 21:56:47,212: DEBUG - + cert_status='{"certificates": {"maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "energy.maindomain.tld": {"CA_type": "letsencrypt", "validity": 85, "style": "success", "summary": "letsencrypt"}, "home.maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "homeassistant.maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "nextcloud.maindomain.tld": {"CA_type": "letsencrypt", "validity": 85, "style": "success", "summary": "letsencrypt"}, "webmail.maindomain.tld": {"CA_type": "letsencrypt", "validity": 85, "style": "success", "summary": "letsencrypt"}, "wikijs.maindomain.tld": {"CA_type": "letsencrypt", "validity": 89, "style": "success", "summary": "letsencrypt"}, "domain2.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "energy.domain2.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "grocy.domain2.tld": {"CA_type": "letsencrypt", "validity": 59, "style": "success", "summary": "letsencrypt"}, "home.domain2.tld": {"CA_type": "letsencrypt", "validity": 55, "style": "success", "summary": "letsencrypt"}, "homeassistant.domain2.tld": {"CA_type": "letsencrypt", "validity": 55, "style": "success", "summary": "letsencrypt"}, "mqtt.domain2.tld": {"CA_type": "letsencrypt", "validity": 55, "style": "success", "summary": "letsencrypt"}, "nextcloud.domain2.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "nodered.domain2.tld": {"CA_type": "letsencrypt", "validity": 77, "style": "success", "summary": "letsencrypt"}, "owntracks.domain2.tld": {"CA_type": "letsencrypt", "validity": 54, "style": "success", "summary": "letsencrypt"}, "webmail.domain2.tld": {"CA_type": "letsencrypt", "validity": 87, "style": "success", "summary": "letsencrypt"}, "wikijs.domain2.tld": {"CA_type": "letsencrypt", "validity": 86, "style": "success", "summary": "letsencrypt"}, "domain3.tld": {"CA_type": "selfsigned", "validity": 3649, "style": "warning", "summary": "selfsigned"}}}'
2023-03-28 21:56:47,214: DEBUG - ++ yunohost domain list --features xmpp --output-as json
2023-03-28 21:56:47,215: DEBUG - ++ jq -r '.domains[]'
2023-03-28 21:56:48,027: DEBUG - + xmpp_domain_list=
2023-03-28 21:56:48,029: DEBUG - ++ yunohost domain list --features mail_in mail_out --output-as json
2023-03-28 21:56:48,030: DEBUG - ++ jq -r '.domains[]'
2023-03-28 21:56:48,861: DEBUG - + mail_domain_list='maindomain.tld
2023-03-28 21:56:48,862: DEBUG - energy.maindomain.tld
2023-03-28 21:56:48,862: DEBUG - home.maindomain.tld
2023-03-28 21:56:48,863: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:48,863: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:48,864: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:48,864: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:48,865: DEBUG - domain2.tld
2023-03-28 21:56:48,865: DEBUG - energy.domain2.tld
2023-03-28 21:56:48,866: DEBUG - grocy.domain2.tld
2023-03-28 21:56:48,866: DEBUG - home.domain2.tld
2023-03-28 21:56:48,867: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:48,867: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:48,868: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:48,868: DEBUG - nodered.domain2.tld
2023-03-28 21:56:48,869: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:48,869: DEBUG - webmail.domain2.tld
2023-03-28 21:56:48,870: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:48,870: DEBUG - domain3.tld'
2023-03-28 21:56:48,871: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:48,872: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-28 21:56:48,873: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d
2023-03-28 21:56:48,874: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-28 21:56:48,874: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail/
2023-03-28 21:56:48,875: DEBUG - + export domain
2023-03-28 21:56:48,876: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:48,878: DEBUG - ++ jq '.certificates."maindomain.tld".CA_type'
2023-03-28 21:56:48,879: DEBUG - ++ tr -d '"'
2023-03-28 21:56:48,962: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:48,963: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:48,964: DEBUG - + grep -q '^maindomain.tld$'
2023-03-28 21:56:48,967: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:48,968: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:48,970: DEBUG - energy.maindomain.tld
2023-03-28 21:56:48,970: DEBUG - home.maindomain.tld
2023-03-28 21:56:48,971: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:48,971: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:48,972: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:48,972: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:48,973: DEBUG - domain2.tld
2023-03-28 21:56:48,973: DEBUG - energy.domain2.tld
2023-03-28 21:56:48,974: DEBUG - grocy.domain2.tld
2023-03-28 21:56:48,974: DEBUG - home.domain2.tld
2023-03-28 21:56:48,975: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:48,976: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:48,976: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:48,976: DEBUG - nodered.domain2.tld
2023-03-28 21:56:48,977: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:48,977: DEBUG - webmail.domain2.tld
2023-03-28 21:56:48,978: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:48,979: DEBUG - domain3.tld'
2023-03-28 21:56:48,979: DEBUG - + grep -q '^maindomain.tld$'
2023-03-28 21:56:48,980: DEBUG - + export mail_enabled=True
2023-03-28 21:56:48,980: DEBUG - + mail_enabled=True
2023-03-28 21:56:48,980: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-28 21:56:48,981: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:48,982: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-28 21:56:48,982: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.conf
2023-03-28 21:56:48,983: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:48,983: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:48,984: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:48,984: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:49,188: DEBUG - + '[' True == True ']'
2023-03-28 21:56:49,189: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:49,190: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:49,190: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:49,191: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:49,192: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/maindomain.tld/autoconfig/mail
2023-03-28 21:56:49,196: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:49,196: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:49,197: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:49,416: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:49,418: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:49,419: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d
2023-03-28 21:56:49,420: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d
2023-03-28 21:56:49,422: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:49,423: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:49,426: DEBUG - + export domain
2023-03-28 21:56:49,428: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:49,431: DEBUG - ++ jq '.certificates."energy.maindomain.tld".CA_type'
2023-03-28 21:56:49,432: DEBUG - ++ tr -d '"'
2023-03-28 21:56:49,515: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:49,516: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:49,518: DEBUG - + grep -q '^energy.maindomain.tld$'
2023-03-28 21:56:49,521: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:49,523: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:49,523: DEBUG - energy.maindomain.tld
2023-03-28 21:56:49,524: DEBUG - home.maindomain.tld
2023-03-28 21:56:49,524: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:49,525: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:49,525: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:49,526: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:49,527: DEBUG - domain2.tld
2023-03-28 21:56:49,527: DEBUG - energy.domain2.tld
2023-03-28 21:56:49,528: DEBUG - grocy.domain2.tld
2023-03-28 21:56:49,528: DEBUG - home.domain2.tld
2023-03-28 21:56:49,529: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:49,529: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:49,530: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:49,530: DEBUG - nodered.domain2.tld
2023-03-28 21:56:49,531: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:49,531: DEBUG - webmail.domain2.tld
2023-03-28 21:56:49,532: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:49,532: DEBUG - domain3.tld'
2023-03-28 21:56:49,533: DEBUG - + grep -q '^energy.maindomain.tld$'
2023-03-28 21:56:49,533: DEBUG - + export mail_enabled=True
2023-03-28 21:56:49,534: DEBUG - + mail_enabled=True
2023-03-28 21:56:49,534: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-03-28 21:56:49,535: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:49,535: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-03-28 21:56:49,536: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.conf
2023-03-28 21:56:49,536: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:49,537: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:49,537: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:49,538: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:49,742: DEBUG - + '[' True == True ']'
2023-03-28 21:56:49,743: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:49,744: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:49,744: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:49,745: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:49,746: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.maindomain.tld/autoconfig/mail
2023-03-28 21:56:49,750: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:49,751: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:49,751: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:49,935: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:49,937: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:49,938: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d
2023-03-28 21:56:49,939: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d
2023-03-28 21:56:49,942: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:49,942: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:49,946: DEBUG - + export domain
2023-03-28 21:56:49,948: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:49,951: DEBUG - ++ jq '.certificates."home.maindomain.tld".CA_type'
2023-03-28 21:56:49,952: DEBUG - ++ tr -d '"'
2023-03-28 21:56:50,039: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:50,040: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:50,041: DEBUG - + grep -q '^home.maindomain.tld$'
2023-03-28 21:56:50,045: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:50,045: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:50,046: DEBUG - energy.maindomain.tld
2023-03-28 21:56:50,047: DEBUG - home.maindomain.tld
2023-03-28 21:56:50,047: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:50,048: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:50,050: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:50,050: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:50,051: DEBUG - domain2.tld
2023-03-28 21:56:50,051: DEBUG - energy.domain2.tld
2023-03-28 21:56:50,052: DEBUG - grocy.domain2.tld
2023-03-28 21:56:50,052: DEBUG - home.domain2.tld
2023-03-28 21:56:50,053: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:50,053: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:50,054: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:50,055: DEBUG - nodered.domain2.tld
2023-03-28 21:56:50,055: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:50,056: DEBUG - webmail.domain2.tld
2023-03-28 21:56:50,056: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:50,057: DEBUG - domain3.tld'
2023-03-28 21:56:50,057: DEBUG - + grep -q '^home.maindomain.tld$'
2023-03-28 21:56:50,058: DEBUG - + export mail_enabled=True
2023-03-28 21:56:50,058: DEBUG - + mail_enabled=True
2023-03-28 21:56:50,059: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-03-28 21:56:50,059: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:50,060: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-03-28 21:56:50,060: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.conf
2023-03-28 21:56:50,061: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:50,061: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:50,062: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:50,062: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:50,261: DEBUG - + '[' True == True ']'
2023-03-28 21:56:50,262: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:50,262: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:50,263: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:50,263: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:50,265: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.maindomain.tld/autoconfig/mail
2023-03-28 21:56:50,268: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:50,269: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:50,270: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:50,461: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:50,464: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:50,465: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d
2023-03-28 21:56:50,466: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d
2023-03-28 21:56:50,468: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:50,469: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:50,472: DEBUG - + export domain
2023-03-28 21:56:50,475: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:50,478: DEBUG - ++ jq '.certificates."homeassistant.maindomain.tld".CA_type'
2023-03-28 21:56:50,479: DEBUG - ++ tr -d '"'
2023-03-28 21:56:50,569: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:50,571: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:50,572: DEBUG - + grep -q '^homeassistant.maindomain.tld$'
2023-03-28 21:56:50,575: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:50,576: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:50,578: DEBUG - energy.maindomain.tld
2023-03-28 21:56:50,578: DEBUG - home.maindomain.tld
2023-03-28 21:56:50,579: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:50,579: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:50,580: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:50,580: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:50,581: DEBUG - domain2.tld
2023-03-28 21:56:50,581: DEBUG - energy.domain2.tld
2023-03-28 21:56:50,582: DEBUG - grocy.domain2.tld
2023-03-28 21:56:50,582: DEBUG - home.domain2.tld
2023-03-28 21:56:50,583: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:50,583: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:50,584: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:50,584: DEBUG - nodered.domain2.tld
2023-03-28 21:56:50,585: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:50,585: DEBUG - webmail.domain2.tld
2023-03-28 21:56:50,586: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:50,586: DEBUG - domain3.tld'
2023-03-28 21:56:50,587: DEBUG - + grep -q '^homeassistant.maindomain.tld$'
2023-03-28 21:56:50,587: DEBUG - + export mail_enabled=True
2023-03-28 21:56:50,588: DEBUG - + mail_enabled=True
2023-03-28 21:56:50,588: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-03-28 21:56:50,589: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:50,589: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-03-28 21:56:50,590: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.conf
2023-03-28 21:56:50,591: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:50,591: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:50,591: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:50,592: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:50,793: DEBUG - + '[' True == True ']'
2023-03-28 21:56:50,794: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:50,795: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:50,795: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:50,796: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:50,797: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.maindomain.tld/autoconfig/mail
2023-03-28 21:56:50,801: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:50,802: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:50,803: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:50,989: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:50,991: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:50,992: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d
2023-03-28 21:56:50,993: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d
2023-03-28 21:56:50,996: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:50,997: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:51,000: DEBUG - + export domain
2023-03-28 21:56:51,002: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:51,005: DEBUG - ++ jq '.certificates."nextcloud.maindomain.tld".CA_type'
2023-03-28 21:56:51,006: DEBUG - ++ tr -d '"'
2023-03-28 21:56:51,097: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:51,098: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:51,099: DEBUG - + grep -q '^nextcloud.maindomain.tld$'
2023-03-28 21:56:51,101: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:51,102: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:51,104: DEBUG - energy.maindomain.tld
2023-03-28 21:56:51,104: DEBUG - home.maindomain.tld
2023-03-28 21:56:51,105: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:51,105: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:51,106: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:51,106: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:51,107: DEBUG - domain2.tld
2023-03-28 21:56:51,107: DEBUG - energy.domain2.tld
2023-03-28 21:56:51,108: DEBUG - grocy.domain2.tld
2023-03-28 21:56:51,108: DEBUG - home.domain2.tld
2023-03-28 21:56:51,109: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:51,109: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:51,110: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:51,110: DEBUG - nodered.domain2.tld
2023-03-28 21:56:51,111: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:51,111: DEBUG - webmail.domain2.tld
2023-03-28 21:56:51,112: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:51,113: DEBUG - domain3.tld'
2023-03-28 21:56:51,113: DEBUG - + grep -q '^nextcloud.maindomain.tld$'
2023-03-28 21:56:51,114: DEBUG - + export mail_enabled=True
2023-03-28 21:56:51,114: DEBUG - + mail_enabled=True
2023-03-28 21:56:51,115: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-03-28 21:56:51,115: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:51,116: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-03-28 21:56:51,117: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.conf
2023-03-28 21:56:51,117: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:51,118: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:51,118: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:51,119: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:51,318: DEBUG - + '[' True == True ']'
2023-03-28 21:56:51,319: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:51,320: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:51,320: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:51,321: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:51,323: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.maindomain.tld/autoconfig/mail
2023-03-28 21:56:51,326: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:51,327: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:51,328: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:51,513: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:51,516: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:51,516: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d
2023-03-28 21:56:51,517: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d
2023-03-28 21:56:51,520: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:51,521: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:51,524: DEBUG - + export domain
2023-03-28 21:56:51,527: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:51,530: DEBUG - ++ jq '.certificates."webmail.maindomain.tld".CA_type'
2023-03-28 21:56:51,530: DEBUG - ++ tr -d '"'
2023-03-28 21:56:51,611: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:51,612: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:51,613: DEBUG - + grep -q '^webmail.maindomain.tld$'
2023-03-28 21:56:51,617: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:51,618: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:51,619: DEBUG - energy.maindomain.tld
2023-03-28 21:56:51,619: DEBUG - home.maindomain.tld
2023-03-28 21:56:51,620: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:51,620: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:51,622: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:51,622: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:51,623: DEBUG - domain2.tld
2023-03-28 21:56:51,623: DEBUG - energy.domain2.tld
2023-03-28 21:56:51,624: DEBUG - grocy.domain2.tld
2023-03-28 21:56:51,624: DEBUG - home.domain2.tld
2023-03-28 21:56:51,625: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:51,625: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:51,626: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:51,626: DEBUG - nodered.domain2.tld
2023-03-28 21:56:51,627: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:51,627: DEBUG - webmail.domain2.tld
2023-03-28 21:56:51,628: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:51,628: DEBUG - domain3.tld'
2023-03-28 21:56:51,629: DEBUG - + grep -q '^webmail.maindomain.tld$'
2023-03-28 21:56:51,630: DEBUG - + export mail_enabled=True
2023-03-28 21:56:51,630: DEBUG - + mail_enabled=True
2023-03-28 21:56:51,630: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf
2023-03-28 21:56:51,631: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:51,631: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf
2023-03-28 21:56:51,632: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.conf
2023-03-28 21:56:51,632: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:51,633: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:51,634: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:51,634: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:51,834: DEBUG - + '[' True == True ']'
2023-03-28 21:56:51,835: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:51,836: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:51,836: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:51,837: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:51,838: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/webmail.maindomain.tld/autoconfig/mail
2023-03-28 21:56:51,842: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:51,843: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:51,843: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:52,035: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/webmail.maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:52,038: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:52,039: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d
2023-03-28 21:56:52,039: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d
2023-03-28 21:56:52,042: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:52,043: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail/
2023-03-28 21:56:52,046: DEBUG - + export domain
2023-03-28 21:56:52,049: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:52,051: DEBUG - ++ jq '.certificates."wikijs.maindomain.tld".CA_type'
2023-03-28 21:56:52,052: DEBUG - ++ tr -d '"'
2023-03-28 21:56:52,132: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:52,133: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:52,134: DEBUG - + grep -q '^wikijs.maindomain.tld$'
2023-03-28 21:56:52,137: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:52,138: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:52,139: DEBUG - energy.maindomain.tld
2023-03-28 21:56:52,140: DEBUG - home.maindomain.tld
2023-03-28 21:56:52,140: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:52,140: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:52,141: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:52,141: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:52,142: DEBUG - domain2.tld
2023-03-28 21:56:52,143: DEBUG - energy.domain2.tld
2023-03-28 21:56:52,143: DEBUG - grocy.domain2.tld
2023-03-28 21:56:52,144: DEBUG - home.domain2.tld
2023-03-28 21:56:52,144: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:52,145: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:52,145: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:52,146: DEBUG - nodered.domain2.tld
2023-03-28 21:56:52,146: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:52,147: DEBUG - webmail.domain2.tld
2023-03-28 21:56:52,147: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:52,148: DEBUG - domain3.tld'
2023-03-28 21:56:52,148: DEBUG - + grep -q '^wikijs.maindomain.tld$'
2023-03-28 21:56:52,149: DEBUG - + export mail_enabled=True
2023-03-28 21:56:52,149: DEBUG - + mail_enabled=True
2023-03-28 21:56:52,150: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-03-28 21:56:52,150: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:52,151: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-03-28 21:56:52,151: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.conf
2023-03-28 21:56:52,152: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:52,152: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:52,153: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:52,153: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:52,351: DEBUG - + '[' True == True ']'
2023-03-28 21:56:52,352: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:52,353: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:52,353: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:52,354: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:52,355: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/wikijs.maindomain.tld/autoconfig/mail
2023-03-28 21:56:52,359: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:52,360: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:52,360: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:52,549: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/wikijs.maindomain.tld.d/yunohost_local.conf
2023-03-28 21:56:52,551: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:52,552: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d
2023-03-28 21:56:52,553: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d
2023-03-28 21:56:52,555: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail/
2023-03-28 21:56:52,556: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail/
2023-03-28 21:56:52,559: DEBUG - + export domain
2023-03-28 21:56:52,562: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:52,565: DEBUG - ++ jq '.certificates."domain2.tld".CA_type'
2023-03-28 21:56:52,566: DEBUG - ++ tr -d '"'
2023-03-28 21:56:52,644: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:52,645: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:52,646: DEBUG - + grep -q '^domain2.tld$'
2023-03-28 21:56:52,649: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:52,650: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:52,651: DEBUG - energy.maindomain.tld
2023-03-28 21:56:52,652: DEBUG - home.maindomain.tld
2023-03-28 21:56:52,652: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:52,653: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:52,654: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:52,655: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:52,656: DEBUG - domain2.tld
2023-03-28 21:56:52,656: DEBUG - energy.domain2.tld
2023-03-28 21:56:52,657: DEBUG - grocy.domain2.tld
2023-03-28 21:56:52,657: DEBUG - home.domain2.tld
2023-03-28 21:56:52,658: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:52,659: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:52,659: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:52,660: DEBUG - nodered.domain2.tld
2023-03-28 21:56:52,660: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:52,661: DEBUG - webmail.domain2.tld
2023-03-28 21:56:52,661: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:52,662: DEBUG - domain3.tld'
2023-03-28 21:56:52,662: DEBUG - + grep -q '^domain2.tld$'
2023-03-28 21:56:52,663: DEBUG - + export mail_enabled=True
2023-03-28 21:56:52,663: DEBUG - + mail_enabled=True
2023-03-28 21:56:52,664: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-03-28 21:56:52,664: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:52,665: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-03-28 21:56:52,665: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.conf
2023-03-28 21:56:52,666: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:52,667: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:52,667: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:52,668: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:52,866: DEBUG - + '[' True == True ']'
2023-03-28 21:56:52,867: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:52,868: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:52,868: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:52,869: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:52,870: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/domain2.tld/autoconfig/mail
2023-03-28 21:56:52,873: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:52,874: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:52,874: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:53,062: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:53,065: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:53,066: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d
2023-03-28 21:56:53,067: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d
2023-03-28 21:56:53,069: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail/
2023-03-28 21:56:53,070: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail/
2023-03-28 21:56:53,073: DEBUG - + export domain
2023-03-28 21:56:53,076: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:53,079: DEBUG - ++ jq '.certificates."energy.domain2.tld".CA_type'
2023-03-28 21:56:53,079: DEBUG - ++ tr -d '"'
2023-03-28 21:56:53,161: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:53,162: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:53,163: DEBUG - + grep -q '^energy.domain2.tld$'
2023-03-28 21:56:53,165: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:53,167: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:53,168: DEBUG - energy.maindomain.tld
2023-03-28 21:56:53,168: DEBUG - home.maindomain.tld
2023-03-28 21:56:53,169: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:53,169: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:53,170: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:53,170: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:53,171: DEBUG - domain2.tld
2023-03-28 21:56:53,171: DEBUG - energy.domain2.tld
2023-03-28 21:56:53,172: DEBUG - grocy.domain2.tld
2023-03-28 21:56:53,172: DEBUG - home.domain2.tld
2023-03-28 21:56:53,173: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:53,173: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:53,174: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:53,174: DEBUG - nodered.domain2.tld
2023-03-28 21:56:53,175: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:53,175: DEBUG - webmail.domain2.tld
2023-03-28 21:56:53,176: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:53,176: DEBUG - domain3.tld'
2023-03-28 21:56:53,177: DEBUG - + grep -q '^energy.domain2.tld$'
2023-03-28 21:56:53,178: DEBUG - + export mail_enabled=True
2023-03-28 21:56:53,178: DEBUG - + mail_enabled=True
2023-03-28 21:56:53,179: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf
2023-03-28 21:56:53,180: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:53,180: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf
2023-03-28 21:56:53,181: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.conf
2023-03-28 21:56:53,181: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:53,182: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:53,182: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:53,183: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:53,381: DEBUG - + '[' True == True ']'
2023-03-28 21:56:53,382: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:53,382: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:53,383: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:53,383: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:53,385: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/energy.domain2.tld/autoconfig/mail
2023-03-28 21:56:53,388: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:53,389: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:53,390: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:53,572: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/energy.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:53,575: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:53,575: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.domain2.tld.d
2023-03-28 21:56:53,576: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.domain2.tld.d
2023-03-28 21:56:53,579: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.domain2.tld/autoconfig/mail/
2023-03-28 21:56:53,580: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.domain2.tld/autoconfig/mail/
2023-03-28 21:56:53,583: DEBUG - + export domain
2023-03-28 21:56:53,585: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:53,588: DEBUG - ++ jq '.certificates."grocy.domain2.tld".CA_type'
2023-03-28 21:56:53,589: DEBUG - ++ tr -d '"'
2023-03-28 21:56:53,672: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:53,673: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:53,674: DEBUG - + grep -q '^grocy.domain2.tld$'
2023-03-28 21:56:53,677: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:53,678: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:53,679: DEBUG - energy.maindomain.tld
2023-03-28 21:56:53,680: DEBUG - home.maindomain.tld
2023-03-28 21:56:53,680: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:53,681: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:53,681: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:53,682: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:53,682: DEBUG - domain2.tld
2023-03-28 21:56:53,683: DEBUG - energy.domain2.tld
2023-03-28 21:56:53,683: DEBUG - grocy.domain2.tld
2023-03-28 21:56:53,684: DEBUG - home.domain2.tld
2023-03-28 21:56:53,685: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:53,685: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:53,686: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:53,686: DEBUG - nodered.domain2.tld
2023-03-28 21:56:53,687: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:53,687: DEBUG - webmail.domain2.tld
2023-03-28 21:56:53,688: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:53,688: DEBUG - domain3.tld'
2023-03-28 21:56:53,689: DEBUG - + grep -q '^grocy.domain2.tld$'
2023-03-28 21:56:53,689: DEBUG - + export mail_enabled=True
2023-03-28 21:56:53,690: DEBUG - + mail_enabled=True
2023-03-28 21:56:53,690: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.domain2.tld.conf
2023-03-28 21:56:53,691: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:53,691: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.domain2.tld.conf
2023-03-28 21:56:53,692: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.domain2.tld.conf
2023-03-28 21:56:53,693: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:53,693: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:53,694: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:53,694: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:53,895: DEBUG - + '[' True == True ']'
2023-03-28 21:56:53,896: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:53,896: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:53,897: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:53,897: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:53,899: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/grocy.domain2.tld/autoconfig/mail
2023-03-28 21:56:53,902: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:53,903: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:53,904: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:54,086: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/grocy.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:54,089: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:54,090: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d
2023-03-28 21:56:54,091: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d
2023-03-28 21:56:54,094: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail/
2023-03-28 21:56:54,094: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail/
2023-03-28 21:56:54,097: DEBUG - + export domain
2023-03-28 21:56:54,100: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:54,103: DEBUG - ++ jq '.certificates."home.domain2.tld".CA_type'
2023-03-28 21:56:54,103: DEBUG - ++ tr -d '"'
2023-03-28 21:56:54,183: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:54,184: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:54,186: DEBUG - + grep -q '^home.domain2.tld$'
2023-03-28 21:56:54,189: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:54,190: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:54,191: DEBUG - energy.maindomain.tld
2023-03-28 21:56:54,192: DEBUG - home.maindomain.tld
2023-03-28 21:56:54,192: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:54,193: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:54,193: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:54,194: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:54,194: DEBUG - domain2.tld
2023-03-28 21:56:54,195: DEBUG - energy.domain2.tld
2023-03-28 21:56:54,195: DEBUG - grocy.domain2.tld
2023-03-28 21:56:54,196: DEBUG - home.domain2.tld
2023-03-28 21:56:54,196: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:54,197: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:54,197: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:54,198: DEBUG - nodered.domain2.tld
2023-03-28 21:56:54,198: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:54,199: DEBUG - webmail.domain2.tld
2023-03-28 21:56:54,199: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:54,200: DEBUG - domain3.tld'
2023-03-28 21:56:54,200: DEBUG - + grep -q '^home.domain2.tld$'
2023-03-28 21:56:54,201: DEBUG - + export mail_enabled=True
2023-03-28 21:56:54,201: DEBUG - + mail_enabled=True
2023-03-28 21:56:54,202: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf
2023-03-28 21:56:54,203: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:54,203: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf
2023-03-28 21:56:54,204: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.conf
2023-03-28 21:56:54,204: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:54,205: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:54,205: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:54,206: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:54,422: DEBUG - + '[' True == True ']'
2023-03-28 21:56:54,423: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:54,424: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:54,425: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:54,426: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:54,428: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/home.domain2.tld/autoconfig/mail
2023-03-28 21:56:54,434: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:54,435: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:54,435: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:54,632: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/home.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:54,635: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:54,636: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d
2023-03-28 21:56:54,637: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d
2023-03-28 21:56:54,639: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/
2023-03-28 21:56:54,640: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail/
2023-03-28 21:56:54,643: DEBUG - + export domain
2023-03-28 21:56:54,645: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:54,648: DEBUG - ++ jq '.certificates."homeassistant.domain2.tld".CA_type'
2023-03-28 21:56:54,649: DEBUG - ++ tr -d '"'
2023-03-28 21:56:54,733: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:54,734: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:54,735: DEBUG - + grep -q '^homeassistant.domain2.tld$'
2023-03-28 21:56:54,738: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:54,739: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:54,740: DEBUG - energy.maindomain.tld
2023-03-28 21:56:54,741: DEBUG - home.maindomain.tld
2023-03-28 21:56:54,741: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:54,742: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:54,742: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:54,743: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:54,743: DEBUG - domain2.tld
2023-03-28 21:56:54,744: DEBUG - energy.domain2.tld
2023-03-28 21:56:54,745: DEBUG - grocy.domain2.tld
2023-03-28 21:56:54,745: DEBUG - home.domain2.tld
2023-03-28 21:56:54,746: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:54,746: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:54,747: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:54,747: DEBUG - nodered.domain2.tld
2023-03-28 21:56:54,748: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:54,748: DEBUG - webmail.domain2.tld
2023-03-28 21:56:54,749: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:54,749: DEBUG - domain3.tld'
2023-03-28 21:56:54,750: DEBUG - + grep -q '^homeassistant.domain2.tld$'
2023-03-28 21:56:54,750: DEBUG - + export mail_enabled=True
2023-03-28 21:56:54,751: DEBUG - + mail_enabled=True
2023-03-28 21:56:54,751: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf
2023-03-28 21:56:54,752: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:54,752: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf
2023-03-28 21:56:54,753: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.conf
2023-03-28 21:56:54,754: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:54,754: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:54,755: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:54,755: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:54,957: DEBUG - + '[' True == True ']'
2023-03-28 21:56:54,958: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:54,958: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:54,959: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:54,959: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:54,961: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/homeassistant.domain2.tld/autoconfig/mail
2023-03-28 21:56:54,964: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:54,965: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:54,966: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:55,149: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/homeassistant.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:55,152: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:55,153: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.domain2.tld.d
2023-03-28 21:56:55,153: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.domain2.tld.d
2023-03-28 21:56:55,156: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.domain2.tld/autoconfig/mail/
2023-03-28 21:56:55,157: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.domain2.tld/autoconfig/mail/
2023-03-28 21:56:55,160: DEBUG - + export domain
2023-03-28 21:56:55,162: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:55,165: DEBUG - ++ jq '.certificates."mqtt.domain2.tld".CA_type'
2023-03-28 21:56:55,166: DEBUG - ++ tr -d '"'
2023-03-28 21:56:55,255: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:55,256: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:55,257: DEBUG - + grep -q '^mqtt.domain2.tld$'
2023-03-28 21:56:55,260: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:55,261: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:55,263: DEBUG - energy.maindomain.tld
2023-03-28 21:56:55,263: DEBUG - home.maindomain.tld
2023-03-28 21:56:55,264: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:55,264: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:55,264: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:55,265: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:55,265: DEBUG - domain2.tld
2023-03-28 21:56:55,266: DEBUG - energy.domain2.tld
2023-03-28 21:56:55,267: DEBUG - grocy.domain2.tld
2023-03-28 21:56:55,267: DEBUG - home.domain2.tld
2023-03-28 21:56:55,268: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:55,268: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:55,268: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:55,269: DEBUG - nodered.domain2.tld
2023-03-28 21:56:55,269: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:55,270: DEBUG - webmail.domain2.tld
2023-03-28 21:56:55,271: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:55,271: DEBUG - domain3.tld'
2023-03-28 21:56:55,272: DEBUG - + grep -q '^mqtt.domain2.tld$'
2023-03-28 21:56:55,272: DEBUG - + export mail_enabled=True
2023-03-28 21:56:55,272: DEBUG - + mail_enabled=True
2023-03-28 21:56:55,273: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.domain2.tld.conf
2023-03-28 21:56:55,273: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:55,274: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.domain2.tld.conf
2023-03-28 21:56:55,275: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.domain2.tld.conf
2023-03-28 21:56:55,275: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:55,276: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:55,276: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:55,277: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:55,478: DEBUG - + '[' True == True ']'
2023-03-28 21:56:55,479: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:55,479: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:55,480: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:55,480: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:55,482: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/mqtt.domain2.tld/autoconfig/mail
2023-03-28 21:56:55,485: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:55,486: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:55,487: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:55,672: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/mqtt.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:55,675: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:55,676: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d
2023-03-28 21:56:55,677: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d
2023-03-28 21:56:55,679: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/
2023-03-28 21:56:55,680: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail/
2023-03-28 21:56:55,683: DEBUG - + export domain
2023-03-28 21:56:55,685: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:55,688: DEBUG - ++ jq '.certificates."nextcloud.domain2.tld".CA_type'
2023-03-28 21:56:55,689: DEBUG - ++ tr -d '"'
2023-03-28 21:56:55,777: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:55,778: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:55,780: DEBUG - + grep -q '^nextcloud.domain2.tld$'
2023-03-28 21:56:55,783: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:55,783: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:55,785: DEBUG - energy.maindomain.tld
2023-03-28 21:56:55,786: DEBUG - home.maindomain.tld
2023-03-28 21:56:55,786: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:55,787: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:55,787: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:55,788: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:55,789: DEBUG - domain2.tld
2023-03-28 21:56:55,789: DEBUG - energy.domain2.tld
2023-03-28 21:56:55,790: DEBUG - grocy.domain2.tld
2023-03-28 21:56:55,790: DEBUG - home.domain2.tld
2023-03-28 21:56:55,791: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:55,791: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:55,792: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:55,792: DEBUG - nodered.domain2.tld
2023-03-28 21:56:55,793: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:55,794: DEBUG - webmail.domain2.tld
2023-03-28 21:56:55,794: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:55,795: DEBUG - domain3.tld'
2023-03-28 21:56:55,795: DEBUG - + grep -q '^nextcloud.domain2.tld$'
2023-03-28 21:56:55,796: DEBUG - + export mail_enabled=True
2023-03-28 21:56:55,796: DEBUG - + mail_enabled=True
2023-03-28 21:56:55,797: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf
2023-03-28 21:56:55,797: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:55,798: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf
2023-03-28 21:56:55,799: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.conf
2023-03-28 21:56:55,799: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:55,800: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:55,800: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:55,801: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:55,999: DEBUG - + '[' True == True ']'
2023-03-28 21:56:56,000: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:56,001: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:56,001: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:56,002: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:56,003: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nextcloud.domain2.tld/autoconfig/mail
2023-03-28 21:56:56,007: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:56,007: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:56,008: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:56,208: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nextcloud.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:56,210: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:56,211: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.domain2.tld.d
2023-03-28 21:56:56,212: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.domain2.tld.d
2023-03-28 21:56:56,215: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.domain2.tld/autoconfig/mail/
2023-03-28 21:56:56,216: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.domain2.tld/autoconfig/mail/
2023-03-28 21:56:56,219: DEBUG - + export domain
2023-03-28 21:56:56,221: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"owntracks.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 54, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain3.tld":' '{"CA_type":' '"selfsigned",' '"validity":' 3649, '"style":' '"warning",' '"summary":' '"selfsigned"}}}'
2023-03-28 21:56:56,224: DEBUG - ++ jq '.certificates."nodered.domain2.tld".CA_type'
2023-03-28 21:56:56,225: DEBUG - ++ tr -d '"'
2023-03-28 21:56:56,315: DEBUG - + export domain_cert_ca=letsencrypt
2023-03-28 21:56:56,316: DEBUG - + domain_cert_ca=letsencrypt
2023-03-28 21:56:56,317: DEBUG - + grep -q '^nodered.domain2.tld$'
2023-03-28 21:56:56,321: DEBUG - + export xmpp_enabled=False
2023-03-28 21:56:56,322: DEBUG - + xmpp_enabled=False
2023-03-28 21:56:56,323: DEBUG - energy.maindomain.tld
2023-03-28 21:56:56,323: DEBUG - home.maindomain.tld
2023-03-28 21:56:56,324: DEBUG - homeassistant.maindomain.tld
2023-03-28 21:56:56,324: DEBUG - nextcloud.maindomain.tld
2023-03-28 21:56:56,324: DEBUG - webmail.maindomain.tld
2023-03-28 21:56:56,325: DEBUG - wikijs.maindomain.tld
2023-03-28 21:56:56,326: DEBUG - domain2.tld
2023-03-28 21:56:56,326: DEBUG - energy.domain2.tld
2023-03-28 21:56:56,327: DEBUG - grocy.domain2.tld
2023-03-28 21:56:56,327: DEBUG - home.domain2.tld
2023-03-28 21:56:56,328: DEBUG - homeassistant.domain2.tld
2023-03-28 21:56:56,328: DEBUG - mqtt.domain2.tld
2023-03-28 21:56:56,329: DEBUG - nextcloud.domain2.tld
2023-03-28 21:56:56,329: DEBUG - nodered.domain2.tld
2023-03-28 21:56:56,330: DEBUG - owntracks.domain2.tld
2023-03-28 21:56:56,330: DEBUG - webmail.domain2.tld
2023-03-28 21:56:56,331: DEBUG - wikijs.domain2.tld
2023-03-28 21:56:56,331: DEBUG - domain3.tld'
2023-03-28 21:56:56,332: DEBUG - + grep -q '^nodered.domain2.tld$'
2023-03-28 21:56:56,332: DEBUG - + export mail_enabled=True
2023-03-28 21:56:56,333: DEBUG - + mail_enabled=True
2023-03-28 21:56:56,333: DEBUG - + ynh_render_template server.tpl.conf /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.domain2.tld.conf
2023-03-28 21:56:56,334: DEBUG - + local template_path=server.tpl.conf
2023-03-28 21:56:56,334: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.domain2.tld.conf
2023-03-28 21:56:56,335: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.domain2.tld.conf
2023-03-28 21:56:56,335: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d
2023-03-28 21:56:56,336: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:56,336: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:56,337: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:56,538: DEBUG - + '[' True == True ']'
2023-03-28 21:56:56,538: DEBUG - + ynh_render_template autoconfig.tpl.xml /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:56,539: DEBUG - + local template_path=autoconfig.tpl.xml
2023-03-28 21:56:56,540: DEBUG - + local output_path=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:56,540: DEBUG - ++ dirname /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.domain2.tld/autoconfig/mail//config-v1.1.xml
2023-03-28 21:56:56,542: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/nodered.domain2.tld/autoconfig/mail
2023-03-28 21:56:56,545: DEBUG - + python3 -c 'import os, sys, jinja2; sys.stdout.write(
2023-03-28 21:56:56,546: DEBUG -                     jinja2.Template(sys.stdin.read()
2023-03-28 21:56:56,547: DEBUG -                     ).render(os.environ));'
2023-03-28 21:56:56,732: DEBUG - + touch /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/nodered.domain2.tld.d/yunohost_local.conf
2023-03-28 21:56:56,735: DEBUG - + for domain in $YNH_DOMAINS
2023-03-28 21:56:56,736: DEBUG - + domain_conf_dir=/var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.domain2.tld.d
2023-03-28 21:56:56,736: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/etc/nginx/conf.d/owntracks.domain2.tld.d
2023-03-28 21:56:56,739: DEBUG - + mail_autoconfig_dir=/var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.domain2.tld/autoconfig/mail/
2023-03-28 21:56:56,740: DEBUG - + mkdir -p /var/cache/yunohost/regenconf/pending/nginx/var/www/.well-known/owntracks.domain2.tld/autoconfig/mail/
2023-03-28 21:56:56,743: DEBUG - + export domain
2023-03-28 21:56:56,746: DEBUG - ++ echo '{"certificates":' '{"maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"webmail.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 85, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"wikijs.maindomain.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 89, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"energy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 87, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"grocy.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 59, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"home.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"homeassistant.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"mqtt.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 55, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nextcloud.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 86, '"style":' '"success",' '"summary":' '"letsencrypt"},' '"nodered.domain2.tld":' '{"CA_type":' '"letsencrypt",' '"validity":' 77, '"style":' '"success",' '"summary":' '"letsencr
```

### let's encrypt certificate

```sh

```