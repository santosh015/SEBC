## commands run

<pre><code>
curl -c cmapi-cookies.txt -X GET -u "santosh015:cloudera" -i \
 http://54.254.163.203:7180/api/v11/tools/echo?message=hello

curl \
 -b cmapi-cookies.txt \
 -X GET \
 -i http://54.254.163.203:7180/api/v11/cm/deployment/
</code></pre>
## output
<pre><code>
HTTP/1.1 200 OK
Content-Type: application/json
Date: Wed, 07 Dec 2016 02:52:06 GMT
Transfer-Encoding: chunked
Server: Jetty(6.1.26.cloudera.4)

{
  "timestamp" : "2016-12-07T02:52:06.869Z",
  "clusters" : [ {
    "name" : "cluster",
    "displayName" : "santosh015",
    "version" : "CDH5",
    "fullVersion" : "5.8.3",
    "services" : [ {
      "name" : "zookeeper",
      "type" : "ZOOKEEPER",
      "config" : {
        "items" : [ ]
      },
      "roles" : [ {
        "name" : "zookeeper-SERVER-9f617b0936bb691e99c97e565f76afde",
        "type" : "SERVER",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "37opwjpcvpufh63nncoqt9unp"
          }, {
            "name" : "serverId",
            "value" : "1"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "zookeeper-SERVER-BASE"
        }
      } ],
      "displayName" : "ZooKeeper",
      "roleConfigGroups" : [ {
        "name" : "zookeeper-SERVER-BASE",
        "displayName" : "Server Default Group",
        "roleType" : "SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "zookeeper"
        },
        "config" : {
          "items" : [ {
            "name" : "zookeeper_server_java_heapsize",
            "value" : "612368384"
          } ]
        }
      } ]
    }, {
      "name" : "oozie",
      "type" : "OOZIE",
      "config" : {
        "items" : [ {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "oozie-OOZIE_SERVER-9f617b0936bb691e99c97e565f76afde",
        "type" : "OOZIE_SERVER",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5mjyhdmn5k3mk3lnotprs1r0p"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "oozie-OOZIE_SERVER-BASE"
        }
      } ],
      "displayName" : "Oozie",
      "roleConfigGroups" : [ {
        "name" : "oozie-OOZIE_SERVER-BASE",
        "displayName" : "Oozie Server Default Group",
        "roleType" : "OOZIE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "oozie"
        },
        "config" : {
          "items" : [ {
            "name" : "oozie_database_host",
            "value" : "ip-172-31-10-136.ap-southeast-1.compute.internal"
          }, {
            "name" : "oozie_database_password",
            "value" : "oozie_password"
          }, {
            "name" : "oozie_database_type",
            "value" : "mysql"
          }, {
            "name" : "oozie_database_user",
            "value" : "oozie"
          }, {
            "name" : "oozie_java_heapsize",
            "value" : "612368384"
          } ]
        }
      } ]
    }, {
      "name" : "hue",
      "type" : "HUE",
      "config" : {
        "items" : [ {
          "name" : "database_host",
          "value" : "ip-172-31-10-136.ap-southeast-1.compute.internal"
        }, {
          "name" : "database_password",
          "value" : "hue_password"
        }, {
          "name" : "database_type",
          "value" : "mysql"
        }, {
          "name" : "hive_service",
          "value" : "hive"
        }, {
          "name" : "hue_webhdfs",
          "value" : "hdfs-NAMENODE-9f617b0936bb691e99c97e565f76afde"
        }, {
          "name" : "oozie_service",
          "value" : "oozie"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hue-HUE_SERVER-9f617b0936bb691e99c97e565f76afde",
        "type" : "HUE_SERVER",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "d0lk7cpgpfm8gijphsd1atd9z"
          }, {
            "name" : "secret_key",
            "value" : "XCen3V7PLxxIGRYThLC94BZVbNKa79"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hue-HUE_SERVER-BASE"
        }
      } ],
      "displayName" : "Hue",
      "roleConfigGroups" : [ {
        "name" : "hue-HUE_LOAD_BALANCER-BASE",
        "displayName" : "Load Balancer Default Group",
        "roleType" : "HUE_LOAD_BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-HUE_SERVER-BASE",
        "displayName" : "Hue Server Default Group",
        "roleType" : "HUE_SERVER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hue-KT_RENEWER-BASE",
        "displayName" : "Kerberos Ticket Renewer Default Group",
        "roleType" : "KT_RENEWER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hue"
        },
        "config" : {
          "items" : [ ]
        }
      } ]
    }, {
      "name" : "hdfs",
      "type" : "HDFS",
      "config" : {
        "items" : [ {
          "name" : "dfs_ha_fencing_cloudera_manager_secret_key",
          "value" : "HSQjtiC8CV3NfqXvMIGlaYDxNdAXjy"
        }, {
          "name" : "dfs_ha_fencing_methods",
          "value" : "shell(true)"
        }, {
          "name" : "fc_authorization_secret_key",
          "value" : "TqTVUGY62EmapBKONbU5obULuR8PGe"
        }, {
          "name" : "http_auth_signature_secret",
          "value" : "Zi0zQA9n8HHe4BXXPpLf8bBcnWHl32"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "10"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hdfs-BALANCER-9f617b0936bb691e99c97e565f76afde",
        "type" : "BALANCER",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-BALANCER-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-a3e5beb26302b9c1688c7be7091b0ec9",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "8f06df91-23ac-4fe3-99c4-e3568789de00"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "17p894ffl7h56erwgfevlmd8d"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-b2f76857524262eea52049f785b6ba79",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "cf9264da-994d-4822-bf8f-58efbdffd9b1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "94kysg3ltrz6ifaizmdh6btsc"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-bfbb9dddde421eea0fce8d1618a5eee4",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "c6ab705c-d589-4f9c-9266-41af328947ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "b572wgu1onnfkr6y6qpdffeib"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-DATANODE-c8c9418c8de7be8b11a21ad9687a16a2",
        "type" : "DATANODE",
        "hostRef" : {
          "hostId" : "bd75d097-879b-48ba-88f0-1c56707f85b1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "59z01rbxkl6mihan86mkbdvj1"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-DATANODE-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-9f617b0936bb691e99c97e565f76afde",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "4dw5nax58dizbiycfqrpj8hw4"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-a3e5beb26302b9c1688c7be7091b0ec9",
        "type" : "FAILOVERCONTROLLER",
        "hostRef" : {
          "hostId" : "8f06df91-23ac-4fe3-99c4-e3568789de00"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "10t7lkgwp40nr7h1hpcybzvsz"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-FAILOVERCONTROLLER-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-a3e5beb26302b9c1688c7be7091b0ec9",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "8f06df91-23ac-4fe3-99c4-e3568789de00"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "9qr8wz418sfqckx3c6atyf1jz"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-b2f76857524262eea52049f785b6ba79",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "cf9264da-994d-4822-bf8f-58efbdffd9b1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "93xvg53oi4ppfwoqzv0z2mscr"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-JOURNALNODE-c8c9418c8de7be8b11a21ad9687a16a2",
        "type" : "JOURNALNODE",
        "hostRef" : {
          "hostId" : "bd75d097-879b-48ba-88f0-1c56707f85b1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "1ieztlx7sardx1ll7xfrg1b6k"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-JOURNALNODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-9f617b0936bb691e99c97e565f76afde",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "38"
          }, {
            "name" : "role_jceks_password",
            "value" : "96bd5ndvewn5mrbzadyym74up"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      }, {
        "name" : "hdfs-NAMENODE-a3e5beb26302b9c1688c7be7091b0ec9",
        "type" : "NAMENODE",
        "hostRef" : {
          "hostId" : "8f06df91-23ac-4fe3-99c4-e3568789de00"
        },
        "config" : {
          "items" : [ {
            "name" : "autofailover_enabled",
            "value" : "true"
          }, {
            "name" : "dfs_federation_namenode_nameservice",
            "value" : "nameservice1"
          }, {
            "name" : "dfs_namenode_quorum_journal_name",
            "value" : "nameservice1"
          }, {
            "name" : "namenode_id",
            "value" : "49"
          }, {
            "name" : "role_jceks_password",
            "value" : "73gljbod2zml75rri5bmmxv9p"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hdfs-NAMENODE-BASE"
        }
      } ],
      "displayName" : "HDFS",
      "roleConfigGroups" : [ {
        "name" : "hdfs-BALANCER-BASE",
        "displayName" : "Balancer Default Group",
        "roleType" : "BALANCER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "balancer_java_heapsize",
            "value" : "612368384"
          } ]
        }
      }, {
        "name" : "hdfs-DATANODE-BASE",
        "displayName" : "DataNode Default Group",
        "roleType" : "DATANODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "datanode_java_heapsize",
            "value" : "1073741824"
          }, {
            "name" : "dfs_data_dir_list",
            "value" : "/dfs/dn"
          }, {
            "name" : "dfs_datanode_du_reserved",
            "value" : "4227576627"
          }, {
            "name" : "dfs_datanode_max_locked_memory",
            "value" : "4294967296"
          }, {
            "name" : "rm_cpu_shares",
            "value" : "200"
          }, {
            "name" : "rm_io_weight",
            "value" : "100"
          } ]
        }
      }, {
        "name" : "hdfs-FAILOVERCONTROLLER-BASE",
        "displayName" : "Failover Controller Default Group",
        "roleType" : "FAILOVERCONTROLLER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_client_use_trash",
            "value" : "true"
          } ]
        }
      }, {
        "name" : "hdfs-HTTPFS-BASE",
        "displayName" : "HttpFS Default Group",
        "roleType" : "HTTPFS",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-JOURNALNODE-BASE",
        "displayName" : "JournalNode Default Group",
        "roleType" : "JOURNALNODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_journalnode_edits_dir",
            "value" : "/tmp/edits"
          } ]
        }
      }, {
        "name" : "hdfs-NAMENODE-BASE",
        "displayName" : "NameNode Default Group",
        "roleType" : "NAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "dfs_name_dir_list",
            "value" : "/dfs/nn"
          }, {
            "name" : "dfs_namenode_servicerpc_address",
            "value" : "8022"
          }, {
            "name" : "namenode_java_heapsize",
            "value" : "612368384"
          } ]
        }
      }, {
        "name" : "hdfs-NFSGATEWAY-BASE",
        "displayName" : "NFS Gateway Default Group",
        "roleType" : "NFSGATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hdfs-SECONDARYNAMENODE-BASE",
        "displayName" : "SecondaryNameNode Default Group",
        "roleType" : "SECONDARYNAMENODE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hdfs"
        },
        "config" : {
          "items" : [ {
            "name" : "fs_checkpoint_dir_list",
            "value" : "/dfs/snn"
          }, {
            "name" : "secondary_namenode_java_heapsize",
            "value" : "612368384"
          } ]
        }
      } ],
      "replicationSchedules" : [ ],
      "snapshotPolicies" : [ ]
    }, {
      "name" : "yarn",
      "type" : "YARN",
      "config" : {
        "items" : [ {
          "name" : "hdfs_service",
          "value" : "hdfs"
        }, {
          "name" : "rm_dirty",
          "value" : "false"
        }, {
          "name" : "rm_last_allocation_percentage",
          "value" : "90"
        }, {
          "name" : "yarn_service_cgroups",
          "value" : "false"
        }, {
          "name" : "yarn_service_lce_always",
          "value" : "false"
        }, {
          "name" : "zk_authorization_secret_key",
          "value" : "4u1J6ynnmkl1HTtxSzboFsZXRniHeh"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "yarn-JOBHISTORY-9f617b0936bb691e99c97e565f76afde",
        "type" : "JOBHISTORY",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "3q9wxjd1puw154ghw9wsblgq0"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-JOBHISTORY-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-a3e5beb26302b9c1688c7be7091b0ec9",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "8f06df91-23ac-4fe3-99c4-e3568789de00"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6xbib8hurdpv7o9yghi6lgb3x"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-b2f76857524262eea52049f785b6ba79",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "cf9264da-994d-4822-bf8f-58efbdffd9b1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "2zjy4dxbteubmmhye973ro3od"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-bfbb9dddde421eea0fce8d1618a5eee4",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "c6ab705c-d589-4f9c-9266-41af328947ce"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "6gi4ohlhug1tba9qs7y7grj9c"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-NODEMANAGER-c8c9418c8de7be8b11a21ad9687a16a2",
        "type" : "NODEMANAGER",
        "hostRef" : {
          "hostId" : "bd75d097-879b-48ba-88f0-1c56707f85b1"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "t0c29z5nuorjj5nvl7q17s1b"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-NODEMANAGER-BASE"
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-9f617b0936bb691e99c97e565f76afde",
        "type" : "RESOURCEMANAGER",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_id",
            "value" : "45"
          }, {
            "name" : "role_jceks_password",
            "value" : "6tlahu5dsio0h0gw4h4x9uymx"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "yarn-RESOURCEMANAGER-BASE"
        }
      } ],
      "displayName" : "YARN (MR2 Included)",
      "roleConfigGroups" : [ {
        "name" : "yarn-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mapred_reduce_tasks",
            "value" : "8"
          }, {
            "name" : "mapred_submit_replication",
            "value" : "2"
          } ]
        }
      }, {
        "name" : "yarn-JOBHISTORY-BASE",
        "displayName" : "JobHistory Server Default Group",
        "roleType" : "JOBHISTORY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "mr2_jobhistory_java_heapsize",
            "value" : "612368384"
          } ]
        }
      }, {
        "name" : "yarn-NODEMANAGER-BASE",
        "displayName" : "NodeManager Default Group",
        "roleType" : "NODEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "rm_cpu_shares",
            "value" : "1800"
          }, {
            "name" : "rm_io_weight",
            "value" : "900"
          }, {
            "name" : "yarn_nodemanager_heartbeat_interval_ms",
            "value" : "100"
          }, {
            "name" : "yarn_nodemanager_local_dirs",
            "value" : "/yarn/nm"
          }, {
            "name" : "yarn_nodemanager_log_dirs",
            "value" : "/yarn/container-logs"
          }, {
            "name" : "yarn_nodemanager_resource_cpu_vcores",
            "value" : "3"
          }, {
            "name" : "yarn_nodemanager_resource_memory_mb",
            "value" : "3492"
          } ]
        }
      }, {
        "name" : "yarn-RESOURCEMANAGER-BASE",
        "displayName" : "ResourceManager Default Group",
        "roleType" : "RESOURCEMANAGER",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "yarn"
        },
        "config" : {
          "items" : [ {
            "name" : "resource_manager_java_heapsize",
            "value" : "612368384"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_mb",
            "value" : "5250"
          }, {
            "name" : "yarn_scheduler_maximum_allocation_vcores",
            "value" : "3"
          } ]
        }
      } ]
    }, {
      "name" : "hive",
      "type" : "HIVE",
      "config" : {
        "items" : [ {
          "name" : "hive_metastore_database_host",
          "value" : "ip-172-31-10-136.ap-southeast-1.compute.internal"
        }, {
          "name" : "hive_metastore_database_password",
          "value" : "hive_password"
        }, {
          "name" : "mapreduce_yarn_service",
          "value" : "yarn"
        }, {
          "name" : "zookeeper_service",
          "value" : "zookeeper"
        } ]
      },
      "roles" : [ {
        "name" : "hive-GATEWAY-bfbb9dddde421eea0fce8d1618a5eee4",
        "type" : "GATEWAY",
        "hostRef" : {
          "hostId" : "c6ab705c-d589-4f9c-9266-41af328947ce"
        },
        "config" : {
          "items" : [ ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-GATEWAY-BASE"
        }
      }, {
        "name" : "hive-HIVEMETASTORE-9f617b0936bb691e99c97e565f76afde",
        "type" : "HIVEMETASTORE",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "a72od3zxkau1w9c4rjolg3vzr"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVEMETASTORE-BASE"
        }
      }, {
        "name" : "hive-HIVESERVER2-9f617b0936bb691e99c97e565f76afde",
        "type" : "HIVESERVER2",
        "hostRef" : {
          "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
        },
        "config" : {
          "items" : [ {
            "name" : "role_jceks_password",
            "value" : "5kceperuag5wsymylntpqabe8"
          } ]
        },
        "roleConfigGroupRef" : {
          "roleConfigGroupName" : "hive-HIVESERVER2-BASE"
        }
      } ],
      "displayName" : "Hive",
      "roleConfigGroups" : [ {
        "name" : "hive-GATEWAY-BASE",
        "displayName" : "Gateway Default Group",
        "roleType" : "GATEWAY",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      }, {
        "name" : "hive-HIVEMETASTORE-BASE",
        "displayName" : "Hive Metastore Server Default Group",
        "roleType" : "HIVEMETASTORE",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hive_metastore_java_heapsize",
            "value" : "612368384"
          } ]
        }
      }, {
        "name" : "hive-HIVESERVER2-BASE",
        "displayName" : "HiveServer2 Default Group",
        "roleType" : "HIVESERVER2",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ {
            "name" : "hiveserver2_java_heapsize",
            "value" : "612368384"
          }, {
            "name" : "hiveserver2_spark_driver_memory",
            "value" : "966367641"
          }, {
            "name" : "hiveserver2_spark_executor_cores",
            "value" : "4"
          }, {
            "name" : "hiveserver2_spark_executor_memory",
            "value" : "4679270400"
          }, {
            "name" : "hiveserver2_spark_yarn_driver_memory_overhead",
            "value" : "102"
          }, {
            "name" : "hiveserver2_spark_yarn_executor_memory_overhead",
            "value" : "787"
          } ]
        }
      }, {
        "name" : "hive-WEBHCAT-BASE",
        "displayName" : "WebHCat Server Default Group",
        "roleType" : "WEBHCAT",
        "base" : true,
        "serviceRef" : {
          "clusterName" : "cluster",
          "serviceName" : "hive"
        },
        "config" : {
          "items" : [ ]
        }
      } ],
      "replicationSchedules" : [ ]
    } ],
    "parcels" : [ {
      "product" : "CDH",
      "version" : "5.8.3-1.cdh5.8.3.p0.2",
      "stage" : "DISTRIBUTED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    }, {
      "product" : "CDH",
      "version" : "5.8.3-1.cdh5.8.3.p0.2",
      "stage" : "ACTIVATED",
      "clusterRef" : {
        "clusterName" : "cluster"
      }
    } ]
  } ],
  "hosts" : [ {
    "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5",
    "ipAddress" : "172.31.10.136",
    "hostname" : "ip-172-31-10-136.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "8f06df91-23ac-4fe3-99c4-e3568789de00",
    "ipAddress" : "172.31.10.137",
    "hostname" : "ip-172-31-10-137.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "c6ab705c-d589-4f9c-9266-41af328947ce",
    "ipAddress" : "172.31.10.138",
    "hostname" : "ip-172-31-10-138.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "cf9264da-994d-4822-bf8f-58efbdffd9b1",
    "ipAddress" : "172.31.10.139",
    "hostname" : "ip-172-31-10-139.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  }, {
    "hostId" : "bd75d097-879b-48ba-88f0-1c56707f85b1",
    "ipAddress" : "172.31.10.140",
    "hostname" : "ip-172-31-10-140.ap-southeast-1.compute.internal",
    "rackId" : "/default",
    "config" : {
      "items" : [ ]
    }
  } ],
  "users" : [ {
    "name" : "__cloudera_internal_user__mgmt-EVENTSERVER-9f617b0936bb691e99c97e565f76afde",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "0a92ea93ebe1b9595154685b209cc0b263818706f797f138c3147c1bbe00425f",
    "pwSalt" : -7200539220982229494,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-HOSTMONITOR-9f617b0936bb691e99c97e565f76afde",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "3a38735dbb1cbaff6c2fa065a2d8f3ff709749637a4071d5603cdc319ad37c72",
    "pwSalt" : -6748409778976604600,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-REPORTSMANAGER-9f617b0936bb691e99c97e565f76afde",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "1eca7917d659bdd70ad9eeae07d34ebf9d0828f4b894465ab284e5fb88b9c6b2",
    "pwSalt" : -1673591343359196589,
    "pwLogin" : true
  }, {
    "name" : "__cloudera_internal_user__mgmt-SERVICEMONITOR-9f617b0936bb691e99c97e565f76afde",
    "roles" : [ "ROLE_USER" ],
    "pwHash" : "16b9a642d71c11a4e26080a3c612a3a742693f2f1dd893cd8860df2140c7e235",
    "pwSalt" : -1203288451249802416,
    "pwLogin" : true
  }, {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ],
    "pwHash" : "784bb76df7d5b166e8ff48482405326a61c0fd1e793406f2c3521293b5d6dfc1",
    "pwSalt" : 700959106732134500,
    "pwLogin" : true
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ],
    "pwHash" : "e1bad4830bd372ffd6dd75a6e35b23c7d6904c8728f10bb519013917946ecfc1",
    "pwSalt" : 2703161935237716689,
    "pwLogin" : true
  }, {
    "name" : "santosh015",
    "roles" : [ "ROLE_ADMIN" ],
    "pwHash" : "93e1d99f3c5b9a60009322ced66e0d359aae6489fe28c7668f7fa238c3c6f21c",
    "pwSalt" : 1539656432697700192,
    "pwLogin" : true
  } ],
  "versionInfo" : {
    "version" : "5.8.2",
    "buildUser" : "jenkins",
    "buildTimestamp" : "20160916-1426",
    "gitHash" : "d23c620f3a3bbd85d8511d6ebba49beaaab14b75",
    "snapshot" : false
  },
  "managementService" : {
    "name" : "mgmt",
    "type" : "MGMT",
    "config" : {
      "items" : [ ]
    },
    "roles" : [ {
      "name" : "mgmt-ALERTPUBLISHER-9f617b0936bb691e99c97e565f76afde",
      "type" : "ALERTPUBLISHER",
      "hostRef" : {
        "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "eywgw1f34xz6cgncmd9buo114"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-ALERTPUBLISHER-BASE"
      }
    }, {
      "name" : "mgmt-EVENTSERVER-9f617b0936bb691e99c97e565f76afde",
      "type" : "EVENTSERVER",
      "hostRef" : {
        "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "bx1og1e5mhsyo00cpytkju3me"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-EVENTSERVER-BASE"
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-9f617b0936bb691e99c97e565f76afde",
      "type" : "HOSTMONITOR",
      "hostRef" : {
        "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "629p8pkdn8xo74spqns1ety2o"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-HOSTMONITOR-BASE"
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-9f617b0936bb691e99c97e565f76afde",
      "type" : "REPORTSMANAGER",
      "hostRef" : {
        "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "b8kvczeb58ws89m8x8r55rifq"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-REPORTSMANAGER-BASE"
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-9f617b0936bb691e99c97e565f76afde",
      "type" : "SERVICEMONITOR",
      "hostRef" : {
        "hostId" : "b051dbc1-1779-41da-8049-d50ff5cd00a5"
      },
      "config" : {
        "items" : [ {
          "name" : "role_jceks_password",
          "value" : "6l4i38k3gjdbpa0rykfozovt2"
        } ]
      },
      "roleConfigGroupRef" : {
        "roleConfigGroupName" : "mgmt-SERVICEMONITOR-BASE"
      }
    } ],
    "displayName" : "Cloudera Management Service",
    "roleConfigGroups" : [ {
      "name" : "mgmt-ACTIVITYMONITOR-BASE",
      "displayName" : "Activity Monitor Default Group",
      "roleType" : "ACTIVITYMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-ALERTPUBLISHER-BASE",
      "displayName" : "Alert Publisher Default Group",
      "roleType" : "ALERTPUBLISHER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-EVENTSERVER-BASE",
      "displayName" : "Event Server Default Group",
      "roleType" : "EVENTSERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "event_server_heapsize",
          "value" : "612368384"
        } ]
      }
    }, {
      "name" : "mgmt-HOSTMONITOR-BASE",
      "displayName" : "Host Monitor Default Group",
      "roleType" : "HOSTMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "612368384"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }
    }, {
      "name" : "mgmt-NAVIGATOR-BASE",
      "displayName" : "Navigator Audit Server Default Group",
      "roleType" : "NAVIGATOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-NAVIGATORMETASERVER-BASE",
      "displayName" : "Navigator Metadata Server Default Group",
      "roleType" : "NAVIGATORMETASERVER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ ]
      }
    }, {
      "name" : "mgmt-REPORTSMANAGER-BASE",
      "displayName" : "Reports Manager Default Group",
      "roleType" : "REPORTSMANAGER",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "headlamp_database_host",
          "value" : "ip-172-31-10-136.ap-southeast-1.compute.internal"
        }, {
          "name" : "headlamp_database_name",
          "value" : "rman"
        }, {
          "name" : "headlamp_database_password",
          "value" : "rman_password"
        }, {
          "name" : "headlamp_database_user",
          "value" : "rman"
        }, {
          "name" : "headlamp_heapsize",
          "value" : "612368384"
        } ]
      }
    }, {
      "name" : "mgmt-SERVICEMONITOR-BASE",
      "displayName" : "Service Monitor Default Group",
      "roleType" : "SERVICEMONITOR",
      "base" : true,
      "serviceRef" : {
        "serviceName" : "mgmt"
      },
      "config" : {
        "items" : [ {
          "name" : "firehose_heapsize",
          "value" : "612368384"
        }, {
          "name" : "firehose_non_java_memory_bytes",
          "value" : "805306368"
        } ]
      }
    } ]
  },
  "managerSettings" : {
    "items" : [ {
      "name" : "CLUSTER_STATS_START",
      "value" : "10/22/2012 1:40"
    }, {
      "name" : "PUBLIC_CLOUD_STATUS",
      "value" : "ON_PUBLIC_CLOUD"
    }, {
      "name" : "REMOTE_PARCEL_REPO_URLS",
      "value" : "https://archive.cloudera.com/cdh5/parcels/{latest_supported}/,https://archive.cloudera.com/cdh4/parcels/latest/,https://archive.cloudera.com/impala/parcels/latest/,https://archive.cloudera.com/search/parcels/latest/,https://archive.cloudera.com/accumulo/parcels/1.4/,https://archive.cloudera.com/accumulo-c5/parcels/latest/,https://archive.cloudera.com/kafka/parcels/latest/,https://archive.cloudera.com/navigator-keytrustee5/parcels/latest/,https://archive.cloudera.com/spark/parcels/latest/,https://archive.cloudera.com/sqoop-connectors/parcels/latest/"
    } ]
  },
  "allHostsConfig" : {
    "items" : [ {
      "name" : "rm_enabled",
      "value" : "true"
    } ]
  },
  "peers" : [ ],
  "hostTemplates" : {
    "items" : [ ]
  }
  </code></pre>
