# DNS Records and related notes

Notes on DNS records are in this. Also check out the cPanel markdown file.

<div id="back-to-top"></div>

DONE:

1. A Records

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
- For example, `https://www.whatsmydns.net/#A/everyguitarchord.com`
- These sites can get you DNSs, registrar, expiration, DNS recs, admin contact info, etc.
- Your web hosting company provide DNS services
- Cloudflare is a DNS provider
- DNS records: `A` record (website), `CNAME` (www?), `MX` record (email service), `SPF(txt)` (verification), and others...

> ### _All this info is public_

- Specific `nameservers` are required to manage DNS

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## A Records

- `A` - The most common DNS record, used to point a domain to an IP address, to the physical IP address of the computer hosting that domain
- The value of an `A` record is always an IP address, and multiple A records can be configured for one domain name
- An `A` record uses a domain name to find the IP address of a computer connected to the internet
- The _A_ in `A` record stands for _Address_
- must have it for a domain that has an associated website
- if there is no IP address then the site doesn't work
- A 32 bit Internet address representing an `IPv4` address
- is the most fundamental type of DNS record
- `A` Records: `A` records will point to a specific IP Address, you do not need to buy your domain name form your host company - you do that with DNS records, specifically a DNS A record - Aoache and Nginx - you need to point a domain name to an IP address, to map it to an IP addres
- In your host company cPanel, find the DNS section for your domain name - maybe Cloudflare for me
- click _Add Record_ > choose _Type A_ > click _Add_
- Host convention is `@` to stand in for the actual domain name, and in `point to` field add the IP address associated with your domain name
- e.g, @ 111.111.11.111 and then www 111.111.11.111 > click `Add records` > go to dnschecker.org to watch the progress worldwide - you will have to wait
- You may also see `IPv4` address field instead of `point to`
- If you see records propulgate but your site address is not found then it may be a local dns caching issue - try checking your site in incognito mode
- Example:

| example.com | record type: |  value:   |  TTL  |
| :---------: | :----------: | :-------: | :---: |
|      @      |      A       | 192.0.2.1 | 14400 |

- `@` indicates that this is a record for the root domain, and the "14400" value is the `TTL` (time to live), listed in seconds
- The default TTL for A records is 14,400 seconds. This means that if an A record gets updated, it takes 240 minutes (14,400 seconds) to take effect
- enables a user's device to connect with and load a website, without the user memorizing and typing in the actual IP address. The user's web browser automatically carries this out by sending a query to a DNS resolver
- DNS A records are also used for operating a Domain Name System-based Blackhole List (DNSBL). DNSBLs can help mail servers identify and block email messages from known spammer domains

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## CNAME Records

- `CNAME` Record - Also known as alias records or canonical name, they point to other DNS records. Sometimes used for subdomains
- it points one domain or subdomain to another domain name, allowing you to update one A Record each time you make a change, regardless of how many Host Records need to resolve to that IP address
- is used in lieu of an `A` record, when a domain or subdomain is an alias of another domain. All `CNAME` records must point to a domain, never to an IP address
- Oftentimes, when sites have subdomains such as blog.example.com or shop.example.com, those subdomains will have `CNAME` records that point to a root domain (example.com). This way if the IP address of the host changes, only the DNS A record for the root domain needs to be updated and all the `CNAME` records will follow along with whatever changes are made to the root
- A frequent misconception is that a CNAME record must always resolve to the same website as the domain it points to, but this is not the case. The CNAME record only points the client to the same IP address as the root domain. Once the client hits that IP address, the web server will still handle the URL accordingly
- It maps one domain name or subdomain to another domain - a little odd but e.g. `www` and `ftp` that both use the same IP address
- They will eventually point to the A record which points to the ip address -
- Drawback for using `CNAME` recs for subdomains: you can use an `A` rec for `store.example.com`
- You can do it with a `CNAME` rec but now 2 DNS lookups are required > make sure an `A` rec already exists then > choose `CNAME` type > you can type the full subdomain or just the subdomain part > for the domain name you can type the name or just use an `@` symbol as for an `A` rec
- in command prompt you can use the `dig` or `nslookup` command to get the `CNAME` or `A` rec for a website

| example.com | record type: |           value:           |  TTL  |
| :---------: | :----------: | :------------------------: | :---: |
|      @      |    CNAME     | is an alias of example.com | 32600 |

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## MX Records

| example.com | record type: | Priority |        value:         |  TTL  |
| :---------: | :----------: | :------: | :-------------------: | :---: |
|      @      |      MX      |    10    | mailhost1.example.com | 45000 |
|      @      |      MX      |    20    | mailhost2.example.com | 45000 |

