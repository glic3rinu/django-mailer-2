===============
django-mailer-2
===============

Django mailer is used to queue e-mails. This allows the emails to be sent
asynchronously (by the use of a command extension) rather than blocking the
response.

Contents:

.. toctree::

    install
    usage
    settings

Django Mailer fork
==================

django-mailer-2 is a fork form Chris Beaven fort to of James Tauber's 
`django-mailer`.__

This document is readthedocs version of the fork that Chris and James made 
the original document with some additional information.

comments.

.. __: http://github.com/jtauber/django-mailer

History
-------

Chris Beaven started a fork of django-mailer and it got to the point when it
would be rather difficult to merge back. The fork was then renamed to the 
completely unimaginative "django mailer 2".

In hindsight, this was a bad naming choice as it wasn't supposed to reflect
that this is a "2.0" version or the like, simply an alternative.

The application namespace was changed (django-mailer-2 uses ``django_mailer``
whereas django-mailer uses ``mailer``), allowing the two products to
technically live side by side in harmony. One of the motivations in doing this
was to make the transition simpler for projects which are using django-mailer
(or to transition back, if someone doesn't like this one).

I made an additional fork as I need to correct some bugs related to unicode
mail and add some interesting patches as the one which allows you to remove
mails.


Differences
-----------

Some of the larger differences in django-mailer-2:

* It saves a rendered version of the email instead - so HTML and other
  attachments are handled fine
  
* The models were completely refactored for a better logical separation of
  data.

* It provides a hook to override (aka "monkey patch") the Django ``send_mail``,
  ``mail_admins`` and ``mail_manager`` functions.

* Added a management command to remove old e-mails, so the database does not
  increase so much.

* Added a new testing procedure, so you can run the tests without having to
  install and configure a Django application.

* Added some cron templates ein `bin` folder to help you to configure the
  cron.

* Improved admin configuration.

* Added a demo project, which shows how we can retrieve an email stored in
  the database and shows django-mailer in the admin.

Credit
------

At the time of the fork, the primary authors of django-mailer were James Tauber
and Brian Rosner. The additional contributors included Michael Trier, Doug
Napoleone and Jannis Leidel.

Original branch and the django-mailer-2 hard work comes from Chris Beaven.


