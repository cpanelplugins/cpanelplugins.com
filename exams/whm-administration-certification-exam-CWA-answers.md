# WHM Administration Certification Exam (CWA) Answers 2022

Given the following options, which indicates the ideal source from which you should obtain your server's resolver IP addresses?

- Your hosting provider or data center.

---

Within which of the following WHM interfaces would you perform a graceful restart of the nameserver software?

- WHM Home &gt;&gt; Restart Services &gt;&gt; DNS Server

---

Which of the following types of DNS cluster synchronization found in WHM can be best described as the copying of one updated zone file to the current server, based on the value you provide as the domain you wish to synchronize?

- Synchronize one zone to this server only.

---

When you use the supported 1:1 NAT setup in WHM, the List Accounts interface in WHM will display which of the following values in each accounts' listed IP address column?

- The public IP address.

---

Which of the following can be described as having the following major strengths?<br>Very high performance. Low memory footprint.

- PowerDNS

---

Which of the following most accurately describes what happens when a domain with two NS records in its zone is queried?

- Both records are returned.

---

Which of the following options accurately indicate a task that can be performed from within the WHM interface?

- Change an MX record.

---

Within which of the following WHM interfaces would you select the nameserver software that you wish to use?

- WHM Home &gt;&gt; Service Configuration &gt;&gt; Nameserver Selection

---

Yudith runs a small web-hosting company. She has added and removed several zones manually but has accidentally deleted a zone belonging to a cPanel account. Fortunately, this zone did not contain any custom records.

Given the situation, which of the following WHM interfaces should she utilize to re-create the zone?

- WHM » DNS Functions » Add a DNS Zone.

---

Which of the following statements most accurately describes the term clustering, in the context of a server hosting environment?

- Two or more servers that all serve the same purpose configured in a distributed, connected environment.

---

By default, cPanel creates SPF records in which of the following modes?

- Development mode (non-production)

---

Which of the following statements accurately describe a situation in which DNS zone templates would be useful, in a cPanel &amp; WHM environment?

- Any time that similar customizations are needed across all hosted accounts.

---

Which of the following options indicates what the abbreviation TTL stands for, in the context of DNS?

- Time To Live; indicating how long a resource record should be cached.

---

Which of the following described situations would utilize DNS resolution as a key component of its handling?

- To determine where to send mail for a domain.

---

Nameserver address record setup in modern installations of cPanel &amp; WHM, both within the Basic WHM Setup and Edit Reseller Nameservers and Privileges interfaces, provide support for certain DNS records associated which of the following types of hostnames?

- Hostnames that resolve to AAAA records.

---

Which of the following options best describes the behavior that occurs when a zone contains no MX records?

- The A record is used to determine where mail should be sent.

---

Diego is a web designer who operates his own cPanel &amp; WHM server. He wants to create a test subdomain for one of his clients and upload some web content to it so that he can share a "beta" (non-production) version of the site to his client.

Which of the following interfaces should he start with, in order to accomplish this?

- cPanel » Domains » Subdomains

---


Which of the following options best describes the term recursive, in the context of DNS?


- A recursive nameserver can resolve non-local domains.

---


The following options found in the Exim Configuration Manager - Basic Editor interface in WHM enables the checking of DNS resolution to see if the sender's domain exists?

- Sender Verification Callouts

---

Which of the following statements best describes the term resolver?

- A nameserver that can resolve non-local domains.

---

Which of the following terms can be described as the way that permissions are handled inside a MySQL or MariaDB database?

- Grants

---

Which of the following columns, found in the WHM Home &gt;&gt; SQL Services &gt;&gt; Show MySQL Processes interface, indicate the actual query being executed by the indicated process?

- info

---

Which of the following is one of the most common causes of MySQL upgrade failures?

- The my.cnf file contains a number of non-default customizations that have not been verified prior to upgrading.

---

Which of the following MySQL storage engines is the native default (native to MySQL - not necessarily in cPanel &amp; WHM) engine used by MySQL versions 5.5.5 and above?

- InnoDB

---

Which of the following types of tables can you repair using the Repair a MySQL Database interface, found in WHM?<br>

- MyISAM

---

Which of the following best describes the MySQL root password's role in a cPanel &amp; WHM environment?”

- A password that is primarily handled via automated means by cPanel &amp; WHM back-end services and can be reset as needed.

---

