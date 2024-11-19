How to Upload a Finished Safe Page
==================================

There are several ways to upload a finished safe page to hosting. Each method varies in complexity and the necessary tools. Below you can read about each option and choose the most convenient one for yourself.

Setting Up a Safe Page via Hosting Control Panel
------------------------------------------------

The easiest method is uploading the safe page through the hosting control panel.
To do this, you need to identify which panel is used and follow the instructions below.

.. important::

 Before uploading a safe page to the hosting panel, make sure the domain you need is linked to the hosting.

**Uploading Safe Page Files via ispmanager:**

1. Open the hosting control panel.

2. Go to the "**Websites**" section, select the domain where you want to upload the safe page and then click on "**Website Files**".

3. Typically, after adding a domain in the hosting control panel parking page files are created in the website’s (safe page) folder. Delete all files in the folder except the **webstat** directory (if it exists), otherwise the safe page installation may not be performed correctly.

4. Click the "**Upload**" button. Select the safe page archive on your device and click "**Ok**".

5. Highlight the uploaded archive and right-click to select "**Extract**".

6. Ensure that the safe page files were extracted directly to the website directory, not into a subdirectory.

7. If necessary, move the safe page files to the root directory by selecting all files and using the "**Cut**" and "**Paste**" buttons.

8. Done! If everything is correct the uploaded safe page should be displayed when visiting your domain.

**Uploading Safe Page Files via Plesk:**

1. Open the hosting control panel.

2. Go to the "**Websites & Domains**" section and open the website folder.

3. Typically, after adding a domain in the hosting control panel parking page files are created in the website’s (safe page) folder. Delete all files in the folder except the **cgi-bin** directory, otherwise the safe page installation may not be performed correctly.

4. Click the "**Upload**" button. Select and upload the safe page archive from your device.

5. Select the uploaded archive and click the "**Extract Files**" button.

6. Ensure that the safe page files were placed directly in the website directory without additional subdirectories.

7. If files were extracted into a subdirectory, move them to the website directory. Go to the subdirectory, select the files you need and click the "**Move**" button. In the window that appears, select the website directory and click "**OK**".

8. Done! If everything is correct the uploaded safe page should be displayed when visiting your domain.

**Uploading Safe Page Files via cPanel:**

1. Open the hosting control panel.

2. In the "**Domains**" section select **Domains**.

3. Click the root folder of your website to enter the root directory.

4. Typically, after adding a domain in the hosting control panel parking page files are created in the website’s (safe page) folder. Delete all files in the folder except the **cgi-bin** directory, otherwise the safe page installation may not be performed correctly.

5. Click the "**Upload**" button.

6. Click "**Choose File**" or simply drag the safe page archive to upload it.

7. Highlight the uploaded archive and click the "**Extract**" button.

8. Enter the path to the directory (domain) where the files need to be extracted. Then click the "**Extract Files**" button.

9. Ensure that the safe page files were extracted directly into the website directory, not into a subdirectory.

10. Done! If everything is correct the uploaded safe page should be displayed when visiting your domain.

Setting Up a Safe Page Through an FTP Client
--------------------------------------------

FTP access is available for all hosting panels. In this instruction we will consider connecting and setting up a safe page via FTP protocol on the example of the most popular FTP client - FileZilla.

1. To work with this protocol you need to `download <https://filezilla-project.org>`_ and install the FileZilla client.

2. Start the client. In the **File** menu, go to **Site Manager...**.

3. In the window that opens, click on “**New Site**” and fill in the following fields:

* | *Host* - name of hosting server, IP address of hosting server or domain. Use domain only if it is bound to the hosting;

* | *Port* - you can leave it blank or specify the standard FTP protocol port - 21;

* | *Protocol* - FTP file transfer protocol;

* | *Encryption* - use explicit FTP over TLS if available;

* | *Logon Type* - normal;

* | *User* - your hosting login, e.g. **userGreg**;

* | *Password* - your hosting password, e.g. **password1234%**;

.. note::
 You can find the data for connection on the page of your hosting services in your cabinet or in the hosting settings.

4. After that, in the same window go to the “**Transfer Settings**” tab and specify the following settings:

* | *Transfer mode* - passive;

* | *Limit number of simultaneous connections* - check the box and specify the maximum available value in the “**Maximum number of connections**” field. When working via FTP protocol different servers have limitations on the number of simultaneous FTP connections from one IP address. Check the value with your hosting provider.

5. After that, click “**Connect**” button to connect to your hosting.

.. note::
 Usually, when using a VPS access is granted only to the root directory. If necessary you can configure the connection directory so that when connecting via FTP protocol, the required directory is opened immediately. 
 To do this go to the “**Advanced**” tab and in the **Default Remote Directory** field write the required path to the directory.

6. After connecting to the hosting you will see a divided window: on the left - the folder of your local device (Local site), on the right - the home folder of the hosting (Remote site). To manage a folder or file right-click on it.

7. In the **Remote site** line specify the path to the root folder where the safe page will be located. In the window on the left, right-click on the folder with the safe page on your device and select “**Download to server**”.

8. Done, if done correctly the uploaded safe page will be displayed when you navigate to your domain.

Setting Up a Safe Page via SSH network protocol
-----------------------------------------------

The most complicated way is to place the safe page on the server via the SSH (Secure SHell) network protocol. 
This way requires basic server skills, which will be described below.

