What is lxml?
=============

lxml is the most feature-rich and easy-to-use library for processing XML and HTML in the Python language.
It's also very fast and memory friendly, just so you know.

For an introduction and further documentation, see `doc/main.txt`_.

For installation information, see `INSTALL.txt`_.

Why is there a cffi branch?
---------------------------

This is an experimental branch of lxml that uses ``cffi`` instead of
C-extensions to compile lxml. This means it is compatible with, among others,
the Pypy project.

Is this ready for production?
-----------------------------

The lxml-cffi branch has passed tests X, Y, and Z and companies A, B, and C are
using it in production. However it is still very much new software and your
mileage may vary.

Installation
------------

If you are installing with CPython, you can use ``pip`` to install lxml.

    .. code-block:: bash

    pip install lxml

This will download the lxml source code onto your machine and compile the lxml
c-code for your machine. 

If you are installing with Pypy, no compile step is necessary. Just copy the
lxml source directory to any place that is checked by Python when it begins
running. Here is one example usage, that will copy lxml-cffi into a virtualenv:

.. code-block:: bash

    virtualenv venv
    source venv/bin/activate

    mkdir -p tmp
    pushd tmp
        if [ ! -d lxml ]; then 
            # Download the lxml code
            git clone https://github.com/amauryfa/lxml.git
        fi
        pushd lxml
            # Checkout the correct branch
            git checkout cffi
        popd
    popd

    # copy lxml into place, no compiling.
    if [ -d venv/site-packages ]; then
        cp -rf tmp/lxml/src/lxml venv/site-packages
    else
        cp -rf tmp/lxml/src/lxml venv/lib/pythonX.Y/site-packages
    fi



Support the project
-------------------

lxml has been downloaded from the `Python Package Index`_ more than
two million times and is also available directly in many package
distributions, e.g. for Linux or MacOS-X.

.. _`Python Package Index`: https://pypi.python.org/pypi/lxml

Most people who use lxml do so because they like using it.
You can show us that you like it by blogging about your experience
with it and linking to the project website.

If you are using lxml for your work and feel like giving a bit of
your own benefit back to support the project, consider sending us
money through PayPal that we can use for fixing bugs in the software
and improving its features and documentation.  Please read the Legal
Notice below, at the bottom of this page.  Thank you for your support.

.. class:: center

  |Donate|_

.. _Donate: https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=R56JE3VCPDA9N

Alternatively, if you prefer expressing your appreciation in a monthy
dose of pennies rather than a dedicated donation, you can also use
Flattr to do so.

.. class:: center

  |FlattrLink|_

.. _FlattrLink: https://flattr.com/thing/268156/lxml-The-Python-XML-Toolkit

Note that Flattr keeps 10% of the transactions for itself, which is money
you pay that will not reach us.  Do not send any larger amounts through
Flattr.  Use PayPal for donations instead, or `contact Stefan Behnel`_ for
other ways to support the lxml project, as well as commercial consulting,
customisations and trainings on lxml and fast Python XML processing.

.. |Donate| image:: https://github.com/lxml/lxml/raw/master/doc/html/paypal_btn_donateCC_LG.gif
            :width: 160
            :height: 47
            :alt: Donate to the lxml project

.. |FlattrLink| image:: https://github.com/lxml/lxml/raw/master/doc/html/flattr-badge-large.png
                :width: 93
                :height: 20
                :alt: Flattr the lxml project

.. _`contact Stefan Behnel`: http://consulting.behnel.de/
.. _`doc/main.txt`: http://lxml.de/
.. _`INSTALL.txt`: http://lxml.de/installation.html


Legal Notice for Donations
--------------------------

Any donation that you make to the lxml project is voluntary and
is not a fee for any services, goods, or advantages.  By making
a donation to the lxml project, you acknowledge that we have the
right to use the money you donate in any lawful way and for any
lawful purpose we see fit and we are not obligated to disclose
the way and purpose to any party unless required by applicable
law.  Although lxml is free software, to the best of our knowledge
the lxml project does not have any tax exempt status.  The lxml
project is neither a registered non-profit corporation nor a
registered charity in any country.  Your donation may or may not
be tax-deductible; please consult your tax advisor in this matter.
We will not publish or disclose your name and/or e-mail address
without your consent, unless required by applicable law.  Your
donation is non-refundable.
