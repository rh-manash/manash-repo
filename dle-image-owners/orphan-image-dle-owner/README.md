dle-image-owners
=========

This role can be used to change project ownership of all images to DLE projects , except for the projects that starts with cert-* or pe[0-9]* or ex[0-9]*


Role Variables
--------------

cluster_name: dagobah  #cluster name

dc: dfw3   #dc name

cloud_name: "{{ cluster_name }}-{{ dc }}"

os_project: admin  #current project of Openstack

owner_project: DLE-Project1  #dle project that should be owner of images.


Example Playbook
----------------

    - name: Change image ownership to DLE-Project1
      hosts: localhost
      connection: local
      tasks:
       - name: call role
         include_role:
           name: orphan-image-dle-owner

License
-------

Copyright 2024 Red Hat, Inc.

Author Information
------------------
Manash Sharma(masharma@redhat.com)

