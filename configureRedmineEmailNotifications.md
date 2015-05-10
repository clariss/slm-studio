Sign in as administrator in Redmine. Then:
  * go to Administration / Settings / Incoming Emails
  * Tick box Enable WS for incoming emails
  * Click on button Generate Key (the key generated will be used in the redmine alias below, replacing GeneratedByRedmine

Add redmine user, so an email inbox is created for redmine
```
adduser --no-create-home --disabled-password --disabled-login redmine
```
Edit email aliases:
```
vi /etc/aliases
```
Add redmine alias:
```
redmine: "|/usr/share/redmine/extra/mail_handler/rdm-mailhandler.rb --url http://slmstudio.dyndns.org/redmine --tracker support --project support --priority normal --allow-override priority --key GeneratedByRedmine>"
```
Re-start mail server
```
newaliases
/etc/init.d/postfix restart
```

In Redmine, add new user as follows (replace email by the one used by Nagios to send notifications):
```
Login: nagios
First Name: Nagios
Last Name: Email Notifications
E-mail: nagios@slmstudio.dyndns.org
```

In Redmine, add new project as follows:
```
Name: Support
Identifier: support
Trackers: Support
Modules: Issue tracking
```

In Centreon, go to Configuration > Commands > Notifications.Add new notification command:
```
Command Name: service-raise-incident
Command Type: Notification
Command Line: /usr/bin/printf "%b" "Priority: Immediate\nStatus: New\n\n SLM Studio Automated Notification\n\nNotification Type: $NOTIFICATIONTYPE$\n\nService: $SERVICEDESC$\nHost: $HOSTALIAS$\nAddress: $HOSTADDRESS$\nState: $SERVICESTATE$\n\nDate/Time: $DATE$ Additional Info : $SERVICEOUTPUT$" | @MAILER@ -s "Host: $HOSTALIAS$ - Service: $SERVICEDESC$ - Status: $SERVICESTATE$" $CONTACTEMAIL$
```

In Centreon, go to Configuration > Commands > Notifications.Add new notification command:
```
Command Name: host-raise-incident
Command Type: Notification
Command Line: /usr/bin/printf "%b" "Priority: Immediate\nStatus: New\n\n SLM Studio Automated Notification\n\nNotification Type: $NOTIFICATIONTYPE$\nHost: $HOSTNAME$\nState: $HOSTSTATE$\nAddress: $HOSTADDRESS$\nInfo: $HOSTOUTPUT$\nDate/Time: $DATE$" | @MAILER@ -s "Host: $HOSTNAME$ - Status: $HOSTSTATE$" $CONTACTEMAIL$
```

In Centreon, go to Configuration > Users > Contacts / Users. Add a new user (replace email by the address in which Redmine will receive emails:
```
Full Name: Redmine
Alias/login: redmine
Email: redmine@slmstudio.dyndns.org
Host Notification Commands: host-raise-incident
Host Notification Options: Down, Unreachable, Recovery
Service Notification Commands: service-raise-incident
Service Notification Options: Warning, Critical, Recovery
```

Verify that email from command line works:
```
/usr/bin/printf "%b" "Priority: Immediate\nStatus: New\n\n Noticication from command line" | /usr/bin/mail -s "Notification subjct" foo@gmail.com
```

Raise incident from command line:
```
/usr/bin/printf "%b" "Priority: Immediate\nStatus: New\n\n Noticication from command line" | /usr/bin/mail -s "Notification subjct" redmine@slmstudio.dyndns.org
```
Note that Linux user must be "nagios", as this is the user configured in Redmine to receive email. See latest logfile to see mail status.



references:

http://www.llamabyte.com/2011/configure-redmine-to-receive-emails-with-sendmail/

http://www.redmine.org/projects/redmine/wiki/RedmineReceivingEmails