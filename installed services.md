---
share: true
---
```toc

```

## services list


> [!WARNING] update date
> last updated on tue 04 apr 2023


```
apps: 
  0: 
    description: Network-wide ads & trackers blocking DNS server
    domain_path: kirkrehn.online/adguard
    id: adguardhome
    name: AdGuard Home
    version: 0.107.26~ynh1
  1: 
    description: Backup your server on a host server using Borg.
    id: borg
    name: Borg Backup
    version: 1.1.16~ynh29
  2: 
    description: Offer backup storage to a friend.
    id: borgserver
    name: Borg Server
    version: 1.1.16~ynh9
  3: 
    description: Distributed and RESTful search engine
    id: elasticsearch7
    name: ElasticSearch 7
    version: 7.17.8~ynh6
  4: 
    description: Processing, logging and visualising energy, temperature and other environmental data
    domain_path: energy.kirkrehn.online/
    id: emoncms
    name: Emoncms
    version: 11.3.0~ynh1
  5: 
    description: Self-hosted financial manager
    domain_path: kirkrehn.online/firefly
    id: firefly-iii
    name: Firefly III
    version: 6.0.4~ynh1
  6: 
    description: Web-based groceries & household management solution for your home
    domain_path: grocy.kirkrehn.online/
    id: grocy
    name: Grocy
    version: 3.3.2~ynh3
  7: 
    description: Customizable browser's home page to interact with your homeserver's Docker containers
    domain_path: home.kirkrehn.online/
    id: homarr
    name: Homarr
    version: 0.11.4~ynh1
  8: 
    description: Home automation platform
    domain_path: homeassistant.kirkrehn.online/
    id: homeassistant
    name: Home Assistant
    version: 2023.3.6~ynh1
  9: 
    description: Very lightweight Speedtest.
    domain_path: kirkrehn.online/librespeed
    id: librespeed
    name: LibreSpeed
    version: 5.2.5~ynh1
  10: 
    description: Open source analytics platform for measuring Web statistics
    domain_path: kirkrehn.online/analytics
    id: matomo
    name: Matomo
    version: 4.14.0~ynh1
  11: 
    description: Interconnect your objects and applications with an open source MQTT broker
    id: mosquitto
    name: Mosquitto
    version: 2.0.12~ynh1
  12: 
    description: Flow-based programming for the Internet of Things
    domain_path: nodered.kirkrehn.online/
    id: nodered
    name: Node-RED
    version: 3.0.2~ynh3
  13: 
    description: Keep track of your location history
    domain_path: owntracks.kirkrehn.online/
    id: owntracks
    name: OwnTracks
    version: 0.1~ynh10
  14: 
    description: Ergonomic, simple and elegant CMS to build in no time landpage websites with modern design
    domain_path: kirkrehn.online/prettynoemiecms
    id: prettynoemiecms
    name: PrettyNoemie CMS
    version: 2022.06.26~ynh1
  15: 
    description: Look up DNS records such as SPF, MX, Whois
    domain_path: kirkrehn.myddns.me/spftoolbox
    id: spftoolbox
    name: SPFtoolbox
    version: 2.1.1~ynh2
  16: 
    description: Open source powerful wiki app built on Node.js, Git and Markdown
    domain_path: wikijs.kirkrehn.online/
    id: wikijs
    name: Wiki.js
    version: 2.5.296~ynh1
```



## domains list  
**kirkrehn.online** - main domain  
    - energy.kirkrehn.online  
    x firefly.kirkrehn.online  
    -  home.kirkrehn.online  
    -  homeassistant.kirkrehn.online  
    x nextcloud.kirkrehn.online  
    -  nodered.kirkrehn.online  
    -  owntracks.kirkrehn.online  
    -  wikijs.kirkrehn.online  
**kirkrehn.myddns.me**   
    x energy.kirkrehn.myddns.me  
    x grocy.kirkrehn.myddns.me  
    x home.kirkrehn.mydns.me  
    x homeassistant.kirkrehn.myddns.me  
    x mqtt.kirkrehn.myddns.me  
    x nextcloud.kirkrehn.myddns.me  
    x nodered.kirkrehn.myddns.me  
    x owntracks.kirkrehn.myddns.me  
    x webmail.kirkrehn.myddns.me  
    x wikijs.kirkrehn.myddns.me  
**kirklabz.nohost.me**  
    x homeassistant.kirklabz.nohost.me  
    x wikijs.kirklabz.nohost.me  

## records cleanup

### change main domain to kirkrehn.online
```sh
yunohost domain main-domain -n kirkrehn.online
```
-> results in error: `alias abuse@kirkrehn.online can not be removed fromthe 'admins' group`

### move apps from kirkrehn.myddns.me domain to kirkrehn.online domain
```sh
yunohost app change-url adguardhome
    new domain: kirkrehn.online
    new path: adguard
yunohost app change-url firefly-iii
    new domain: kirkrehn.online
    new path: firefly
yunohost domain add grocy.kirkrehn.online
yunohost domain cert install grocy.kirkrehn.online --no-checks --force
yunohost app change-url grocy
    new domain: grocy.kirkrehn.online
    new path: /
yunohost app change-url homarr
    new domain: home.kirkrehn.online
    new path: /
yunohost app change-url matomo
    new domain: kirkrehn.online
    path: analytics
yunohost app change-url nodered
    main domain: nodered.kirkrehn.online
    path: /
yunohost app change-url owntracks
r    main domain: owntracks.kirkrehn.online
    path: /
yunohost app change-url prettynoemiecms
    new domain: kirkrehn.online
    path: prettynoemiecms
yunohost app change-url wikijs
    new domain: wikijs.kirkrehn.online
    path: /


--> yunohost domain add speedtest.kirkrehn.online
yunohost domain cert install speedtest.kirkrehn.online --no-checks --force
yunohost app change-url librespeed

```

### push updated dns records
```sh

```

### renew each let's encrypt certificate
```sh

```

### remove unecessary kirkrehn.myddns.me domains
```sh

```

### remove unecessary kirklabz.nohost.me domains
```sh

```

**keep kirklabz.nohost.me as domain on file for occassional use if needed**

### remove e-mail and xmpp from all subdomains that do not require use of e-mail services
```sh

```

### re-run dns push
```sh

```

