# cPanel In-Depth

Subjects I have experience with:

- phpmyadmin, mysql, redirects, mx entry, ssh/tls, cron jobs, dns,

Links:

1. https://websitesetup.org/beginners-guide-to-cpanel/
2. https://www.hostinger.com/tutorials/cpanel/
3. https://rshweb.com/cpanel-beginners-guide

## General

- cPanel is a Linux-based web hosting control panel
- features that automates the process of hosting a website
- It can only be installed in Linux servers, it supports CentOS, RHEL and CloudLinux operating software
- most of the Linux webhosting servers use cPanel to host and manage websites on their servers

## Link 1

- https://websitesetup.org/beginners-guide-to-cpanel/
- a control panel where you can manage every element of your web hosting account
- Connect domain names to your hosting. Set up emails for your site. Install WordPress (or another content management system). Back up your website. Upload files to your server. Check your bandwidth and other usage stats. Change various security settings. Install add-on apps on your server. Create new databases/manage existing ones. Set up various optimizations.
- The `search` field allows you to find the key options within cPanel

### Preferences

1. Password & Security: the first thing ytou should do is change your password to something "normal" rather than use the hosting company's randomly generated PW
1. Contact Information: if you need to change the contact email address
1. User Manager: Click the Add User button when you want someone help you manage your website(s). Each person will require their own user profile in cPanel

- You can see all accounts that are currently set in your cPanel
- The _envelope_ icon indicates if the person has an email account set up in the system
- The _truck_ icon indicates if the person has an FTP account
- The _disk_ icon indicates if the user can use the web disk services

### Domains

> stopped at Managing Domain Names

1.

## Link 2

## Link 3

## Video cPanel Mastery Course 2022

- https://youtu.be/b1TfeJbU9I0?si=0MGdlXIUZjjPCUsF

### How to create a MySQL DB and insert data into it

1. Got to Databases > MySQL Databases > Create Database > add db name input field
2. or go to Databases > MySQL Database Wizard > add db name input field
3. NOTE: it will be prefixed with your domain name
4. create a Username which is who has access to the DB
5. create a PW but click on Password Generator then copy that info - click Create User
6. add the user to the DB - select ALL PRIVILEGES > click Next Step

> NOTE: your user name is also prefixed with the domain name - for me it looks like the DB name and username values are the same

phpMyAdmin

- this takes you to a screen where you can see and interact with all your DBs
- for WP, some plugins create tables and you can edit the data in those tables
- going in here is useful if you get locked out of your website -
- for example, go to wp_users >

### How to use Awstats

- Google Analytics gives you a more granular view
- there are nuggets that Awstats gives you that GA does not
- you can get the KWs that people are using in search engines to find you
- you can find who is liniing to your for good or bad reasons

Other Stats icons:

- `Visitors`: tells you every IP address of visitors and the file they are accessing
- `Errors`:
- `Bandwidth`: how many MB or GB your users/visitors are using
- `Raw Access`:
- `Analog Stats`:
- `Webalizer`:
- `Webalyzer FTP`:
- `Metrics Editor`:
- `Resource Usage`:

Awstats:

- you can seee the days and the visits per day - when to publish, when to send auto emails
- you can see the duration - how long are people statying on your site
- IDIOT DOESN'T SHOW ANYTHING
- look for people linking to my pages
- you can also see the search phrases

## Softaculous

- it is a suite of popular scripts that you can build into your website
- WP, Joomla, Forums - all free

## Setup Error and Redirect Page

- 404 error page - or redirect all the traffic to a specific page like a landing page
- Go to Advanced > Error Pages - choose 404 and then enter HTML (Whaaat?)
- `content="0"` means to redirect right away

## File Manager

- `httpdocs` or `public_html`

## Email Authentication

- protect your email from spam
- Email > Apache SpamAssassin - I don't have that, I have `Spam Filters`
  - look into Blacklist
- Email > Authentication - I don't have that - it helps prevent spam -
  - Enable DKIM and SPF, helps protect your email
  - Check under Email Deliverability

## Backup and restore

- frequently backup your website - consider having a local backup
- do when you move to a new host
- Backup and Backup Wizard -

Backup:

- allows you to d\l a FULL backup onto our computer
- from your server to your computer
- or better - just d\l what's in the home directory, w\o emails and DBs
- or just d\l the DBs or just the emails

Backup Wizard:

- the full backup can be stored on your server where above it's only on your local machine - but you have the option to also d\l onto your machine
- it moving to another host, you can ask them to log in and d\l into their server

Click on restore if you have a copy
