Role Name
=========

This runs the Java keytool against keystores and creates fact files in the /etc/ansible/facts.d folder.

Installation
------------

A requirements.yml file might have this in it:

  - src: https://github.com/staylorx/ansible-role-keystore-facts
    version: master
    name: staylorx.keystore-facts

Alternatively clone the repo into your roles folder which has its own charm. 

Place a .gitmodules file in _your_ git repo with this,

  [submodule "roles/staylorx.keystore-facts"]
    path = roles/staylorx.keystore-facts
    url = git@github.com:staylorx/ansible-role-keystore-facts.git
    branch = master

Requirements
------------

The script assumes Java has been installed, specifically the keytool program.

Role Variables
--------------

A Java home with keytool in bin.
  java_home: /usr/java/latest.


A keystore list. The name is used in the fact file (viz., keystore-{{ item.name}}.fact).
  keystores:
    - name: DemoIdentity
      path: "/u01/app/oracle/middleware/wlserver_10.3/server/lib/DemoIdentity.jks"
      storepass: "DemoIdentityKeyStorePassPhrase"
    - name: DemoTrust
      path: "/u01/app/oracle/middleware/wlserver_10.3/server/lib/DemoTrust.jks"
      storepass: "DemoTrustKeyStorePassPhrase"
    - name: cacerts
      path: "/u01/jdk1.7.0_85/jre/lib/security/cacerts"
      storepass: "changeit"

Dependencies
------------

No Ansible-Galaxy dependencies. 

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: weblogic
      roles:
         - { role: staylorx.keystore-facts }

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
