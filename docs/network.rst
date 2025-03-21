.. _service-sonarr-network:

Network
#######
Sonarr should be run via a Reverse Proxy, allowing you to isolate and wrap
connections in SSL. See :ref:`service-nginx` for more details. See
:ref:`service-nginx-base-proxy-control` for basic proxy configuration.

See `Sonarr V4 reverse proxy reference <https://wiki.servarr.com/sonarr/faq-v4#my-reverse-proxy-doesnt-work-anymore>`__.
See `Sonarr reverse proxy reference <https://gist.github.com/IronicBadger/362c408d1f2c27a0503cb9252b508140#file-bash_aliases>`__.

Ports
*****
.. literalinclude:: ../defaults/main/ports.yml

Using Subdomains
================
.. literalinclude:: source/subdomain.conf
  :caption: **0644 root root** ``nginx/conf.d/reverse-proxy.conf``

Using Subpaths
==============
.. literalinclude:: source/subpath.conf
  :caption: **0644 root root** ``nginx/conf.d/reverse-proxy.conf``

.. note::
  Set ``sonarr_url_base`` to **/sonarr** before enabling the reverse-proxy.

  .. code-block:: yaml
    :caption: ``ansible_sonarr_vars.yaml``

    sonarr_url_base: '/sonarr'
