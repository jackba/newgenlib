## Why NGL Messaging Server? ##
The purpose of NGL Messaging Server is to assist your NewGenLib Server to send Emails(via SMTP) to your users. The question is "Can't NewGenLib Server dispatch Emails directly?". NewGenLib Server acts like a SMTP client and can send Emails to your Email server. However if you have HTTP proxy between NewGenLib Server and your Mail Server then NewGenLib Server fails to send emails via the HTTP proxy.

Hence in such cases where NewGenLib Server cannot send Emails to your EMail Server, you can take the assistance of NGL Messaging Server. NewGenLib Server sends Email via HTTP to the NGL Messaging Server and NGL Messaging Server dispatches the EMail to your Email Server using SMTP.
## Important pre-requisites in using NGL Messaging Server ##
Important pre-requisites to use NGL Messaging Server are
  * Your EMail Server must be available on the public domain or through a static IP. This is because NGL Messaging Server hosted on the web must be able to connect to your Email Server
  * Your Email Server must accept connections from NGL Messaging Server IP. It means, if your having a firewall protecting your Email Server make sure it allows NGL Messaging Server to connect
  * NewGenLib Server is connected to the Internet
## Getting started with NGL Messaging Server ##
### Step 1: Get Free Verus Subscription Id from Verus Solutions ###
Send your Organization name and Address and Contact Person's name to support@verussolutions.biz. Verus Solutions will assign a subscription Id for your organization. An email with Subscription Id and Password will be sent to you via Email.
### Step 2: Edit your SMTP Settings. ###
Open your Internet Browser and visit http://183.82.0.178/NGLMS/Admin/Home

[[File:Selection\_012.jpeg|thumb|left]]

Enter your Verus Subscription Id and Password.



[[File:Selection\_013.jpeg|thumb|left]]

Enter your SMTP Server Settings and click on "Submit" to save the settings. Also you can click on "Send Test Email" and enter an Email Id and test whether your settings are working

### Step 3: Edit your ENV\_VAR.txt ###
On your NewGenLib Server. Go to C:/NewGenLibFiles/SystemFiles (For Linux users go to /usr/NewGenLibFiles/SystemFiles). In this directory open the file ENV\_VAR.txt using your favourite text editor and enter these values



USE\_MESSAGING\_SERVER=YES

MESSAGING\_SERVER\_HOST=183.82.0.178

MESSAGING\_SERVER\_PORT=8080

MESSAGING\_SERVER\_ACCOUNT\_ID=<Place your Verus Subscription Id>

MESSAGING\_SERVER\_ACCOUNT\_PASSWORD=<Place your Verus Subscription Password>

If the above values are already available edit the existing values.

Save your ENV\_VAR.txt
### Step 4: If your NewGenLib Server is behind a proxy server make sure you have proxy.properties ###
If your NewGenLib Server is behind the proxy server make you have a file named proxy.properties in C:/NewGenLibFiles/SystemFiles directory (For Linux users /usr/NewGenLibFiles/SystemFiles). The proxy.properties file must have the following content

http.proxyUser=<Your proxy server user name>

http.proxyPassword=<Your proxy server password>

http.proxyHost=<Your proxy server host/ip address>

http.proxyPort=<Your proxy server port number>
### Step 5: Restart your NewGenLib Server ###
Finally for all the changes to get into place, please restart your NewGenLib Server (Apache Tomcat Server)