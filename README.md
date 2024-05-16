# How-to-Setup-Hadoop-Cluster

Welcome to the comprehensive guide on setting up your very own Hadoop cluster! Hadoop has emerged as a cornerstone technology in the realm of big data processing, enabling organizations to efficiently store and process massive volumes of data across distributed computing environments. Whether you're a seasoned data engineer looking to refine your cluster setup skills or a newcomer eager to delve into the world of distributed computing, this repository is your go-to resource. From the foundational concepts behind Hadoop to detailed step-by-step instructions, we've got you covered. Let's embark on this journey together as we unlock the power of Hadoop to tackle your data processing challenges head-on.

### Some Prerequisites:
A. **RECOMMENDED** - It is advised to use a Linux Installation such as Ubuntu 16.04 on your system to smooth out the process of installation. You can also use Virtual Machine for this purpose. If you are on Windows, you may also use the Windows Subsystem for Linux (WSL). It allows users to install a complete Ubuntu terminal environment in minutes on a Windows machine, allowing cross-platform application development without leaving Windows. You may follow the instruction provided here: https://canonical-ubuntu-wsl.readthedocs-hosted.com/en/latest/

B. You must have SSH installed. If not, then type in the following command:
```
sudo apt-get install ssh
```

C. You must also have PDSH installed. If not, then type in the following command:
```
sudo apt-get install pdsh
```
D. Every command that follows now should be typed inside the folder ``bin/hadoop``.


## Step 1: Download Hadoop Zip File from the website and make some changes in some files:
Preferred site for download:
https://archive.apache.org/dist/hadoop/common/hadoop-3.3.2/hadoop-3.3.2.tar.gz

Unpack the downloaded Hadoop distribution. In the distribution, edit the file etc/hadoop/hadoop-env.sh to define some parameters as follows:
```
# set to the root of your Java installation
export JAVA_HOME=/usr/java/latest
```
Hadoop can also be run on a single-node in a pseudo-distributed mode where each Hadoop daemon runs in a separate Java process.

Use the following:

etc/hadoop/core-site.xml:
```
<configuration>
    <property>
        <name>fs.defaultFS</name>
        <value>hdfs://localhost:9000</value>
    </property>
</configuration>
```

etc/hadoop/hdfs-site.xml:
```
<configuration>
    <property>
        <name>dfs.replication</name>
        <value>1</value>
    </property>
</configuration>
```


## Step 2: Get your ``ssh`` ready:
Type the following command:
```
ssh localhost
```

If you get error while running the above command, then type the following one by one
```
ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa
cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys
chmod 0600 ~/.ssh/authorized_keys
```
Now, run ``ssh localhost`` again and it should work!


## Step 3: HDFS Format:
We need to clear everything in hdfs, and to do so type the following command:
```
bin/hdfs namenode -format
```

## Step 4: Start NameNode daemon and DataNode daemon:
```
sbin/start-dfs.sh
```

Browse the web interface for the NameNode; by default it is available at:

NameNode - http://localhost:9870/

If you get an error in executing the above command, type this:
```
export PDSH_RCMD_TYPE=ssh
sudo service ssh start
sbin/start-dfs.sh
```
