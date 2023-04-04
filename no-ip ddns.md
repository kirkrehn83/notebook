---
share: true
---
> [!NOTE] dynamic dns service provider
> dynamic dns enhanced package for ddns services  

## faq  

| **item** | **description** |
| --- | --- |
| url | noip.com |
| user | rehn.kirk@gmail.com | 
| password | Ditd54zXDg92uk |  

## billing  


> [!WARNING] billing information
> dynamic dns enhanced package is $x/mth and renews on the xth of each month, next billing date is x  

## ssl certificate  


> [!NOTE] ssl certificate 
> one ssl certificate "encryption everywhere dv" is available at no charge per account  

**ssl certificate instructions**  


> [!INFO] instructions
> see [setup instructions](https://www.noip.com/support/knowledgebase/configure-rapidssl-basic-dv-ssl/)  

1. generate csr  
    - a csr is a file containing certificate application info including public key  

```
sudo openssl req -new -nodes -keyout kirkrehn.myddns.me.key -out kirkrehn.myddns.me.csr
```  

- keep .key file private as it is the private/secret key  

2. create a DN or distinguished name  

```
Country Name (2 letter code) [AU]: US
State or Province Name (full name) [Some-State]: Washington
Locality Name (eg, city) []: Tacoma
Organization Name (eg, company) [Internet Widgits Pty Ltd]: kirkhomelab
Organizational Unit Name (eg, section) []: tech admin
Common Name (eg, YOUR name) []: kirkrehn.myddns.me
Email Address []: kirk@kirkrehn.online

do NOT include 'extra' attributes such as challenge password
```  

3. open server.csr in TXT editor and copy/paste the contents into noip csr request form online [csr generator](https://my.noip.com/my-services/ssl-certificates)  

4. add TXT record to DNS records in order to validate FQDN (fully qualified domain name)  

    `TXT @ <string provided by ssl provider> 600 seconds`  

5. add TXT records for SPF record for e-mail validation  

    - only ONE SPF record is allowed, combine any existing records into one single line item `v=spf1 include:secureserver.net -all`  



