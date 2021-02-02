.. _goodies:


Goodies
==========

Gifts that makes Felix Felicis easy to use.


.. _preview-server:

Preview Server
---------------

Preview your blog with::

    $ liquidluck server
    $ liquidluck server -p 8888
    $ liquidluck server -p 8888 -s settings.py

Preview server now support livereload, when you are editing a post, it will
auto compile and auto refresh the browser for you. **Added in version 1.12**

To enable livereload, your should install tornado::

    $ pip install tornado


Webhook
----------

Felix Felicis supports webhook since v1.6. When you push to GitHub or BitBucket,
your blog can generate itself.

First, you need to install Felix Felicis on your server::

    $ pip install liquidluck

Second, your blog repo on your server::

    $ git clone git://path/to/your/repo blog

Then, start webhook daemon in your blog::

    $ cd blog
    $ liquidluck webhook start -p 9876


Configure webhook on GitHub or BitBucket. We take GitHub as an example.

Head over to your blog source repo admin, select **Service Hooks**

.. image:: media/github.jpg
    :alt: github service hook

If you prefer BitBucket, you should select the POST service:

.. image:: media/bitbucket.jpg
    :alt: bitbucket service hook

If your server ip is 88.88.88.88, you can add a URL::

    http://88.88.88.88:9876/webhook

And when you push to GitHub, your server will update the repo and generate the whole site.
