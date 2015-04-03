# Introduction #

NGL dispatches Emails to your Users, Vendors, and Binders at various instances. For example: Check out slips to your Users, Purchase Orders to Vendors.
You can configure NGL to connect to any SMTP Server this also includes Gmail SMTP server.


# Pre-requisites #
  * Your NGL Server must have Internet Connectivity
  * NGL Server must be able to connect to your SMTP Server directly and not via a HTTP proxy
  * Library must have an account in the Mail Server and the Mail Server must support SMTP (Simple Mail Transfer Protocol)

# Procedure to configure #
  * Open mail.properties file present in C:/NewGenLibFiles/SystemFiles directory. If you are on Linux then it is /usr/NewGenLibFiles/SystemFiles. Open this file using a text editor
  * If the above file is not present then create a file mail.properties and edit this file
  * Note the below properties and edit them accordingly
If the below parameter is set to true then the Emails are dispatched otherwise Emails are not sent. Hence leave this parameter as true
```
send.email.online=true
```
If the below property is set then NGL will send a CC (Carbon Copy) of all the Emails mentioned in this property. You can also mention multiple Emails separated by a ,(comma). This is an optional property
```
default.cc=abc@xyz.com,pqr@xyz.com
```
If the below property is set then NGL will send a BCC (Blank Carbon Copy) of all the Emails mentioned in this property. You can also mention multiple Emails separated by a ,(comma). This is an optional property
```
default.bcc=abc@xyz.com,pqr@xyz.com
```
In the below property specify the IP Address or the host name of your SMTP Server
```
host=smtp.gmail.com
```
In the below property specify the Port of your SMTP Server
```
port=587
```
In the below property specify the username of your mailbox.
```
username=XXXXXX@gmail.com
```
In the below property specify the password of your mailbox.
```
password=XXXXXXX
```
In the below property specify the FROM Email using which you are sending Emails. This is usually the same value you used om username
```
from=XXXXXX@gmail.com
```
In the below property specify the FROM name you are sending Emails.
```
sender.name=ABC Library
```
In the below property specify whether you want to use TLS. If you are using Gmail then tls=true. You have your own SMTP server then usually tls=false
```
tls=true
```
  * Placing everything together, your mail.properties must look something like this.
```
send.email.online=true
host=smtp.gmail.com
port=587
username=XXXX@gmail.com
from=XXXX@gmail.com
password=XXXXX
sender.name=ABC Library
tls=true
```

  * Save your mail.properties
  * Close Apache Tomcat Server and Start it again