- `MX` Record - Mail Exchanger records are used to set email servers and their priority
- A DNS 'mail exchange' (MX) record directs email to a mail server. The MX record indicates how email messages should be routed in accordance with the Simple Mail Transfer Protocol (SMTP, the standard protocol for all email). Like CNAME records, an MX record must always point to another domain.
- The 'priority' numbers before the domains for these MX records indicate preference; the lower 'priority' value is preferred. The server will always try mailhost1 first because 10 is lower than 20. In the result of a message send failure, the server will default to mailhost2
- The email service could also configure this MX record so that both servers have equal priority and receive an equal amount of mail, both with a priority of `10` - This configuration enables the email provider to equally balance the load between the two servers
- Message transfer agent (MTA) software is responsible for querying MX records. When a user sends an email, the MTA sends a DNS query to identify the mail servers for the email recipients. The MTA establishes an SMTP connection with those mail servers, starting with the prioritized domains
- MX records have to point directly to a server's A record or AAAA record
- There are a # of them that you need depending on your site settings
- Each `MX` record has a priority - Google workspace email provider will tell you what you need to set if that is what you are using
- The web server and the mail server may not be the same server
- note the `Priority` field - mail is sent to the record with the lowest priority
- It goes from 0-256 or 2 to the power of 32, it depends
- To create > add `@` for the `Host` field > choose `MX` > set time to live (`TTL`) as 3600 > add a priority > in data field add the mail server doamin like `mail.kernixwebdesign.com` though the last two fields may be combind like `10 mail.kernixwebdesign.com`

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## TXT Records

| example.com | record type: |           value:           |  TTL  |
| :---------: | :----------: | :------------------------: | :---: |
|      @      |     TXT      | Some description text here | 32600 |

- `TXT` records - Text records are commonly used for configuration settings such as `SPF` and `DKIM` records
- The DNS ‘text’ (TXT) record lets a domain administrator enter text into the Domain Name System (DNS). The TXT record was originally intended as a place for human-readable notes. However, now it is also possible to put some machine-readable data into TXT records. One domain can have many TXT records
- Today, two of the most important uses for DNS TXT records are email spam prevention and domain ownership verification, although TXT records were not designed for these uses originally
- The primary 2 uses for `TXT` records,
  - 1. email spam prevention,
  - 2. domain ownership verification
