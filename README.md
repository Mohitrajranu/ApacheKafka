# kafka-example

Download Kafka from https://www.apache.org/dyn/closer.cgi?path=/kafka/2.3.0/kafka-2.3.0-src.tgz
 http://mirrors.estointernet.in/apache/kafka/2.2.0/kafka_2.11-2.2.0.tgz
 
zookeeper.properties
# The directory where the snapshot is stored.
dataDir=/tmp/zookeeper
# the port at which the clients will connect
clientPort=2181
# disable the per-ip limit on the number of connections since this is a non-production config
maxClientCnxns=0
server.properties

server.properties
############################# Zookeeper #############################

# Zookeeper connection string (see zookeeper docs for details).
# This is a comma separated host:port pairs, each corresponding to a zk
# server. e.g. "127.0.0.1:3000,127.0.0.1:3001,127.0.0.1:3002".
# You can also append an optional chroot string to the urls to specify the
# root directory for all kafka znodes.
zookeeper.connect=localhost:2181

# Timeout in ms for connecting to zookeeper
zookeeper.connection.timeout.ms=6000

############################# Log Basics #############################

# A comma separated list of directories under which to store log files
log.dirs=/tmp/kafka-logs
/libs directory contain all dependency executables like java, jetty, log4j and etc.

If you are okay with the above default configurations, you are ready to start zookeeper and Kafka server.

Start the Zookeeper:
Go to Kafka_X.XX-X.X.X\bin\windows\


D:\Softwares\kafka_2.11-2.0.0\bin\windows>zookeeper-server-start.bat ../../config/zookeeper.properties
[2018-11-17 03:20:58,713] INFO Reading configuration from: ..\..\config\zookeeper.properties (org.apache.zookeeper.server.quorum.QuorumPeerConfig)
[2018-11-17 03:20:58,713] INFO autopurge.snapRetainCount set to 3 (org.apache.zookeeper.server.DatadirCleanupManager)
[2018-11-17 03:20:58,713] INFO autopurge.purgeInterval set to 0 (org.apache.zookeeper.server.DatadirCleanupManager)
[2018-11-17 03:20:58,713] INFO Purge task is not scheduled. (org.apache.zookeeper.server.DatadirCleanupManager)
[2018-11-17 03:20:58,713] WARN Either no config or no quorum defined in config, running  in standalone mode (org.apache.zookeeper.server.quorum.QuorumPeerMain)
[2018-11-17 03:20:58,744] INFO Reading configuration from: ..\..\config\zookeeper.properties (org.apache.zookeeper.server.quorum.QuorumPeerConfig)
[2018-11-17 03:20:58,744] INFO Starting server (org.apache.zookeeper.server.ZooKeeperServerMain)
[2018-11-17 03:21:03,261] INFO Server environment:zookeeper.version=3.4.13-2d71af4dbe22557fda74f9a9b4309b15a7487f03, built on 06/29/2018 00:39 GMT (org.apache.zookeeper.server.ZooKeeperServer)
.............
.............
[2018-11-17 03:21:03,345] INFO Using org.apache.zookeeper.server.NIOServerCnxnFactory as server connection factory (org.apache.zookeeper.server.ServerCnxnFactory)
[2018-11-17 03:21:03,345] INFO binding to port 0.0.0.0/0.0.0.0:2181 (org.apache.zookeeper.server.NIOServerCnxnFactory)
[2018-11-17 03:21:35,434] INFO Accepted socket connection from /127.0.0.1:63924 (org.apache.zookeeper.server.NIOServerCnxnFactory)
[2018-11-17 03:21:35,450] INFO Client attempting to establish new session at /127.0.0.1:63924 (org.apache.zookeeper.server.ZooKeeperServer)
[2018-11-17 03:21:35,450] INFO Creating new log file: log.5 (org.apache.zookeeper.server.persistence.FileTxnLog)
[2018-11-17 03:21:35,535] INFO Established session 0x1000238240f0000 with negotiated timeout 6000 for client /127.0.0.1:63924 (org.apache.zookeeper.server.ZooKeeperServer)

Start Apache Kafka:

D:\Softwares\kafka_2.11-2.0.0\bin\windows>kafka-server-start.bat ../../config/server.properties
[2018-11-17 03:21:30,291] INFO Registered kafka:type=kafka.Log4jController MBean (kafka.utils.Log4jControllerRegistration$)
[2018-11-17 03:21:30,777] INFO starting (kafka.server.KafkaServer)
[2018-11-17 03:21:30,777] INFO Connecting to zookeeper on localhost:2181 (kafka.server.KafkaServer)
[2018-11-17 03:21:30,831] INFO [ZooKeeperClient] Initializing a new session to localhost:2181. (kafka.zookeeper.ZooKeeperClient)
[2018-11-17 03:21:35,350] INFO Client environment:zookeeper.version=3.4.13-2d71af4dbe22557fda74f9a9b4309b15a7487f03, built on 06/29/2018 00:39 GMT (org.apache.zookeeper.ZooKeeper)
[2018-11-17 03:21:35,350] INFO Client environment:host.name=DESKTOP-RN4SMHT (org.apache.zookeeper.ZooKeeper)
[2018-11-17 03:21:35,350] INFO Client environment:java.version=9.0.4 (org.apache.zookeeper.ZooKeeper)
[2018-11-17 03:21:35,350] INFO Client environment:java.vendor=Oracle Corporation (org.apache.zookeeper.ZooKeeper)
[2018-11-17 03:21:35,350] INFO Client environment:java.home=C:\Program Files\Java\jdk-9.0.4 (org.apache.zookeeper.ZooKeeper)
................
................
[2018-11-17 03:21:43,100] INFO [ProducerId Manager 0]: Acquired new producerId block (brokerId:0,blockStartProducerId:0,blockEndProducerId:999) by writing to Zk with path version 1 (kafka.coordinator.transaction.ProducerIdManager)
[2018-11-17 03:21:43,138] INFO [TransactionCoordinator id=0] Starting up. (kafka.coordinator.transaction.TransactionCoordinator)
[2018-11-17 03:21:43,154] INFO [TransactionCoordinator id=0] Startup complete. (kafka.coordinator.transaction.TransactionCoordinator)
[2018-11-17 03:21:43,154] INFO [Transaction Marker Channel Manager 0]: Starting (kafka.coordinator.transaction.TransactionMarkerChannelManager)
[2018-11-17 03:21:43,200] INFO [/config/changes-event-process-thread]: Starting (kafka.common.ZkNodeChangeNotificationListener$ChangeEventProcessThread)
[2018-11-17 03:21:43,235] INFO [SocketServer brokerId=0] Started processors for 1 acceptors (kafka.network.SocketServer)
[2018-11-17 03:21:43,238] INFO Kafka version : 2.0.0 (org.apache.kafka.common.utils.AppInfoParser)
[2018-11-17 03:21:43,238] INFO Kafka commitId : 3402a8361b734732 (org.apache.kafka.common.utils.AppInfoParser)
[2018-11-17 03:21:43,238] INFO [KafkaServer id=0] started (kafka.server.KafkaServer)
Note: Should start the zookeeper prior to Kafka server.
