# Web Host and cPanel

This markdown file is mostly for cPanel options. Web hosting notes are at the beginning. For guides on all the cPanel features check for _documentation_ or _Knowledge Base_ for your host company. For A2 hosting it's [knowledge base](https://www.a2hosting.com/kb/cpanel). Most of the fields do not have any information as it will take me a long time to read the docs on every possible option.

- Choose managed hosting - it is the best and cheapest for a simple/small websites

<div id="back-to-top"></div>

## Table of Contents

1. [Different types of hosting](#different-types-of-hosting)
   1. [Whats included](#whats-included)
   1. [After signup](#after-signup)
1. [cPanel](#cpanel)
   1. [Preferences](#preferences)
   1. [Emails](#emails)
   1. [Domains](#domains)
   1. [Applications](#applications)
   1. [Software](#software)
   1. [Files](#files)
   1. [Databases](#databases)
   1. [Metrics](#metrics)
   1. [Security](#security)
   1. [Advanced](#advanced)
1. [Examples](#examples)
1. [Miscellaneous](#miscellaneous)

## Different types of hosting

- Business / shared hosting - where you have a server that have a number of shared accounts on that server - the cheapest option
- VPS hosting, a step up, a virtual server, gives you more freedom 
- Dedicated server - you have your own machine - you rent out a physical machine from the company - 
- Reseller hosting - like a VPS except you are selling shared hosting to other people - you have a billing system, skip 
- WordPress hosting - shared hosting optimized for WP

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Whats included

- most companies include a domain name free, at least for the 1st year 
- you may have a domain registered somewhere else - you would have to go back to that registrar and add the hosting nameservers to link your domain to your new hosting acct
- you can choose if you want WP installed automatically - 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### After signup

- you get an email with a login id which will be your email address 
- you need to create your password and then you can log into your account panel
- your account panel/admin area is where you can update your billing plan, your contact info, pay your bill, etc
- you will also see a link to cPanel

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

## cPanel

- this is where you manage your site
- each hosting company will have a different theme or setup for the cPanel main view page
- possible themes: paper lantern, jupiter, 
- in the sidebar is your server information: 
- addon domains - for packages where you can have more than 1 website - make sure they are small websites because they share the features like bandwidth
- db options MySQL, Postgres, 
- disk usage, email accts, forwarders, ftp accts, cpu usage, subdomains, ...

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Preferences

I don't see a link for this section of cPanel so search the Knowledge Base if you want to change anything in this section.

- Different for each hosting company 
- [Password](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/changing-your-cpanel-password) and security:
- [Change Language](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/changing-the-cpanel-language): 
- [Contact info](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/updating-contact-information-and-preferences-in-cpanel): 
- [User manager](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/cpanel-user-manager):

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Emails

[A2 cPanel Mail Features](https://www.a2hosting.com/kb/cpanel/cpanel-mail-features)

- lots of choices here
- Barracuda spam firewall:
- Forwarders: 
- Autoresponders: 
- Global email filters: 
- Email deliverability: 
- Encryptions: 
- Email disk usage: 
- Email accounts: 
- Email routing: 
- Mailing lists: 
- Email filters
- Spam filters
-  Calendars and contacts: 
- Remote MX wizard: 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Domains

[A2 cPanel Domain Features](https://www.a2hosting.com/kb/cpanel/cpanel-domain-features)

- where you can add your domains, subdomains, aliases, redirects, 
- [WordPress toolkit](https://www.a2hosting.com/kb/cpanel/wordpress-toolkit): 
- Domains: 
- Zone editor: 
- Site publisher: 
- Redirects

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Applications

I can't find a link for this section.

**Scripts**: 

- WordPress, Woocommerce, WP Toastmasters, WPBeginner, WordPress + Elementor, WordPress + Unsplash, WordPress + Weglot, Drupal 7, Mattomo, CubeCart, CMS made simple, Joomla, b2revolution, MODX

**Categories**: 

- Blogs, Portals/CMS, Forums, Image Galleries, Wikis, Social Networking, Ad Management, Calendars, Mails, Polls and Analytics, Project Management, E-Commerce, ERP, Customer Support, FRameworks, Educational, DB Tools, Music, RSS, File Management, Others, Libraries, Mails
- you can install them on your main domain, subdomain, add-on domain

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Software

[A2 cPanel Software Features](https://www.a2hosting.com/kb/cpanel/cpanel-software)

- Cloudflare: 
- PHP PEar PAckages: 
- Optimize website: 
- Dropmysite: 
- A2 website builder: 
- Select PHP version: 
- Setup Ruby app: 
- WordPress manager by Softaculous: 
- Perl modules: 
- Application manager: 
- Softaculouus apps installer: here is where you can install all of the scripts listed above 
- Setip Node.js app: 
- Setup Python app: 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Files

[A2 cPanel File Features](https://www.a2hosting.com/kb/cpanel/cpanel-file-features)

- File Manager: public_html is where all your website files go - you can create subfolders in here like `/blog` - he says don't use it because it's not that good but instead use an FTP account (this video is from 2017!) - 
- Directory privacy: 
- Web disk: 
- Backup:
- Git version control: 
- images:
- Disk usage: 
- FTP accounts: you can use your home ftp account or create new accounts - 
- Backup wizard: 
- Server rewind: 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Databases

[A2 cPanel Database Features](https://www.a2hosting.com/kb/cpanel/cpanel-database-features)

- phpMyAdmin: 
- MySQL Database Wizard: 
- PostgreSQL: 
- phpPgAdmin: 
- MySQL databases: 
- Remote MySQL: 
- PosthreSQL database wizard: 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Metrics

[A2 Using the Logging Features in cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-logging-features)

- Visitors: 
- Bandwidth: 
- Awstats: 
- Webalizer: 
- Metrics Editor: 
- Errors: 
- Raw Access: 
- Analog stats: 
- Webalizer FTP:
- Resource usage: 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Security

[A2 cPanel Security Features](https://www.a2hosting.com/kb/cpanel/cpanel-security-features)

- Autoinstall SSL: 
- IP Blocker: 
- Manage API Tokens: 
- Leech protection: 
- SSL/TLS Status: 
- Imunify360: 
- SSH access: 
- SSL/TLS:
- Hotlink protection: 
- ModSecurity: 
- Two-factor authentification: 

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Advanced

[A2 cPanel Advanced Features](https://www.a2hosting.com/kb/cpanel/advanced-features)

- Teminal: 
- Track DNS: 
- Error pages: 
- MIME types:
- Cron jobs: for automation
- Indexes:
- Apache handlers:
- Virus scanner:

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Examples

<ins><strong>Create an email account</strong></ins>:

- Click _Email Accounts_ > click _Create_ if you already have an email or the fields will be available to enter the prefix
- Select the domain name if you have more than one 
- Enter a Password
- Choose size though default is probably fine 
- Click _Create Account_ 
- Click _Check Email_ though your inbox will be empty except for maybe a system generated Welcome email with configuration settings
- The only option for me is `horde`, but you may also see `roundcube` and `SquirrelMail`
- Try to compose a test email to your personal account
- You can setup a forwarder to Gmail if you like

<ins><strong>Setup a forwarder</strong></ins>:

[CPanel Email Forwarder with A2 Hosting](https://docs.cpanel.net/cpanel/email/forwarders/)

- Go back to the main cPanel area > click on _Forwarders_
- Choose the domain and click _Add Forwarder_
- Enter the email address you want forwarded and the address to where you want to get it
- You can also send emails form your website email address from your forwarded address

<ins><strong>Deploy your website</strong></ins>:

- He suggests _FileZilla Client_ for FTP but no one does that anymore
- I manually uploaded my files for my first 2 websites via _File Manager_
- Those sites were simple HTML/CSS sites. I had to manually upload pages and images individually which was time consuming for my photography website, but it's a one-timer.

<ins><strong>Adding WordPress to a sub-domain</strong></ins>:

- Go to Domains > Subdomains - I don't have that options maybe because I have 3 domains for a package that has 3 as the max
- Check [How to configure subdomains in cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-domain-features/subdomains)
- enter the subdomain name like _wordpress_ or _blog_ - I'm not sure if he had to add a dot (`.`) or not
- your _document root_ is your main domain with what you entered above, e.g. `wordpress.mydomain.com`
- Click Create - then go back to the main cPanel window
- Find WordPress and click on it then click Install
- Under domains choose your sub-domain otherwise you will overwrite your root domain WHICH YOU DO NOT WANT TO DO!
- Enter your Admin User Name and PAssword - 
- OPTIONAL: Under Advanced Options, you can change the name of your database
- Click Install on that screen 
- when it is finished you will get a link to the main domain which is your sub-domain, and you also get a link to your WordPRess Admin area

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Miscellaneous

BACKUPS: 

- Choose _Backup Wizard_ - click _Backup_ to get a copy of your site or _Restore_ for that option

DATABASES: 

- To create a MySQL database click _MySQL Database Wizard_ 
- Your database will be prefixed with your username followed by an undeerscore, e.g. _username_
- In the input field enter the suffix like _secondary_, _test_, etc.
- Click Next Step > then for username you get the same prefix so enter _jim_ or whatever you want
- Enter a Password > click Create User
- Select All Privileges - click New USer
- Go back to the databases view and you will see your db

MANAGE YOUR DATABASES:

- Select `phpMyAdmin` - click on the database you created above 
- It won'y have any tables in it so you can create one such as _users_
- Fill out the fields and other settings
- Click Insert to add a record to your table and then click Go to add it
- You can create as many tables as you need for that database but make sure they are focused on users or whatever you chose
- Create a new table for subjects such as _products_

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>