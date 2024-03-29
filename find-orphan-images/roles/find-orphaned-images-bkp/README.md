
# Project Title

A brief description of what this project does and who it's for

find-orphaned-images
=========

This role can be used to list and count of orphaned images from specfic cluster.

Role Variables
--------------

cluster_name: "{{ cluster }}" #openstack cluster in which play should run

dc: "{{ region }}" #dc in which play should run

git_secret_folder: 'common/git/RedHatTraining' #this is in vault where git pass key is stored.

vault_file: vault_config.yaml #config file for vault that will have creds to access vault.

repo_dir: '/tmp/ole-config-labenv' #temp folder in remote machine where repo will be cloned

git_heatdir: "{{ repo_dir }}/data/zdoc/osp_heat_template"  #folder in repo which will be checked for heat templates.

images_to_keep_regex: '^[Ee][Xx][0-9][0-9][0-9]|^[Pp][Ee][0-9][0-9][0-9]|^cert-|rhcos|mirror|OCP-client-install|ocp|^rhel-|^octavia-|^cirros-|^sidecar$|tsunami|^node2$|^dle-|^ole-'  ##images to exclude from checking

git_secret_file: '/tmp/git-secret' #file in which git pass will be stored temporarily.

cloud_image_list: '/tmp/cloud-image-list' #file in which openstack image list will be stored temporarily.

heat_template_image_list: '/tmp/heat-template-image-list'  #file in which heat-templates image list will be stored temporarily.

cloud_image_list_final: '/tmp/cloud-image-list-final'  #file in which final image list will be stored (after using images_to_keep_regex)

final_folder: '/tmp/orphan-images' #folder in which final list will be kept

final_list: "{{ final_folder}}/{{ cluster_name }}" #final list


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers 
      roles:
         - role: find-orphaned-images


How to run it in AAP
--------------------

After launching job in AAP select below:

      Inventory : Select as per requirement
      Credentials : Selected Category : OpenStack : Select as per cluster
      Survey : Select the cluster :  Select as per cluster : Select the region : Select as per DC

License
------------------
BSD-2-Clause
Copyright 2024 Red Hat, Inc.


Author Information
------------------
Ravikumar Karuppuchamy (rkaruppu@redhat.com)
Forrest Taylor (ftaylor@redhat.com)  
Manash Sharma (manash@redhat.com)
