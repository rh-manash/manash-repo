dle-ownership-images
=========

This role can be used to change project ownership of all images to DLE projects , except for the projects that starts with cert-* or pe[0-9]* or ex[0-9]* and ends with *-rhcos.


Role Variables
--------------

cluster_name: dagobah  #cluster name

dc: dfw3   #dc name

os_project: admin  #current project of Openstack

owner_project: DLE-Project1  #dle project that should be owner of images.

dump_file_folder: '/var/content/orphan' #folder in which image list will be stored.

dump_file: "{{ dump_file_folder }}/{{ cluster_name }}"  #file in which image list will be stored.

dump_host: 'automation-controller-geonosis-dfw3.ole.redhat.com' #server in which file will be stored.



Example Playbook
----------------

    - name: Change image project ownership
      hosts: localhost
      collections:
         - openstack.cloud
      tasks:
         - name: Calling the role to check and change ownership
           include_role:
               name: dle-ownership-images


License
-------

Copyright 2024 Red Hat, Inc.

Author Information
------------------
Manash Sharma(masharma@redhat.com)

