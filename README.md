# OpenShift RoundCube Quickstart

Roundcube webmail...

```
...is a browser-based multilingual IMAP client with an application-like user interface. It provides full functionality you expect from an e-mail client, including MIME support, address book, folder manipulation, message searching and spell checking.
```

This Quickstart has an accompanying blog post [How To Setup Your Own Free Mail Server](https://www.openshift.com/blogs/free-paas-email-server-with-roundcube).

## Setup

Create an OpenShift application with PHP, MySQL, and PHPMyAdmin cartridges

```
rhc app create roundcube php-5.3 mysql-5.1 phpmyadmin
cd roundcube
```

Pull the source code from this Quickstart

```
git pull -s recursive -X theirs git://github.com/openshift-quickstart/roundcube-openshift-quickstart.git
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
