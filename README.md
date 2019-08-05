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


Start Apache Kafka:

D:\Softwares\kafka_2.11-2.0.0\bin\windows>kafka-server-start.bat ../../config/server.properties

Note: Should start the zookeeper prior to Kafka server.

Run the application from Spring boot 
-------------------

       $ cd your project directory where src and pom.xml is file present.
       $ mvn spring-boot:run
if Maven is not installed, use maven wrapper
       
	   $ mvmw spring-boot:run
    
    Then from postman call your post api
    method: post
    content type: application/json
    http://localhost:8080/api/kafka
    and in the body send the below json
 {
  "field1":"Mohit",
  "field2":"Ranu"
}

