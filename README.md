
kafka installation on mac (assuming java8 or above is already installed)

- brew install kafka
this will install kafka with zookeeper

- zookeeper-server-start /usr/local/etc/kafka/zookeeper.properties
starting zookeeper with default properties

- kafka-server-start /usr/local/etc/kafka/server.properties
starting kafka with default properties

- kafka-topics --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic testTopic
to create a test topic

- kafka-console-producer --broker-list localhost:9092 --topic testTopic

- kafka-console-consumer --bootstrap-server localhost:9092 --topic testTopic --from-beginning




Note: To connect to kafka using java code, need to refer /usr/local/etc/kafka/consumer.properties for default group-id

In case of below error,
{{ java.lang.NoSuchMethodError: org.apache.zookeeper.ZooKeeper.multi(Ljava/lang/Iterable;Lorg/apache/zookeeper/AsyncCallback$MultiCallback;Ljava/lang/Object;)V}}

Env variable $CLASSPATH had contained 
 * $HIVE_HOME/lib/*:.
 * $HADOOP_HOME/lib/*:.

Kafka loaded libraries  from these paths. After remove these classpaths kafka launch well.