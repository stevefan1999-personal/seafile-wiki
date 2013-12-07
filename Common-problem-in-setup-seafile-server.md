#### Failed to upload/download file online

* Check your SERVICE_URL setting in ccnet.conf and HTTP_SERVER_ROOT setting in seahub_settings.py
* Make sure you firewall for seafile httpserver is opened.
* Using chrome/firefox debug mode to find which link is given when click download button and what's wrong with this link

#### When downloading a library, the client hangs at "connecting server"

First, you can check the ccnet.log in client (~/.ccnet/logs/ccnet.log for Linux, C:/users/your_name/ccnet/logs/ccnet.log for Windows) to see what's wrong.

Possible reasons:

* Miss config of  <code>SERVICE_URL</code>: Check whether the value of is set correctly in server's <code>ccnet.conf</code>.
* Firewall: Ensure the firewall is configured properly. See [[Firewall Settings for Seafile Server ]]

Trouble shooting:

* Manually telnet to see if you can connect: <code>telnet your-server-IP-or-domain 10001</code> 


#### Error on Apache log: "File does not exist: /var/www/seahub.fcgi"

Make sure you use "FastCGIExternalServer /var/www/seahub.fcgi -host 127.0.0.1:8000" in httpd.conf or apache2.conf, especially the "/var/www/seahub.fcgi" part.