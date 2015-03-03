docker-ambari-server
=====

Ambari : 安裝、管理 Hadoop Cluster 的工具，version:1.7.0。

base on [FayeHuang/docker-centos-serf](https://github.com/FayeHuang/docker-centos-serf)

使用方式
-----

執行 fayehuang/ambari-server docker container，預設啟動 sshd(expose 22 port) & ambari-server(expose 8080 port) 兩個 service。

* 可透過設定 **ROOTPASSWORD**=mypassword 指定 root ssh login 密碼。如不指定 root ssh login 密碼，預設密碼為 **changeme**

        docker run -d -p 2222:22 -p 8080:8080 --name=my-ambari-server --hostname=ambari.example.local --dns=127.0.0.1 -e ROOTPASSWORD=<mypassowrd> fayehuang/ambari-server

* 可透過設定 **SERF_JOIN_IP**=1.1.1.1（叢集內任一節點 IP），加入特定的叢集。

        docker run -d -p 2222:22 -p 8080:8080 --name=my-ambari-server --hostname=ambari.example.local --dns=127.0.0.1 -e SERF_JOIN_IP=<node_IP> fayehuang/ambari-server
  
Get Involved
-----

[Hortonworks Ambari 1.7.0 documentations](http://docs.hortonworks.com/HDPDocuments/Ambari-1.7.0.0/index.html)


