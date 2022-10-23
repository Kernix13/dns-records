# DNS Records and related notes

<div id="back-to-top"></div>

## Table of Contents

1. [General notes](#general-notes)
1. [A Records](#a-records)
1. [CNAME Records](#cname-records)
1. [MX Records](#mx-records)
1. [TXT Records](#txt-records)
1. [NS Records](#ns-records)
1. [Miscellaneous notes](#miscellaneous-notes)
1. [Cloudflare notes](#cloudflare-notes)
1. [A2 notes](#a2-notes)
   1. [Transfer process](#transfer-process)

## General notes

- Your registrar will provide the DNSs that will propulgate your domain name records
- Check out the sites: [What's My DNS](https://www.whatsmydns.net/) | [DNS Checker](https://dnschecker.org/) | [MX Toolbox](https://mxtoolbox.com/)
- For example, `https://www.whatsmydns.net/#A/kernixwebdesign.com`
- These sites can get you DNSs, registrar, expiration, DNS recs, admin contact info, etc.
- Your web hosting company provide DNS services
- Cloudflare is a DNS provider -
- DNS records: `A` record (website), `CNAME` (www?), `MX` record (email service), `TXT` (verification), and others...
- All this info is public

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## A Records

- `A` - The most common DNS record, used to point a domain to an IP address
- must have it for a domain that has an associated website
- if there is no IP address and the site doesn't work
- `A` Records: `A` records will point to a specific IP Address, you do not need to buy your domain name form your host company - you do that with DNS records, specifically a DNS A record - Aoache and Nginx - you need to point a domain name to an IP address, to map it to an IP addres
- In your host company cPanel, find the DNS section for your domain name - maybe Cloudflare for me
- click _Add Record_ > choose _Type A_ > click _Add_
- Host convention is `@` to stand in for the actual domain name, and in `point to` field add the IP address associated with your domain name
- e.g, @ 111.111.11.111 and then www 111.111.11.111 > click `Add records` > go to dnschecker.org to watch the progress worldwide - you will have to wait
- You may also see `IPv4` address field instead of `point to`
- If you see records propulgate but your site address is not found then it may be a local dns caching issue - try checking your site in incognito mode

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## CNAME Records

- `CNAME` Record - Also known as alias records or canonical name, they point to other DNS records. Sometimes used for subdomains
- It maps one domain name or subdomain to another domain - a little odd but e.g. `www` and `ftp` that both use the same IP address
- They will eventually point to the A record which points to the ip address -
- Drawback for using `CNAME` recs for subdomains: you can use an `A` rec for `store.example.com`
- You can do it with a `CNAME` rec but now 2 DNS lookups are required > make sure an `A` rec already exists then > choose `CNAME` type > you can type the full subdomain or just the subdomain part > for the domain name you can type the name or just use an `@` symbol as for an `A` rec
- in command prompt you can use the `dig` or `nslookup` command to get the `CNAME` or `A` rec

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## MX Records

- `MX` Record - Mail Exchanger records are used to set email servers and their priority
- There are a # of them that you need depending on your site settings
- Each `MX` record has a priority - Google workspace email provider will tell you what you need to set if that is what you are using
- The web server and the mail server may not be the same server
- note the `Priority` field - mail is sent to the record with the lowest priority
- It goes from 0-256 or 2 to the power of 32, it depends
- To create > add `@` for the `Host` field > choose `MX` > set time to live (`TTL`) as 3600 > add a priority > in data field add the mail server doamin like `mail.kernixwebdesign.com` though the last two fields may be combind like `10 mail.kernixwebdesign.com`

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## TXT Records

- `TXT` records - Text records are commonly used for configuration settings such as `SPF` and `DKIM` records
- The primary 2 uses for `TXT` records,
  - 1. email spam prevention,
  - 2. domain ownership verification
- For #2 you are given a long string to add which is proof you own the domain
- For #1 this can be done with `SPF`, `DKIM` and `DMARC` records which are technically text records but `SPF` may be listed as its own type
- a `TXT` rec can be used as an `SPF` rec if N/A I think (he says he has another video for that)
- Some `TXT` records are used for verification and used only once
- An `SPF` rec depends on the email provider you have and it helps being recognized by other email providers

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## NS Records

- `NS`records: Name Server records store the authoritative `nameserver`.
- `NS` record vs `Nameserver`: `NS` stands for nameserver - the primary purpose is to connect a domain with a nameserver
- Similar to other records they are an object with props of `host` name, `type`, `TTL`, and `value`
- There should be at least 2 nameservers for each domain and and each nameserver should resolve to a unique IP address
- Usually when you purchase a domain name from your hosting provider, your `NS` records are automatically set up for you
- You need to change the `NS` recs when you buy a domain name from someone other than your host provider
- In which case you can give the domain name provider your host prodiver nameservers or vice versa
- Or you can use a 3rd party DNS provider like Cloudflare to manage your DNS records in which case you give those `NS` recs to both your domain registrar and host provider

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## Miscellaneous notes

- Apache or Nginx - he has terminal sessions for servers
- he has a config file in an nginx folder on his computer and he changed the `server_name` to his domain name
- for nginx he add the www version on the same line -
- for apache folder, there is a default file - confusing - he added a key/value of `ServerName` websitename.com and `ServerAlias` as www.websitename.com

## Cloudflare Notes

CLOUDFLARE NAMESERVERS:

```
serenity.ns.cloudflare.com
steven.ns.cloudflare.com
```

Siteground NAMESERVERS:

```
ns1.us233.siteground.us
ns2.us233.siteground.us
```

Cloudflare: api token, speed, dns, cache, rules, network, traffic, scrape

- https://www.a2hosting.com/kb/add-on-services/cloudflare/how-to-activate-cloudflare
- https://perfmatters.io/docs/cloudflare-wordpress-settings/

RULES:

- fairmountpetservice.com/wp-admin* with Browser Integrity Check: `On`, http://*fairmountpetservice.com/* with `Always Use HTTPS`, fairmountpetservice.com/*preview=true* with Browser Integrity Check: On - maybe fairmountpetservice.com/wp-login*,
- SSL/TLS: Overview – Full, Edge certs – always use https,

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## A2 notes

A2 NAMESERVERS:

```
NS1.A2HOSTING.COM
NS2.A2HOSTING.COM
NS3.A2HOSTING.COM
NS4.A2HOSTING.COM
```

```
Type: MX
Name: @
Mail server: mi3-ss58.a2hosting.com
TTL: Auto:
Priority: 0
```

A2 Links:

- https://www.a2hosting.com/kb/cpanel/cpanel-domain-features/using-the-cpanel-zone-editor
- https://www.a2hosting.com/kb/cpanel/cpanel-mail-features/mail-exchanger-mx-record-entry
- check out: https://www.a2hosting.com/kb/getting-started-guide/configuring-domain-settings/ accessing-your-web-site-before-dns-propagation-is-complete#Method-2.3A-Use-the-hosts-file
- https://www.a2hosting.com/kb/cpanel/cpanel-mail-features/e-mail-accounts

1. cPanel > Email Accounts > Create >
2. In the EMAIL section of the cPanel home screen, click Email Accounts.
3. Click Create.
4. From the Domain menu, select the domain where you want to create the e-mail account.

This article will show you how to transfer everyguitarchord.com and kernixwebdesign.com to A2 Hosting:

- https://www.a2hosting.com/kb/getting-started-guide/configuring-domain-settings/transferring-a-domain-to-a2-hosting

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Transfer process

1. transfer domain name(s) to A2,
2. The domain must be unlocked (contact the domain's current registrar),
3. The domain's contact information must be current. A domain name record contains an Administrative Contact and a Technical Contact. Both of these contacts can be the same person, but at least one of them should be you. When a domain transfer request is initiated, the Administrative Contact and Technical Contact are notified by e-mail
4. Additionally, if your domain has **WHOIS** privacy protection enabled, you should temporarily disable it before the migration. Doing this helps ensure that you receive the domain transfer verification e-mail message
5. You must obtain an `EPP` (Extensible Provisioning Protocol) code from the current registrar or hosting company. This code is an identifying number for the domain that indicates you are authorized to transfer it. In some cases, there may be a time delay between when the domain is initially registered and when it can be transferred - If you are unsure what your `EPP` code is, or how to find it, contact the domain's current registrar. The `EPP` code may also be called an `EPP key`, an `AuthInfo code`, a `Transfer secret`, or something similar - you can find the EPP code in your Client Area > Services > Domains > Manage > kebab menu > Get EPP Code
6. When you initiate the domain transfer process, A2 Hosting sends a domain transfer request to the domain's Administrative and Technical contacts. The amount of time to complete the domain transfer depends in large part on how quickly these contacts approve the transfer request. If the Administrative or Technical contact approves the authorization promptly, the domain may be transferred in as little as 2 to 4 days

Ticket with A2 support:

> You can create the same email addresses from cPanel > Email accounts. You can view the details information here : https://www.a2hosting.com/kb/cpanel/cpanel-mail-features/e-mail-accounts

> Once done, you need to update the DNS records for all the sites so they point to A2. Email: You can create the same email addresses from cPanel > Email accounts. You can view the details information here : https://www.a2hosting.com/kb/cpanel/cpanel-mail-features/e-mail-accounts

> > Fairmount Pet Service seems fine. Kernix web Design: I can get into the WordPRess dashboard but I'm getting a 404 for my portfolio page at: https://kernixwebdesign.com/resume-portfolio.html

> > That page is in my public_html folder. I also have the CSS and JavaScript files in that folder. That page links to one of my portfolio items which also lives in public_html and has links to files in the css, icons, images, and js folders in public_html. This is my web design website and is the one I need the most! I also tried to send a message from the contact page and I got a success message but it did not go through, but then I haven't done anything with that yet.

> > Every Guitar Chord: Site is fine, Wordpress admin dashboard 404, but I have a plugin to hide the login. My url for that page is https://everyguitarchord.com/384closed/. The plugin I use is WPS Hide Login. I can try removing it manually from Siteground. But I also have that plugin installed on fairmountpetservice.com and kernixwebdesign.com. Let me know why I can get into thise but not this dashboard.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>
