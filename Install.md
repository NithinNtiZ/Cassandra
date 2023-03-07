# Step 1: Install Java
```bash
yum -y install java
```
### Now, let’s quickly check the version of java we just installed

```bash
java -version

RESULT:

 openjdk version "1.8.0_201"
 OpenJDK Runtime Environment (build 1.8.0_201-b09)
 OpenJDK 64-Bit Server VM (build 25.201-b09, mixed mode)
 ```

# Step 2: Adding the Cassandra Repo

```bash 
vim /etc/yum.repos.d/cassandra.repo

```
**(click insert on your keyboard and then copy/paste the info below into the repo file)**

```bash 
	
[cassandra]
name=Apache Cassandra
baseurl=https://www.apache.org/dist/cassandra/redhat/311x/
gpgcheck=1
repo_gpgcheck=1
gpgkey=https://www.apache.org/dist/cassandra/KEYS

```
**(after that, click on the escape key to end editing the file)**

```bash
NOTE:  Add the Apache repository of Cassandra to the file /etc/yum.repos.d/cassandra.repo (as the root user). The latest major version is 4.0 and the corresponding distribution name is 40x (with an "x" as the suffix). For older releases use 311x for C* 3.11 series, 30x for {30_version}, 22x for {22_version} and 21x for {21_version}. For example, to add the repository for version 4.0 (40x):
```

# Step 3: Install Cassandra

```bash
yum update -y
yum install cassandra
```

# Step 4: Start Cassandra

```bash
systemctl start  cassandra
systemctl enable cassandra
```