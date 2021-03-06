OVERVIEW
========

``greatape`` is a minimalist client library for version 1.2 of the MailChimp
API.  It was very much inspired by Mike Verdone's `Twitter client library
<http://github.com/sixohsix/twitter>`_ in that it does a bit of mucky, dynamic
business with __getattr__ to avoid having to actually write code for all the
methods that the API provides.

``greatape`` is pretty darned easy to use.  Simple import the API object and 
instantiate it with your API key.

::

>>> from greatape import MailChimp
>>> mailchimp = MailChimp('<your api key>')

You can now access any of the methods in the API by calling them on your
``MailChimp`` instance with the required parameters as keyword arguments.
Results will be returned as Python lists or dictionaries.  (Note that you do
not need to provide your API key as a parameter other than to the constructor.)
Refer to the `MailChimp API documentation <http://www.mailchimp.com/api/1.2/>`_
for a complete list of available methods.

``greatape`` defaults to using SSL to access the MailChimp API.  If this isn't
what you want, pass ``ssl=False`` to the ``MailChimp`` constructor.

In case you desperately want to know exactly what resource you are hitting with
what data, pass the constructor ``debug=True`` and you will get a print out of
the URL and POST data just before the call is made.
