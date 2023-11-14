```
wget https://github.com/liquibase/liquibase/releases/download/v4.25.0/liquibase-4.25.0.tar.gz\n
```

```
sudo mkdir -p /opt/liquibase
```

```
sudo tar -xvf liquibase-4.25.0.tar.gz -C /opt/liquibase
```

Install mysql JDBC Driver or find it's path using the following command:

```
dpkg -L mysql-connector-j
```

```
vim .zshrc
OR
vim .bashrc
```

```
export PATH=$PATH:/opt/liquibase
export CLASSPATH=$CLASSPATH:/usr/share/java/mysql-connector-java-8.2.0.jar
```

```
source .zshrc
OR
source .bashrc
```

### Run it using the following command:

```
liquibase --classpath=/usr/share/java/mysql-connector-java-8.2.0.jar --changeLogFile=changelog.xml update
```
