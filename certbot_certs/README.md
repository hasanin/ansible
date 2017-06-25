certbot_certs
=========

This role generates and apply let's encrypt ssl certificate to a domain.
It is not fully functional though, some improvements, and more webservers will be supported later.

Requirements
------------

EL7:
The epel repository is required for the certbot app installation.

Role Variables
--------------
website url: domain name defaults to {{ ansible_nodename }} which is usually the hostname
website user: the user owner of the website account defaults to root
website root dir: the root directory where the .well-known dir will be created defaults to /var/www/html
webserver: the webserver where the ssl certificate will be applied to, defaults to nginx - installed from source /usr/local/nginx - more webservers support may come later.

Dependencies
------------

Depends on the geerlingguy.certbot https://galaxy.ansible.com/geerlingguy/certbot/  for certbot installation 

Example Playbook
----------------
Here is an example of a cpanel server, note that the default webserver is nginx so for this to work, you need nginx configured as a reversec proxy.

    - hosts: servers
      roles:
         - { role: hasanin.certbot_certs, website_url: "domain.com", website_user: "domain", website_root: "/home/domain/public_html", }

License
-------

BSD

Author Information
------------------

later.
