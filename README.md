obiba.obiba-ansible-deployment-aegir
=========
Ansible script to deploy Obiba Mica Drupal site using Aegir
It deploy Drupal site and perform some composer command to update some composer library dependencies

Role Variables
--------------
We need a
- vars/{{ destination}}-vars.yml to define these variables :

      branch: <Used obiba_mica branch version (exp : 7x21x)>
      ENV_DEV: <Is it an development/test environment (true/false)>
      mica_version: <The obiba_mica version tag to use (exp :7.x-21.1|master|7.x-20.x) >
      agate_version: <The obiba_agate version tag to use (exp :7.x-2.3|master|7.x-2.x) >
      theme_bootstrap_version: <The obiba_bootstrap version tag to use (exp :7.x-4.2|master|7.x-4.x) >
      js_lib_version: <The mica-drupal-js-libraries version tag to use (exp :2.1.4|master|branch-2.1.x) >
      alias_domain: <The domain name for deployed site>
      server_alias: <The serve alias defined in Aegir>
      web_server_alias: <The web serve alias defined in Aegir>
- vars/server_config.yml to define host name server behind proxy
      SERVER_deployement_staging: <Server staging host name>
      SERVER_deployement_production: l<Server live host name>

Example Playbook
----------------

    - hosts: "{{ destination }}"
      roles:
        - obiba.obiba-ansible-deployment-aegir
      vars_files:
        - vars/server_config.yml
        - "vars/{{ destination }}-vars.yml"

Command to deploy :

    ansible-playbook -i hosts -u aegir deploy.yml --flush-cache  -e "destination=staging"


License
-------

BSD

Obiba
------------------
OBiBa is an international project committed to build open source software for epidemiological studies. As part of the Maelstrom Research program, OBiBa software suite is developed in close partnership with large-scale studies and supports the entire data management lifecycle including data collection, integration, harmonization, sharing, and analysis.

[Read More](http://www.obiba.org/pages/about/)
