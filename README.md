# Top10-Friend-Recommendation
Create top 10 friend recommendations for specific users using Apache Hadoop(MapReduce) with Java

## Setting Up Hadoop

1) In hadoop-env.sh, do

        export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.0.1.jdk/Contents/Home

2) Update the configuration files : core-site.xml, hdfs-site.xml, yarn-site.xml, mapred-site.xml.

At command line, navigate to the hadoop home directory and run 

    $ nano etc/hadoop/core-site.xml

    <configuration>
        <property>
            <name>fs.defaultFS</name>
            <value>hdfs://localhost:9000</value>
        </property>
    </configuration>

    $ nano etc/hadoop/hdfs-site.xml

    <configuration>
        <property>
            <name>dfs.replication</name>
            <value>1</value>
        </property>
    </configuration>


    $ nano etc/hadoop/mapred-site.xml

    <configuration>
        <property>
            <name>mapreduce.framework.name</name>
            <value>yarn</value>
        </property>
    </configuration>

    $ nano etc/hadoop/yarn-site.xml

    <configuration>
        <property>
            <name>yarn.nodemanager.aux-services</name>
            <value>mapreduce_shuffle</value>
        </property>
    </configuration>



3) At command line, navigate to the hadoop home directory and run 

        $ bin/hdfs namenode -format 
        $ sbin/start-dfs.sh
        $ sbin/start-yarn.sh 
4）Create Node
        $ bin/hdfs dfs -mkdir /user/zixia
        $ jps

4) When you are done with your work 

        $ sbin/stop-dfs.sh
        $ sbin/stop-yarn.sh
