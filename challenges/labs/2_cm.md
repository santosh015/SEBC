### List repositories
<pre><code>
[root@ip-172-31-9-250 ~]# ls /etc/yum.repos.d
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-Media.repo  CentOS-Vault.repo  cloudera-manager.repo  mysql-community.repo
[root@ip-172-31-9-250 ~]
</code></pre>

### Configure Cloudera Manager
# i used ansible to create the db,properties file from /usr/share/cmf/schema/scm_prepare_database.sh.The ouput db.properties in attached.
<pre><code>
- name: configure cloudera manager databases
#  command: "/usr/share/cmf/schema/scm_prepare_database.sh -h {{ scm_db_host }} -P {{ scm_db_port }} {{ scm_db_type }} {{ scm_db_name }} {{ scm_db_user }} {{ scm_db_user_password }} creates={{ scm_done_file }}"
  command: "/usr/share/cmf/schema/scm_prepare_database.sh -h {{ scm_db_host }} {{ scm_db_type }} {{ scm_db_name }} {{ scm_db_user }} {{ scm_db_user_password }} creates={{ scm_done_file }}"
</code></pre>
