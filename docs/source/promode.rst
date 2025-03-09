=================
Professional Mode
=================

.. attention::
 The mode is only available with an active **Professional** or **Business** subscription!

Professional Mode is an advanced feature available for Professional and Business subscriptions. It unlocks additional customization options for safe page generation, allowing users to fine-tune safe page content, integrate tracking tools and improve compliance with advertising network rules.

Settings Description
====================

**Page Customization Settings (Additional Settings)**
-----------------------------------------------------

These settings provide greater control over how the safe page is structured and complience with advertising campaign: 

| 🏷️ **Safe Page Title** – allows you to set a custom title of the safe page.
| Example: `Example Safe Page`

| 🔑 **Keywords** - allows you to set keywords for integration into safe page. Separate with commas.
| Example: `key, keyword1, keyword2`

| 🔗 **Redirection Link** – allows you to set a URL that buttons or forms on the safe page will redirect to.
| Use Case: directing users to a landing page, affiliate offer or another safe page.

| 📂 **Rename Index File** – allows you to set the name of index file.
| Default: `index.html`
| Example: `page.html`

**Legal & Compliance Settings (TOS&Privacy Settings)**
------------------------------------------------------

These settings allow you to customize the Terms of Service (TOS), Privacy Policy and Cookies pages: 

.. list-table::
   :header-rows: 1
   :stub-columns: 1

   * - Setting
     - Description
     - Example
   * - 🌎 **Domain Name**
     - Inserts the domain name into TOS&Privacy pages.
     - `https://example.com` or `example.com`
   * - 🏢 **Company Name**
     - Inserts the company name into TOS&Privacy pages. 
     - `Stratton Oakmont Ltd.`
   * - 📞 **Phone Number**
     - Inserts the phone number into TOS&Privacy pages.
     - `+1 (800) 999-9999`
   * - 📧 **E-mail**
     - Inserts the e-mail into TOS&Privacy pages. 
     - `support@example.com` 

.. important::
 Make sure the provided **Company Name**, **Domain Name** and **Contact Info** match your advertising campaign information to avoid compliance issues.

.. | 1. "``Domain Name``" - domain name to integrate into TOS&Privacy.
.. | Example: *https://example.com* или *example.com*

.. | 2. "``Company Name``" - company name to integrate into TOS&Privacy.
.. | Example: *Stratton Oakmont*

.. | 3. "``Phone Number``" - phone number to integrate into TOS&Privacy.
.. | Example: *1(800)999-99*

.. | 4. "``E-mail``" - Email to integrate into TOS&Privacy.
.. | Example: *stratton.oak@mail.com*

**Cloaking Integration**
------------------------

These settings allow you to integrate cloakers and edit index file extension:

| 🎭 **Cloaking** - allows you to select a cloaker for integration.

| 📄 **File Extension** - selects the format of index file extension for compatibility with cloaking systems.
| Default: `.html`
| If using Adspect Cloaking: `.php is automatically applied`

**Custom Code & Tracking (Code Integration)**
---------------------------------------------

This section enables you to insert custom scripts, analytics tools or tracking pixels into safe pages:

| 📊 **Pixel** - allows you to add conversion tracking pixels (e.g. Facebook Pixel, Google Ads, or custom tracking scripts).

| 📝 **Custom Code in <head>** – allows you to add JavaScript, meta tags or CSS inside the ``<head>`` of the safe page.

| 📍 **Custom Code to the start of <body> tag** - allows you to add code into the safe page after ``<body>``.

| 📍 **Custom Code to the end of <body> tag** - allows you to add code into the safe page before ``<body>``.