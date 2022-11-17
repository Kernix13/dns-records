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

I can't find a link for this section in cPanel, though the features seem to be under a heading of _Softaculous AppsInstaller_. There are too many here to go over one by one, so check the ones pertinent to you for how to use them.

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

The best features here are File Manager, Web Disk, Backup, Images, and Backup wizard. 

- [File Manager](https://www.a2hosting.com/kb/cpanel/cpanel-file-features/cpanel-file-manager): public_html is where all your website files go - you can create subfolders in here like `/blog` - he says don't use it because it's not that good but instead use an FTP account (this video is from 2017!) - You can browse directories, as well as copy, rename, and move files. You can upload and download files, and there are several ways to edit files
- **Directory privacy**: Set a password to protect certain directories of your account. When you enable this feature, a user that tries to open a protected folder will be prompted to enter a username and password before they can access your content - [docs](https://docs.cpanel.net/cpanel/files/directory-privacy/)
- **Web disk**: Create a Web Disk account to manage, navigate, upload, and download the files on your web server - [docs](https://go.cpanel.net/WebDisk)
- **Backup**: Download a zipped copy of your entire site or a part of your site that you can save to your computer. When you backup your website, you have an extra copy of your information in case something happens to your host - [docs](https://go.cpanel.net/Backup)
- **Git version control**: Create and manage Git™ repositories. You can use Git to maintain any set of files and track the history of changes from multiple editors - [docs](https://go.cpanel.net/GitVersionControl)
- **Images**: Modify and manage images that are saved to your account - [docs](https://docs.cpanel.net/cpanel/files/images/)
- **Disk usage**: Monitor your account's available space with the Disk Usage feature - [docs](https://go.cpanel.net/DiskUsage)
- **FTP accounts**: You can use an FTP client to manage your website’s files, you can use your home FTP account or create new accounts - [docs](https://go.cpanel.net/FtpAccounts)
- **Backup wizard**: The _Backup_ feature allows you to download a compressed copy of all or part of your website - the _Restore_ feature allows you to upload an existing partial backup file in order to restore parts of your website
- **Server rewind**: to restore files and databases on your web site. Using Server Rewind, you can restore a file, a set of files, or a database with just a few clicks - [docs](https://www.a2hosting.com/kb/cpanel/cpanel-file-features/server-rewind)

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Databases

[A2 cPanel Database Features](https://www.a2hosting.com/kb/cpanel/cpanel-database-features)

cPanel supports two of the most widely-used database systems, MySQL® and PostgreSQL. These database systems are complete SQL server and database solutions. You can interact with MySQL and PostgreSQL databases using a wide variety of programming languages, including PHP, Perl, and Python.

- **phpMyAdmin**: used to manage MySQL databases (phpMyAdmin) and PostgreSQL databases (phpPgAdmin) - You can create and drop tables, import and export data, execute SQL statements, repair tables, and much more - [docs](https://www.a2hosting.com/kb/cpanel/cpanel-database-features/phpmyadmin-and-phppgadmin)
- **MySQL Database Wizard**: create a new MySQL database
- **PostgreSQL**: - [How to manage PostgreSQL databases and users in cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-database-features/managing-postgresql-databases)
- **phpPgAdmin**: see link for phpMyAdmin. 
- **MySQL databases**: You can see a list of your current databases, as well as create and modify databases - [docs](https://docs.cpanel.net/cpanel/databases/mysql-databases/)
- **Remote MySQL**: Add a specific domain name to allow visitors to connect to your MySQL databases - [docs](https://go.cpanel.net/RemoteMySql)
- **PostgreSQL database wizard**: create a new PostgreSQL database

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Metrics

[A2 Using the Logging Features in cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-logging-features)

- **Visitors**: This function displays up to 1,000 of the most recent entries in the domain’s web server log
- **Bandwidth**: This function allows you to see the bandwidth usage for your site. It shows the current month’s bandwidth usage, as well as your total bandwidth usage
- **Awstats**: Awstats produces visual statistics about visitors of your site.
- **Webalizer**: Webalizer is a complex stats program that produces a variety of charts and graphs about who has visited your site
- **Metrics Editor**: This interface allows you to choose which stats programs you will use when viewing site statistics - Analog, Awstats, or Webalizer.
- **Errors**: The function displays the most recent entries in your website’s error logs in reverse chronological order. You can use this information to find broken links or problems with missing files - [docs](https://go.cpanel.net/Errors)
- **Raw Access**: Raw Access Logs allow you to see who has visited your website without displaying graphs, charts, or other graphics. You can use the Raw Access Logs menu to download a zipped version of the server’s access log for your site. This can be very useful when you want to quickly see who has visited your site
- **Analog stats**: Analog produces a simple summary of all the people who have visited your site. It is fast and provides great lightweight statistics. Analog shows the people who have accessed your site during a specific month. It provides limited content but can be helpful to see where your main users are from
- **Webalizer FTP**: Webalizer FTP is a complex stats program that produces a variety of charts and graphs about who has visited your site using FTP protocol
- **Resource usage**: [docs](https://www.a2hosting.com/kb/cpanel/cpanel-logging-features/latest-visitors-bandwidth-resource-usage) and [docs2](https://www.a2hosting.com/kb/cpanel/cpanel-logging-features/resource-limit-information)

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Security

[A2 cPanel Security Features](https://www.a2hosting.com/kb/cpanel/cpanel-security-features)

- **Autoinstall SSL**: check out [How to set up AutoSSL on your domain](https://www.a2hosting.com/kb/cpanel/cpanel-security-features/reconfiguring-autossl-on-domains)
- **IP Blocker**: This feature will allow you to block a range of IP addresses to prevent them from accessing your site. You can also enter a fully qualified domain name, and the IP Deny Manager will attempt to resolve it to an IP address for you
- **Manage API Tokens**: This feature lets you create and manage API tokens for cPanel API 2 and UAPI - Warning: The API Tokens feature is experimental [docs](https://go.cpanel.net/ManageAPITokensIncPanel)
- **Leech protection**: Leech Protect allows you to prevent your users from giving out or publicly posting their passwords to a restricted area of your site. This feature will redirect accounts which have been compromised to a URL of your choice
- **SSL/TLS Status**: You can use this interface to view the SSL status of your domains - [docs](https://go.cpanel.net/tlsstatus)
- **Imunify360**: With SSH keys, you can automate logins to your A2 Hosting account, or use two-factor authentication for increased security - Check out [How to use Imunify360](https://www.a2hosting.com/kb/cpanel/cpanel-security-features/imunify360)
- **SSH access**: Check out [How to configure SSH keys using cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-security-features/configuring-ssh-keys-with-cpanel)
- **SSL/TLS**: The SSL/TLS Manager will allow you to generate SSL certificates, certificate signing requests, and private keys
- **Hotlink protection**: Hotlink protection prevents other websites from directly linking to files (as specified below) on your website - Check out [How to configure hotlink protection in cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-security-features/hotlink-protection)
- **ModSecurity**: Check out [How to manage the ModSecurity module in cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-security-features/managing-the-modsecurity-module-in-cpanel)
- **Two-factor authentification**: Check out [How to set up two-factor authentication for cPanel](https://www.a2hosting.com/kb/cpanel/cpanel-security-features/two-factor-authentication-for-cpanel)

<div align="right">&#8673; <a href="#back-to-top" title="Table of Contents">Back to Top</a></div>

### Advanced

[A2 cPanel Advanced Features](https://www.a2hosting.com/kb/cpanel/advanced-features)

- **Teminal**: This interface provides command line access to your account on the server
- **Track DNS**: There are 2 input files, 
   - 1) _Domain Lookup_: allows you to find out the IP address of any domain, as well as DNS information about that domain. This can be a very useful tool right after your site is set up or after DNS changes have been made to make sure your DNS is setup properly. I assume it uses a tool like [whatsmydns.net](https://www.whatsmydns.net/)
   - 2) _Trace Route_: allows you to trace the route from the computer you are accessing cPanel from to the server your site is on (i.e. the number of servers and what servers your data must pass through to get to your site).
- **Error pages**: you can create a custom error page for any valid HTTP status code beginning in 4 or 5: 400, 401, 403, 404, 500 - Check out [docs](https://www.a2hosting.com/kb/cpanel/advanced-features/custom-error-pages)
- **MIME types**: to configure custom MIME types for your web site - Check out [How to configure custom MIME types in cPanel](https://www.a2hosting.com/kb/cpanel/advanced-features/mime-types)
- **Cron jobs** (for automation): This is an advanced feature and you better know what you are doing - Check out [How to set up cron jobs in cPanel](https://www.a2hosting.com/kb/cpanel/advanced-features/cron-jobs)
- **Indexes**: The “Index Manager” allows you to customize the way a directory appears when no index files reside in a directory (huh?, see below) - Check out [How to configure directory indexes in cPanel](https://www.a2hosting.com/kb/cpanel/advanced-features/index-manager)
- **Apache handlers**: Check out [How to configure custom Apache handlers in cPanel](https://www.a2hosting.com/kb/cpanel/advanced-features/apache-handlers)
- **Virus scanner**: -Check out [How to use Virus Scanner in cPanel](https://www.a2hosting.com/kb/cpanel/advanced-features/virus-scanner)

Example Index Files: 

```
index.php index.php5 index.php4 index.php3 index.perl index.pl index.plx index.ppl index.cgi index.jsp index.jp index.phtml index.shtml index.xhtml index.html index.htm index.wml Default.html Default.htm default.html default.htm home.html home.htm index.js
```

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