.. important::
 | Before you start using SSH protocol, make sure that you have access to the server or hosting via this protocol. 
 | You will need the following data: **ip**, **user** and **password**.

**Setting up safe page files on LINUX server with Ubuntu distribution, on Nginx web server:**

Nginx web server installation:

1. Access the server using the command: ``ssh ip@user``

2. Obtain **root** permissions using the command: ``sudo -i``

3. Update packages using the command: ``sudo apt update``

4. Install Nginx using the command: ``sudo apt install nginx``

5. Check Nginx status using the command: ``systemctl status nginx``

6. You should get: **Active: active (running)**. If status is not active, write the following command: ``systemctl restart nginx``

7. Done, Nginx is installed correctly and is in an active state.

Settin up a safe page on the server:

The easiest and most basic way to place files is Secure Copy Protocol, aka SSH File Transfer. 
Placing a static site (safe page) is always done in the directory **/var/www/** using the command: ``scp -r ~/path/to/folder ip@user:/var/www/``

Nginx and domain configuration:

.. important::
 To map your safe page to a domain, you need to set a set of rules for Nginx.
 Your actual domain must be bound to the current server using DNS.

In the instructions below you need to replace ``domain.com`` with your domain name.

1. You need to replace your safe page to the following directory: ``/var/www/domain.com``

2. Basic domain configuration:
::
   server {
     server_name domain.com www.domain.com;

     location / {
       root /var/www/domain.com;
     }
   }

You need to write this configuration in the following path: ``/etc/nginx/sites-available/domain.com``

.. note::
 You can find commands for interacting with the server file system in the tables below.

3. You need to do symlink configuration using the command: ``ln -s /etc/nignx/sites-available/domain.com /etc/nginx/sites-enabled/``

4. The final step is to restart Nginx using the command: ``systemctl restart nginx``
 
**Commands for interacting with the file system and editing server files.**

.. list-table:: Basic Linux commands
   :header-rows: 1
   :stub-columns: 0

   * - Command
     - Description
   * - ``cd``
     - | The command allows you to navigate through the directories of the file system.
       | Example: ``cd /var/www``
   * - ``ls``
     - | The command allows you to view all available folders and files in the current directory.
   * - ``mkdir``
     - | The command allows you to create folders within a directory.
       | Example: ``mkdir new-folder``
   * - ``rm``
     - | The command allows you to delete folders or files.
       | Deletion example: ``rm file``
       | Deletion example of files inside a folder (recursive): ``rm -rf folder``
   * - ``cp``
     - | The command allows you to copy folders or files.
       | Copy example: ``cp file newfile``
       | Copy example of files inside a folder (recursive): ``cp -r folder new-folder``
   * - ``mv``
     - | The command allows you to move folders or files.
       | Example: ``mv folder new-folder``
   * - ``cat``
     - | The command allows you to read data from a file. This command allows you to write a file from the clipboard.
       | 1. Open a record to a file: ``cat >>file``
       | 2. Paste text from the clipboard: keyboard shortcut **Ctrl + v** (WIN) or **Cmd + v** (MacOS)
       | 3. To close the record: press the keyboard shortcut 2 times **Ctrl + d**


.. list-table:: Commands for the Vim text editor
   :header-rows: 1
   :stub-columns: 0

   * - Command
     - Description
   * - ``vim file``
     - | The command allows you to open or create a file.
   * - ``i``
     - | The command allows you to switch to the interaction mode.
   * - ``esc``
     - | The command allows you to exit any mode.
   * - ``:w``
     - | The command allows you to save a file.
   * - ``:wq``
     - | The command allows you to save and exit a file.
   * - ``:q``
     - | The command allows you to exit a file.

.. csv-table:: Commands for the Nano text editor
   :header: "Command", "Description"

   "``nano file``", "The command allows you to open or create a file."
   "``Ctrl + x``", "| The command allows you to save and exit a file.
   | Nano will ask you to confirm the action: select ``y``
   | Nano will ask for the name of the file: press **Enter**"

**Possible errors and their solutions.**

If you see a white screen or PHP related error when opening a domain, you should do the following:

1. Check for PHP and PHP-FPM modules using following commands: ``php -v`` и ``php-fpm -v``

2. If one of the modules is missing, you will get the following: ``Command 'php' not found, but can be installed with:``

3. The missing modules need to be installed:

| PHP installation - ``sudo apt install php``

| PHP-FPM installation (Fastcgi) - ``sudo apt install php-fpm``

4. Domain configuration with PHP-FPM:
:: 
   server {
     server_name domain.com www.domain.com;

     location / {
       root /var/www/domain.com;
       index index.php index.html;
     }

     # pass the PHP scripts to FastCGI server
     location ~ \.php$ {
       fastcgi_pass "unix:/var/run/php/php8.1-fpm.sock";
       fastcgi_index index.php;
       fastcgi_param  SCRIPT_FILENAME  /var/www/domain.com$fastcgi_script_name;
       include fastcgi_params;
     }
   }

You must write this configuration to the following directory: ``/etc/nginx/sites-available/domain.com``

5. You need to do symlink configuration using the command: ``ln -s /etc/nignx/sites-available/domain.com /etc/nginx/sites-enabled/``

6. The last step is to restart Nginx: ``systemctl reload nginx``