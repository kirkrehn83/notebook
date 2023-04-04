---
share: true
---
> [!INFO] command-line terminal admin usage
> for linux usage on home server

## faq
| **item** | **description** |
| --- | --- |
| url | pop.local |
| local ip | 192.168.50.136 |
| ssh user | root |
| ssh password | kirkhomelab |
| root user | kirkrehn |
| root password | kirkster |

## config
1.  create domain
```sh
yunohost domain add maindomain.tld

# for godaddy
yunohost domain add kirkrehn.online
```
2. set domain as main domain
```sh
yunohost domain  main-domain -n newdomain.tld

# for godaddy
yunohost domain main-domain -n kirkrehn.online
```
3. push dns records 
	1. for yunohost dyndns service
		```sh
		yunohost dyndns update
		```

	2. for godaddy
		```sh
		yunohost domain  dns push maindomain.tld --force
		# for godaddy
		yunohost domain dns push kirkrehn.online --force
		```
4. let's encrypt certificate
```sh
yunohost domain cert install maindomain.tld --no-check --force
```
6. create subdomain for app
```sh
yunohost domain add sub.domain.tld

# for homarr
yunohost domain add home.kirkrehn.online
```
7. update dns records
	1. for yunohost dyndns service
		```sh
		yunohost dyns update
		```
	2. for godaddy
		```sh
		yunohost domain dns push kirkrehn.online --force

		# dns records unable to be set automatically will be shown and must be updated manually at [godaddy](godaddy.com)
		# generally these are MX and xmpp records
		```
8. install let's encrypt certificate on subdomain
```sh
yunohost domain cert install sub.maindomain.tld --no-check --force
```
9. update dnsmasq
```sh
yunohost service restart dnsmasq
```
