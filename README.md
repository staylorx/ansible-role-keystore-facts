Role Name
=========

This runs the Java keytool against keystores and creates fact files in the /etc/ansible/facts.d folder.

Requirements
------------

The script assumes Java has been installed, specifically the keytool program.

Role Variables
--------------

java_home: defaults to /usr/java/latest.


keystores:
  - name: DemoIdentity
    path: "{{ middleware_home }}/wlserver_10.3/server/lib/DemoIdentity.jks"
    storepass: "DemoIdentityKeyStorePassPhrase"
  - name: DemoTrust
    path: "{{ middleware_home }}/wlserver_10.3/server/lib/DemoTrust.jks"
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
         - { role: staylorx.keystore_facts }

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
