# How-to-Setup-Hadoop-Cluster

Welcome to the comprehensive guide on setting up your very own Hadoop cluster! Hadoop has emerged as a cornerstone technology in the realm of big data processing, enabling organizations to efficiently store and process massive volumes of data across distributed computing environments. Whether you're a seasoned data engineer looking to refine your cluster setup skills or a newcomer eager to delve into the world of distributed computing, this repository is your go-to resource. From the foundational concepts behind Hadoop to detailed step-by-step instructions, we've got you covered. Let's embark on this journey together as we unlock the power of Hadoop to tackle your data processing challenges head-on.

### Some Prerequisites:
A. **RECOMMENDED** - It is advised to use a Linux Installation such as Ubuntu 16.04 on your system to smooth out the process of installation. You can also use Virtual Machine for this purpose. If you are on Windows, you may also use the Windows Subsystem for Linux (WSL). It allows users to install a complete Ubuntu terminal environment in minutes on a Windows machine, allowing cross-platform application development without leaving Windows. You may follow the instruction provided here: https://canonical-ubuntu-wsl.readthedocs-hosted.com/en/latest/

B. You must have SSH installed. If not, then type in the following command:
```
 $ sudo apt-get install ssh
```

C. You must also have PDSH installed. If not, then type in the following command:
```
$ sudo apt-get install pdsh
```

## Step 1: Download Hadoop Zip File from the website:
Preferred site for download:
https://archive.apache.org/dist/hadoop/common/hadoop-3.3.2/hadoop-3.3.2.tar.gz

## Step 2: Get your ``ssh`` ready:
First, unzip the hadoop folder and go to ``bin/hadoop``. Then type the following command:
```
$ ssh localhost
```
