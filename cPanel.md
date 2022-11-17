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

I don't see a link for this section of cPanel so search the Knowledge Base if you want to change anything in this section. These options will be different for each hosting company:

- [Password](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/changing-your-cpanel-password) and security: Nothing out of the ordinary here, a simple form to enter your current password followed by 2 fields for the new one.
- [Change Language](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/changing-the-cpanel-language): eslf-explanatory.
- [Contact info](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/updating-contact-information-and-preferences-in-cpanel): set your default email address, set up push notifications, select various contact preferences, notifications for AutoSSL.
- [User manager](https://www.a2hosting.com/kb/cpanel/getting-started-with-cpanel/cpanel-user-manager): Per this page:

> This interface allows you to manage subaccounts. Subaccounts use the same login and password information for email, FTP, and Web Disk services. The system synchronizes the password of each of the subaccount’s allowed services. (SKIP)

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Emails

[A2 cPanel Mail Features](https://www.a2hosting.com/kb/cpanel/cpanel-mail-features)

The following are worth using:

- **Forwarders**: Send a copy of any incoming email from one address to another
- **Autoresponders**: Configure an email account to send automated emails. This can be useful if you are on vacation or unavailable, or if you have a generic message that you wish to send from a support email address
- **Global email filters**: Create and manage email filters for your main email account. Rules will be processed in the order shown below, from the top down. For more information, read the [documentation](https://docs.cpanel.net/cpanel/email/global-email-filters/).
- **Email deliverability**: Use this interface to reduce the number of emails sent from this server that end up in spam folders. For more information, read our [Email Deliverability](https://docs.cpanel.net/cpanel/email/email-deliverability-in-cpanel/) documentation:

> Use this interface to identify problems with your mail-related DNS records for one or more of your domains. The system uses these records to verify that other servers can trust it as a sender

- **Email disk usage**: This utility allows you to recover disk space by deleting old messages from your mailbox.
- **Email accounts**: This feature lets you create and manage email accounts. Read the [documentation](https://go.cpanel.net/Accounts) to learn more.
- **Email routing**: Route a domain’s incoming mail to a specific server. For more information, read the [documentation](https://docs.cpanel.net/cpanel/email/email-routing/). 
- **Mailing lists**: Use a single address to send email to multiple email addresses. Read the [documentation](https://go.cpanel.net/MailingLists) for more info.
- **Email filters**: Create and manage email filters for an email address that you specify. This can be useful if you want to avoid spam, redirect mail, or pipe messages to a program. For more information, read the [documentation](https://go.cpanel.net/UserFilters). 
- **Spam filters**: Manage the settings for the spam filters (powered by Apache SpamAssassin™) for your email accounts. Identify unsolicited bulk email, more commonly known as spam, and send it to a separate folder (Spam Box) or automatically delete it (Auto-Delete) from your email account.
- **Remote MX wizard**: This tool allows you to configure the MX records and other services of your mail provider in a few clicks.

Skip the following IMO:

- _Barracuda spam firewall_: No longer available on A2
- **Encryptions**: GnuPG is a publicly available encryption scheme that uses the “public key” approach. With GnuPG, messages are encrypted using a “public key” however, they can only be decrypted by a “private key”, which is retained by the intended recipient of the message...
- **Calendars and contacts**: ...set up calendars and contacts on your device.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Domains

[A2 cPanel Domain Features](https://www.a2hosting.com/kb/cpanel/cpanel-domain-features)

This is where you can add your domains, sub-domains, aliases, redirects, etc.

- [WordPress toolkit](https://www.a2hosting.com/kb/cpanel/wordpress-toolkit): there are 3 tabs on this page:
   - installations:
   - Plugins: Here you can see the list of all plugins installed on your WordPress installations - just use your admin area.
   - Themes: lists all the active and inactive themes you have loaded into your WordPress site(s) - seems useless, just use your Admin area to maintain them.
- **Domains**: Use this interface to manage your domains. For more information, read the [documentation](https://go.cpanel.net/Domains).
- **Zone editor**: DNS converts domain names into computer-readable IP addresses. Use this feature to manage DNS zones. For more information, read the [documentation](https://go.cpanel.net/zoneeditor). There are buttons for `A record`, `CNAME record`, `MS record`, and `Manage`.
- **Site publisher**: You can use this interface to quickly create a website from a set of available templates. This allows visitors to see some basic information while you continue to develop your website. Templates button did not work for me.
- **Redirects**: Self-explanatory. I currently add my redirects to the `.htaccess` file, though this interface is really good.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Applications

I can't find a link for this section in cPanel, though it the features seem to be under a heading of _Softaculous AppsInstaller_. There are too many here to go over one by one, so check the ones pertinent to you for how to use them.

**Scripts** (14 total): 

- WordPress, Woocommerce, WP Toastmasters, WPBeginner, WordPress + Elementor, WordPress + Unsplash, WordPress + Weglot, Drupal 7, Mattomo, CubeCart, CMS made simple, Joomla, b2revolution, MODX

**Categories** (23 total): 

- Blogs, Portals/CMS, Forums, Image Galleries, Wikis, Social Networking, Ad Management, Calendars, Mails, Polls and Analytics, Project Management, E-Commerce, ERP, Customer Support, Frameworks, Educational, DB Tools, Music, RSS, File Management, Others, Libraries, Mails
- you can install them on your main domain, subdomain, add-on domain

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Software

[A2 cPanel Software Features](https://www.a2hosting.com/kb/cpanel/cpanel-software)

- _Cloudflare_: no longer being support by A2.
- **PHP Pear Packages**: PEAR packages are collections of functions that allow you to perform tasks in PHP. You will need to install a PEAR package before you can use it inside a PHP program. Note: Packages are installed directly from the PHP Extensions and Applications repository (PEAR).
- **Optimize website**: Optimize the performance of your website by tweaking the way Apache handles requests.
- **Dropmysite**: got as 404 page when trying to access that link.
- **A2 website builder**: no thanks
- **Select PHP version**: It's very important to make sure you are not running an older version of PHP.
- **Setup Ruby app**: No clue about this one, check knowledge base.
- **WordPress manager by Softaculous**: Ehhh? Why not use the WordPress admin area?
- **Perl modules**: Perl modules are collections of functions that allow you to perform tasks in Perl. You will need to install a Perl module before you can use it inside a Perl program. Note: Modules are installed directly from the CPAN repository.
- **Application manager**: This feature allows you to register, manage, and deploy your custom applications using Phusion Passenger (?)
- **Softaculouus apps installer**: here is where you can install all of the scripts listed above 
- **Setup Node.js app**: Most likely you will not need this.
- **Setup Python app**: Same as above.

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Files

[A2 cPanel File Features](https://www.a2hosting.com/kb/cpanel/cpanel-file-features)

      <!-- Done to this point WTF? -->

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