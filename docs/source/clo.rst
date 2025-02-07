Cloaker Integration
====================

Adspect Cloaking
----------------

One of the undeniable advantages of Comsign tools has been and remains the collaboration with Adspect – a cloud service designed to protect online advertising campaigns from unwanted traffic. Thanks to this collaboration, not only can you use a single account in both interfaces, but it also allows you to reduce the entire process of cloaking integration with the generated page to a couple of clicks, following our main concept - extremely simple and extremely effective. All our generators are capable of automatically integrating the stream into the generated pages.

| **How to generate a safe page with Adspect cloaking stream:**

| 1. Create a stream, specifying the action "No action" in the safe page settings.

| 2. Skip the page with integration instructions.

| 3. In the generator, select the stream for integration from the list and click the "Generate" button.

| 4. If the result suits you – click the "Download" button to get a ZIP archive with the already integrated cloak. Then you just need to "unpack" the archive and place it on your server.

Other Cloakers
--------------

Despite Adspect's cloaking usability and automatic integration of safe pages with any stream, you always have the option to integrate our safe pages with any other cloaking manually using reverse PHP integration.

| **How to integrate any cloaking with Comsign safe pages:**

| 1. Move the cloaking filter file to the safe page folder, e.g. *filter.php*

| 2. Write the first line in the *index.html* file the name of your filter file as follows:
| ``<?php require __DIR__ . '/filter.php' ?>``

| 3. Rename the file *index.html* to *index.php*

.. note::
     When manually integrating Adspect cloaking, you must also select **"Local file"** in the **"Action"** field in the stream settings.

