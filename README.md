# OpenShift RoundCube Quickstart

Roundcube webmail...

```
...is a browser-based multilingual IMAP client with an application-like user interface. It provides full functionality you expect from an e-mail client, including MIME support, address book, folder manipulation, message searching and spell checking.
```

This Quickstart has an accompanying blog post [How To Setup Your Own Free Mail Server](https://openshift.redhat.com/community/blogs/free-paas-email-server-with-roundcube).

## Setup

Create an OpenShift application with PHP and MySQL cartridges

```
rhc app create roundcube php-5
rhc cartridge add mysql -a roundcube
cd roundcube
```

Pull the source code from this Quickstart

```
git pull -s recursive -X theirs git://github.com/openshift-quickstart/roundcube-openshift-quickstart.git
```

Add PhPMyAdmin cartridge to manage MySQL server

```
rhc cartridge add phpmyadmin -a roundcube
```

and import the database from a file in repository

```
php/SQL/mysql.initial.sql
```

Push the code back to OpenShift to deploy

```
git push origin master
```

## Notes

This Quickstart is pre-configured to be used with the Mailgun service, however there are no blockers to use any other available service. To change this, edit the *php/config/main.inc.php* file accordingly.