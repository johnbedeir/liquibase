# Liquibase Installation and Setup Guide

This guide provides step-by-step instructions for installing Liquibase and setting up the MySQL JDBC driver on your system.

## Step 1: Download Liquibase

First, download the Liquibase package:

```bash
wget https://github.com/liquibase/liquibase/releases/download/v4.25.0/liquibase-4.25.0.tar.gz
```

## Step 2: Extract and Install Liquibase

Create a directory for Liquibase and extract the downloaded package into it:

```bash
sudo mkdir -p /opt/liquibase
sudo tar -xvf liquibase-4.25.0.tar.gz -C /opt/liquibase
```

## Step 3: Install MySQL JDBC Driver

Install the MySQL JDBC Driver or locate its path using the following command:

```bash
dpkg -L mysql-connector-j
```

## Step 4: Configure Environment Variables

Edit your shell configuration file (.zshrc for Zsh or .bashrc for Bash) to include Liquibase and the JDBC driver in your PATH and CLASSPATH environment variables:

```bash
vim .zshrc # For Zsh users
# OR
vim .bashrc # For Bash users
```

Add the following lines to your shell configuration file:

```bash
export PATH=$PATH:/opt/liquibase
export CLASSPATH=$CLASSPATH:/usr/share/java/mysql-connector-java-8.2.0.jar
```

## Step 5: Apply Configuration Changes

Apply the changes to your current shell session:

```bash
source .zshrc # For Zsh users
# OR
source .bashrc # For Bash users
```

## Step 6: Run Liquibase

Use the following command to run Liquibase with the specified classpath and changelog file:

```bash
liquibase --classpath=/usr/share/java/mysql-connector-java-8.2.0.jar --changeLogFile=changelog.xml update
```

---
