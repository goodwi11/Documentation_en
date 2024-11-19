How to Upload a Finished Safe Page
==================================

There are several ways to upload a finished safe page to hosting. Each method varies in complexity and the necessary tools. Below you can read about each option and choose the most convenient one for yourself.

Uploading a Safe Page via Hosting Control Panel
-----------------------------------------------

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
