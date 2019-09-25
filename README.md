# nagios-msteams
A Nagios plugin to send notifications to MS teams

## prerequisites

These perl modules need to be installed.

 - HTTP::Request
 - LWP::UserAgent
 - JSON

## usage

`--webhook` is a required option when used from the command line
`--nagios_url` to add a link in the notification.

```
export NAGIOS_HOSTALIAS="hoge101" NAGIOS_SERVICEDESC="http" NAGIOS_SERVICESTATE="WARNING" NAGIOS_SERVICEOUTPUT="test output"
./nagios-msteams.pl --webhook 'https://your incoming webhook url'
```

## Nagios installation

1. place the script in nagios plugin directory
2. `chmod +x <path to Nagios plugin>/nagios-msteams.pl`
3. configure commands, contacts

## OMD/Check_MK installation

1. Place the script in `<check_mk home>/local/share/check_mk/notifications`
2. `chmod +x nagios-msteams.pl`
3. Reload OMD or Check_MK as appropriate
4. In WATO, create a machine user account, e.g. `msteams`
5. Configure a custom notification table for this user, and choose "nagios-teams.pl" as the Notification Method
6. Select "Call with the following parameters"
7. Enter your MS Teams Webhook URL as the first parameter

# Reference

https://docs.microsoft.com/en-us/outlook/actionable-messages/message-card-reference
