===================
WordPress Generator
===================

Overview
========

| The **WordPress Generators** is a classic generator of multi-page news blogs based on CMS WordPress templates and a content module developed by our team, allowing the selection of the most relevant and trustworthy content for each generation.
| Additionally, the safe page structure is assembled by a special algorithm that bypasses all known moderation triggers of advertising networks.

| Additional trust for safe pages created with this generator is due to the fact that websites based on CMS WordPress are widely used across the internet and in other advertising campaigns. Thus, the HTML code of safe pages is indistinguishable from the code of hundreds of thousands of real websites.
| Advertising platforms such as Google or Meta find it difficult to distinguish a safe page from a regular site created using this CMS from the mass of WordPress sites, even with the help of machine learning. This fact, coupled with other technologies, guarantees high pass rates during the moderation of advertising campaigns.

WordPress PHP
=============

| The WordPress PHP version differs from the WordPress HTML version by having a full emulation of the WordPress engine, as well as an emulation of the database and admin panel.
Since we use a modified version of CMS WordPress, which does not require installation on a server and hosting, nor working with a database, it only requires strict compliance with the system requirements, which can be found below.

System Requirements for WordPress PHP
-------------------------------------

* **PHP** version must be no higher than 7.4 or 7.4.X.

* Installed **NGINX** or **Apache** with the "mod_rewrite" module (when using Apache, it is recommended to switch PHP to FastCGI mode).

* Installed **PHP Data Objects (PDO)** extension.

* Installed **PDO_SQLITE** driver.

.. attention::

 PHP safe page files must be uploaded to the server or hosting only through an FTP client and placed in the root folder.

Possible Errors and Their Solutions
-----------------------------------

| 1. **There has been a critical error on this website** - this error indicates that the server or hosting does not meet the system requirements and file placement requirements. Additionally, check all settings or contact your server or hosting support to adapt the configuration to our requirements.

| 2. **Error establishing a database connection (this error does not exclude problems with system requirements)** - if this error occurs, check the following:

| `In the zip file -> /wp-include/version.php -> $wp_db_version = 51917`
| `In cpanel -> phpmyadmin -> table wp_options -> db_version`

| `In the zip file -> /wp-include/version.php -> $wp_version = 6.0`
| `In cpanel -> phpmyadmin -> table wp_options -> wp_version`

The versions in the safe page files and on your server/hosting must match.
If the problem persists or another error is received, check the server or hosting for compliance with the system requirements.

WordPress CMS
=============

This version of the WordPress generator is a full version of the CMS system, including all features and using as a database MySQL. This version supports installation of custom themes and plugins, allowing you to flexibly expand functionality and customize the appearance of the safe page.

System Requirements for WordPress CMS
-------------------------------------

* The **PHP** version must be 7.4, 7.4.X, or higher.

* A **MySQL** database version 5.7 or higher or a **MariaDB** database version 10.3 or higher.

* An active **HTTPS** protocol (SSL or TLS certificate).

* Enabled **PHP extensions**: MySQLi, curl, GD or ImageMagick, Multibyte String, JSON, XML.

* The PHP **memory_limit** must be 64 MB or higher.

Login Information for the Admin Panel
-------------------------------------

.. csv-table:: 
   :header: "Filed", "Value"
   :width: 10
   :align: center

   "**User**", `admin`
   "**Password**", `0!1#EHxp&K5{x9$%`
   "**Email**", `admin@wordpress.com`

How to Generate a Safe Page
===========================

**Step 1.** Select the **WordPress** generator on the generation page and choose a theme from the provided list in the corresponding "Theme" field that best suits your keywords or creative.

| **Step 2.** Enter the keywords and domain name in the corresponding fields.
| Keywords Example (separate by commas): `key, keyword1, keyword2`
| Domain Example: `https://example.com` or `example.com`

| **Step 3.** Click the **"Generate"** button, and after some time, a preview of the page will be displayed to you.
| If desired, you can regenerate the safe page to get a different design and content option.

**Step 4.** Click the **"Download"** button to get a ZIP archive with the ready-made safe page.

**Step 5.** Unpack the received ZIP archive and place it on your server or hosting.

