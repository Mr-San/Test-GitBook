![](/assets/QQ截图20170912234149.png)

1. 创建/opt/hdd目录
    cd /opt/
    mkdir hdd
    cd hdd

2. 创建MySQL数据库的hdd用户和hdd数据库
    SERVER_IP = 安装Server的这台机器的IP
    DBHOST = MySQL主机IP/10.123.1.130

    DBUSER = hdd/root
    DBPASSWORD = hdd123/123456
    DBPORT = 3306
    DB = hdd
    
    create user ‘$DBUSER’@’$SERVER_IP’ identified by ‘$DBPASSWORD’;
    create database $DB;
    grant all privileges on $DB.* to $DBUSER@$SERVER_IP identified by ‘$DBPASSWORD’;
    flush privileges;

注：
3. 获取集群信息
    - ZK_HOST = 10.123.1.130:2181,10.123.1.131:2181,10.123.1.132:2181
    - KAFKA_HOST = 10.123.1.159,10.123.1.161
    - ZooKeper上Kafka服务范围：/kafka
    - ZooKeeper上Solr6服务范围：/solr6