Ananya has a website that writes data into a MySQL database. She was mail-bombed, and as a result, has gone over the quota that was set for her account by the WHM server administrator. Which of the following best describes what happens to her website now?

- It continues operating normally and no production impact is seen.

---

In a cPanel &amp; WHM environment, which of the following MySQL storage engines is set as the default?

- MyISAM

---

Which of the following MySQL/MariaDB-related terms describe a data structure that improves operations' speed in a table accurately?


- Index

---

The WHM Home &gt;&gt; SQL Services &gt;&gt; Additional Access Hosts interface creates server-level grants that are similar to the grants that can be created in which of the following cPanel account-level Interfaces?

- cPanel Home &gt;&gt; Databases &gt;&gt; Remote MySQL

---

Given the following options, which accurately describe a feature specific to the MyISAM storage engine?

- MyISAM has repair capabilities that allow you to perform the REPAIR query, either directly or from the WHM interface, on tables that may have corrupted data or indexes.

---

Which of the following definitions best describes InnoDB's data dictionary component?

- A part of the InnoDB storage engine that uses metadata to map structural information to the file it’s stored in.

---

Which of the following options describes an actual benefit of utilizing remote MySQL capabilities using the MySQL Profiles feature in WHM?

- Remote MySQL servers can reduce load on the WHM Server.

---

Which of the following actions can you perform directly from within the WHM interface, without using phpMyAdmin?

Change a database user's password.

---

MySQL Profiles can set up what kind of relationship between servers

- 1-to-1 (1:1) only

---

Which of the following database-related terms defines marking a table or row so that only one process can access it a time?”

- Locking

---

Given the options below, which of these accurately indicate a point during WHM user interactions, which triggers the system to create grants for all pre-existing cPanel accounts, is based on the configurations set within the Additional MySQL Access Hosts interface?

- When the user clicks the link at the bottom of the Additional MySQL Access Hosts interface labeled "click here".

---

Which of the following details about the remote server would you need to know, if you wanted to set up a new remote MySQL profile in WHM?

- Remote SSH port

---

What language is used to add, remove, and view data in a MySQL/MariaDB database?

- SQL

---

Which of the following options indicate the correct number of characters that a MySQL 4.1 password contains before being updated to the current standard of 41 character-hashes?”

- 16 characters.

---

In a cPanel &amp; WHM environment, which of the following options accurately describes what the system default PHP version setting defined in WHM's MultiPHP Manager interface represents?<br>The version that is used if a domain does not already have a specific version selected for it.

---

Which of the following accurately indicates the user that processes created for the DSO handler are owned by?

- nobody user

---

Besides increasing the speed of the build process, which of the following options describes another reason that EasyApache 4 provides an improvement over EasyApache 3

---

- Reduced chance of critical Apache failures.

---

In modern installations of cPanel &amp; WHM, how is the PHP version determined for newly created accounts, when System PHP-FPM status is set to ON?

- It is set to the same value as the system default.

---

During PHP requests, which of the following statements accurately describes how the DSO handler processes the request?

- PHP handling operates internally by Apache's own processes.

---

Which of the following options accurately indicates the file syntax that can be seen within downloaded EasyApache 4 profiles?

- JSON

---

Which of the following options is NOT a real Multi-Processing Module (MPM) available for installation within WHM's EasyApache 4 interface?

- Postfork

---

Which of the following options best describes the method you would use to install the PHP-FPM software, within a cPanel &amp; WHM environment?

- PHP-FPM appears under the PHP Extensions stage of the EasyApache 4 profile customization walkthrough.

---

Given the following options, select the components or component combinations that would provide standard per-user process ownership for handling PHP content.

- suPHP (mod_suphp) OR Ruid2 (mod_ruid2) OR PHP-FPM

---

In modern installations of cPanel &amp; WHM, which of the following PHP configuration values are set automatically during the Initial Setup Assistant steps?

- memory_limit

---

Which interface can be used to set a virtual host's PHP version?

- WHM only

---

Which of the following options describes the appropriate method needed to enable PHP-FPM from within the WHM interface?

- PHP-FPM is enabled via WHM's MultiPHP Manager interface.

---

What types of packages do EasyApache 4 rely on to install modules and extensions, when provisioning an EasyApache 4 profile?

- RPM packages.

---

