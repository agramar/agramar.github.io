1. 하둡 다운로드
- http://www.apache.org/dyn/closer.cgi/hadoop/common/
```bash
$ sudo wget "http://apache.mirror.cdnetworks.com/hadoop/common/hadoop-2.7.4/hadoop-2.7.4.tar.gz"
$ sudo wget "http://apache.mirror.cdnetworks.com/hadoop/common/hadoop-2.7.4/hadoop-2.7.4-src.tar.gz"
```

2. 압축 해제
```bash
$ sudo tar -xzvf hadoop-2.7.4.tar.gz
```

3. 환경 설정
```bash
# cd /usr/local/src/hadoop/etc/hadoop
# vim hadoop-env.sh
```

```
export JAVA_HOME=${JAVA_HOME}
```

```bash
# vim ~/.bashrc
```

```
#HADOOP VARIABLES START
export JAVA_HOME=/usr/lib/jvm/java-8-oracle
export HADOOP_INSTALL=/usr/local/hadoop
export PATH=$PATH:$HADOOP_INSTALL/bin
export PATH=$PATH:$HADOOP_INSTALL/sbin
export HADOOP_MAPRED_HOME=$HADOOP_INSTALL
export HADOOP_COMMON_HOME=$HADOOP_INSTALL
export HADOOP_HDFS_HOME=$HADOOP_INSTALL
export YARN_HOME=$HADOOP_INSTALL
export HADOOP_COMMON_LIB_NATIVE_DIR=$HADOOP_INSTALL/lib/native
export HADOOP_OPTS="-Djava.library.path=$HADOOP_INSTALL/lib/native"
#HADOOP VARIABLES END
```

```bash
# source ~/.bashrc
```