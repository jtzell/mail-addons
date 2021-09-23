.. image:: https://itpp.dev/images/infinity-readme.png
   :alt: Tested and maintained by IT Projects Labs
   :target: https://itpp.dev

Fix mail error 553
==================

Module updates 'FROM' field to portal@MYDOMAIN.COM  value in order to fix 553 error on a mail service that checks FROM field.

E.g:

* Customer send email from USER@CUSTOMER.com to info@MYDOMAIN.COM
* flectra accept email and try to send notifcation to related flectra users. E.g to admin@gmail.com.
* By default flectra prepare notification email with parameters as follows:

  * FROM: user@CUSTOMER.com
  * TO: admin@gmail.com

if you mail service provider, e.g. pdd.yandex.ru, doesn't allow emails with a FROM value differ from ...@MYDOMAIN.COM, then you get 553. This is why you need to update FROM value to portal@MYDOMAIN.COM

Configuration
=============

You can configure default alias at Settings -> System Parameters -> mail.catchall.alias_from
You can configure name for default alias at Settings -> System Parameters -> mail.catchall.name_alias_from

You can configure name for default alias at Settings -> System Parameters -> mail.catchall.name_alias_from

Known issues / Roadmap
======================

The module is consist of redefined send function from mail.mail
model. So it is just copy pasted source code with some
modification. This function is changed very rarely, but sometime it
can happens and the module should be updated. You can check commits
for mail_mail.py here:
https://github.com/flectra/flectra/commits/8.0/addons/mail/mail_mail.py

Tested on `Flectra 8.0 <https://github.com/flectra/flectra/commit/d023c079ed86468436f25da613bf486a4a17d625>`_

Status
======

Related issues at flectra's tracker: 
* https://github.com/flectra/flectra/issues/5864
* https://github.com/flectra/flectra/issues/3347

Fix: https://github.com/flectra-dev/flectra/commit/a4597fe34fcfa8dae28b156410080346bb33af33