Which of the following EasyApache 4 profile actions can you perform from WHM's EasyApache 4 interface, in modern installations of cPanel &amp; WHM?

- Upload a profile file from your file system or via a URL.

---

You're operating in a PHP 5.6 environment and using DSO as your PHP handler. You've created a .user.ini file in your website's public_html folder, but are not seeing your changes reflected.

Of the following choices, which of these most accurately describes the issue that is occurring here?

- An .htaccess file stored in public_html should be used instead, containing the appropriate syntax for declaring PHP values.

---

Which of the following options best describes the procedure needed to enable the BlueHost SymLink Protection Patch?<br>


- Toggle the corresponding option found in WHM's Apache Configuration's Global Configuration interface.

---

Which of the following options accurately describes an action one performs in WHM's EasyApache 4 interface?”

- Install new PHP extensions for use in your active Apache/PHP environment.

---

Which of the following Apache modules are core to Apache and can be disabled, but cannot be removed using the EasyApache 4 interface?

- mod_userdir

---

Which of the following PHP handlers works on only one PHP version at a time?

- DSO

---

If a user wants to utilize the system default version of PHP, which of the following selections would they enable for their account?

- inherit

---

If the mail server defers a message, what did it do to the message?

- Delayed it.

---

Which of the following options best describes what is indicated by the act of a mail server "relaying" its mail?

- It is handing mail off to another mail server for delivery.

---

In which WHM interface can you configure the forwarders for the root, cPanel, and nobody mail accounts?

- WHM Home » Server Contacts » Edit System Mail Preferences

---

Given the following options, which accurately describe the Mail Troubleshooter interface's behavior, found in WHM?

- It does not send an actual test message but simulates sending one.

---

Given the following options, which best describes something about an email address that can be determined by using the WHM Home » Email » Mail Troubleshooter interface, found in WHM?

- It will indicate whether the destination address forwards mail to a remote server.

---

Given the following options, which of these accurately describe the behavior of the Mail Troubleshooter interface, found in WHM?

- It can report the remote or local server that Exim uses to hand off messages for a specific email address.

---

When mail is delivered to "/dev/null”, which of the following statements accurately indicate what happens to the message?

- The message has been permanently deleted.

---

Which of the following options best indicate a legitimate reason that would describe why you would want to configure the forwarder address fields within the WHM Home » Server Contacts » Edit System Mail Preferences interface?

- To prevent emails destined for "root" from getting frozen within the mail queue.

---

Which of the following mail diagnostics are available within the WHM interface, and can help you troubleshoot mail?

- A diagnostic tool that provides a telnet-like interface, allowing you to manually reproduce the SMTP process.

---

If there is a long delay indicated when an email is being sent, the Mailer Daemon will send a warning message to which of the following destinations?

- The email's sender.

---

The following options found in the Exim Configuration Manager - Basic Editor interface in WHM enables the contact of the sender's mail server to see if the sender exists?

- Sender Verification Callouts

---

Which of the following Mail interfaces in WHM can provide you with a historical snapshot of the mail queue?

- Mail Delivery Reports

---

Which of the following options describes one of the commonly known characteristics, though are not always indicative, of an average spam email message?

- The message contains an attachment.

---


Within which of the following WHM interfaces would you look to determine why the system did not deliver an email message?

- Mail Delivery Reports

---

You can use the Exim Configuration Manager - Basic Editor to configure Exim to deliver mail without scanning messages based on which of the following criteria?

- When the message is over a certain size.

---

Justine's boss just told her that the authentication daemon for the mail server is broken. Which of the following options best indicates the component of the mail system that is affected by this?

- The component that validates user credentials.

---

cPanel & WHM allows you to choose whether mail should be held in the queue or returned to sender when the recipient's mailbox meets which of the following criteria?

- Exceeds its assigned quota.

---

Which of the following tools may help you to resolve issues indicated by the time moved backwards warning?

- The "Sync Time" tool in WHM »Server Configuration » Server Time

---

Which of the following options describes one of the commonly known characteristics, though are not always indicative, of an average spam email message?

- The message has a "Reply-to" address defined.

---

All mail from a specific user is neither delivered to the inbox nor bounced. When you check the WHM Home » Email » Mail Delivery Reports interface, you see a funnel-shaped icon next to the message. Which of the following options best describes what this probably indicates?

- The message was likely rejected at SMTP-time due to spam-like characteristics.
