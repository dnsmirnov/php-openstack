# php-openstack
PHP module, written in C for OpenStack API.

Development platform and components:
- Ubuntu 14.04.4 LTS
- php-7.0.7 source
- language: C with curl and json-c libs

Install notes:

1. Extract source code into php-7.0.7/ext/openstack directory
2. Run phpize in the module source directory
3. Run configure; make; make install; make test
4. Create configuration file /etc/php.d/30-openstack.ini with extension=openstack.so
5. Add into php.ini section [openstack] with 3 parameters:
    - openstack.keystone_host="127.0.0.1" # IP address keystone host
    - openstack.user_port=5000 # Request port
    - openstack.admin_port=35357
6. Restart php-fpm or apache2 service ( who are using )
7. Check phpinfo(); for openstack module is running

Module functionality:

- User authorization takes user token an create session
- Get user attributes: projects, VMs, images, disks, float IPs, networks, routers
- Get user statistics: cpu usage, disk usage, memory usage, network traffic
- Start/stop VMs, create and delete VMs, attach glance images, create cinder disks
- Attach and release floating IPs