- For #2 you are given a long string to add which is proof you own the domain
- For #1 this can be done with `SPF`, `DKIM` and `DMARC` records which are technically text records but `SPF` may be listed as its own type
- a `TXT` rec can be used as an `SPF` rec if N/A I think (he says he has another video for that)
- Some `TXT` records are used for verification and used only once
- An `SPF` rec depends on the email provider you have and it helps being recognized by other email providers
- The original RFC only indicates that 'text strings' go in the 'value' field of a TXT record. This could be any text that an administrator wants to associate with their domain.
- Most DNS servers will put a limit on how big TXT records can be and how many records they can store, so administrators cannot use TXT records for large amounts of data
- format for storing attributes and their corresponding values within the 'value' field of TXT records: the attribute and the value contained within quotation marks (") and separated by an equal sign (=), `"printer=lpr5"`, but this is really followed or done anymore if ever
- Spammers often try to fake or forge the domains from which they send their email messages. TXT records are a key component of several different email authentication methods that help an email server determine if a message is from a trusted source
- Common email authentication methods include Domain Keys Identified Mail (DKIM), Sender Policy Framework (SPF), and Domain-based Message Authentication, Reporting & Conformance (DMARC). By configuring these records, domain operators can make it more difficult for spammers to spoof their domains and can track attempts to do so
- While domain ownership verification was not initially a feature of TXT records, this approach has been adopted by some webmaster tools and cloud providers.
- By uploading a new TXT record with specific information included, or editing the current TXT record, an administrator can prove they control that domain

`SPF records`: SPF TXT records list all the servers that are authorized to send email messages from a domain.

`DKIM records`: DKIM works by digitally signing each email using a public-private key pair. This helps verify that the email is actually from the domain it claims to be from. The public key is hosted in a TXT record associated with the domain. (Learn more about public key encryption.)

`DMARC records`: A DMARC TXT record references the domain's SPF and DKIM policies. It should be stored under the title \_dmarc.example.com. with 'example.com' replaced with the actual domain name. The 'value' of the record is the domain's DMARC policy (a guide to creating one can be found here).

### SPF Record

- Stands for Sender Policy Framework and is an email validation technique by detecting email spoofing and preventing spam
- SPF records are a type of DNS TXT record commonly used for email authentication. SPF records include a list of IP addresses and domains authorized to send emails from that domain
- A sender policy framework (SPF) record is a type of DNS TXT record that lists all the servers authorized to send emails from a particular domain
- SPF records were originally created because the standard protocol used for email — the Simple Mail Transfer Protocol (SMTP) — does not inherently authenticate the “from” address in an email. This means that without SPF or other authentication records, an attacker can easily impersonate a sender and trick the recipient into taking action or sharing information they otherwise would not.
  if an SPF record does not have a sender’s IP address or domain on its list, the receiving server will either not deliver those emails or mark them as spam
- they help email servers confirm whether an email comes from a trusted source
- Using an `SPF` record can also prevent your emails from being flagged as spam
- An `SPF` record starts with a _v_, _v1_ is the most recognized - e.g.: `<v="spfl a include:_spf.google.com -all">`
  - where `v="spfl` is for version 1, `a` is for authorization, `include` is used to authorize emails, `-all` denies all emails not listed in the record

```bash
# Another example
v=spf1 ip4=192.0.2.0 ip4=192.0.2.1 include:examplesender.email -all
```

Check Cloudflare's page on [SPR Records](https://www.cloudflare.com/learning/dns/dns-records/dns-spf-record/) for an explanation of the above example.

Why use SPF Records?

There are many reasons domain operators use SPF records:

- Preventing attacks: If emails are not authenticated, companies and email recipients are at risk for phishing attacks, spam emails, and email spoofing. With SPF records, it is harder for attackers to imitate a domain, reducing the likelihood of these attacks.
- Improving email deliverability: Domains without a published SPF record may have their emails bounce or be marked as spam. Over time, bounced emails or emails marked as spam can hurt a domain’s ability to reach their audience’s inboxes, compromising efforts to communicate with customers, employees, and other entities.
- DMARC compliance: DMARC is an email validation system that helps ensure that emails are sent only by authorized users. DMARC policies dictate what servers should do with emails that fail SPF and DKIM checks. Based on the DMARC policy instructions, those emails will either be marked as spam, rejected, or delivered as normal. Domain administrators receive reports about their email activity that help them make adjustments to their policy.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## NS Records

| example.com | record type: |        value:         |  TTL  |
| :---------: | :----------: | :-------------------: | :---: |
|      @      |      NS      | ns1.exampleserver.com | 21600 |

- `NS`records: Name Server records store the authoritative `nameserver`.
- The NS record indicates which DNS server is authoritative
- the nameserver record indicates which DNS server is authoritative for that domain
- NS records tell the Internet where to go to find out a domain's IP address. A domain often has multiple NS records which can indicate primary and secondary nameservers for that domain. Without properly configured NS records, users will be unable to load a website or application
- `NS` record vs `Nameserver`: `NS` stands for nameserver - the primary purpose is to connect a domain with a nameserver
- Similar to other records they are an object with props of `host` name, `type`, `TTL`, and `value`
- There should be at least 2 nameservers for each domain and and each nameserver should resolve to a unique IP address
- Usually when you purchase a domain name from your hosting provider, your `NS` records are automatically set up for you
- You need to change the `NS` recs when you buy a domain name from someone other than your host provider
- In which case you can give the domain name provider your host prodiver nameservers or vice versa
- Or you can use a 3rd party DNS provider like Cloudflare to manage your DNS records in which case you give those `NS` recs to both your domain registrar and host provider

What is a nameserver:

- A nameserver is a type of DNS server. It is the server that stores all DNS records for a domain, including A records, MX records, or CNAME records.
- Almost all domains rely on multiple nameservers to increase reliability: if one nameserver goes down or is unavailable, DNS queries can go to another one. Typically there is one primary nameserver and several secondary nameservers, which store exact copies of the DNS records in the primary server. Updating the primary nameserver will trigger an update of the secondary nameservers as well.
- When multiple nameservers are used (as in most cases), NS records should list more than one server
- Domain administrators should update their NS records when they need to change their domain's nameservers. For instance, some cloud providers provide nameservers and require their customers to point to them.
- Admins may also wish to update their NS records if they want a subdomain to use different nameservers. In the example above, the nameserver for example.com is ns1.exampleserver.com. If the example.com admin wanted blog.example.com to resolve via a ns2.exampleserver.com instead, they could set this up by updating the NS record.
- When NS records are updated, it may take several hours for the changes to be replicated throughout the DNS.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## Miscellaneous notes

- Apache or Nginx - he has terminal sessions for servers
- he has a config file in an nginx folder on his computer and he changed the `server_name` to his domain name
- for nginx he add the www version on the same line -
- for apache folder, there is a default file - confusing - he added a key/value of `ServerName` websitename.com and `ServerAlias` as www.websitename.com

Other DNS Records:

- DNS `AAAA` record: The DNS AAAA record matches a domain name with an IPv6 address — similar to A records, which do the same for IPv4 addresses.
- DNS `SOA` record: The SOA record contains important information about a domain and who is responsible for it
- DNS `SRV` record: The SRV record is used for special services like VoIP.
- DNS `PTR` record: The PTR record is used for reverse DNS lookups
- DNS `DNSKEY` and `DS` Records: The DNSKEY and DS records are used by DNSSEC resolvers to verify the authenticity of DNS records

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
