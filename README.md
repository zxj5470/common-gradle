# common-gradle

<!-- @import "[TOC]" {cmd="toc" depthFrom=1 depthTo=6 orderedList=false} -->

<!-- code_chunk_output -->

* [common-gradle](#common-gradle)
* [Notes](#notes)
* [jars](#jars)
	* [JDBC](#jdbc)
		* [MySQL](#mysql)
		* [SQLite](#sqlite)
		* [MSSQL](#mssql)
		* [MongoDB](#mongodb)
		* [postgresql](#postgresql)
		* [DB2](#db2)
		* [Oracle](#oracle)
	* [JSON](#json)
		* [gson](#gson)
		* [fastjson](#fastjson)
		* [Jackson](#jackson)
		* [json-lib](#json-lib)
* [Repositories](#repositories)
	* [Maven Central](#maven-central)
	* [google](#google)
	* [jcenter](#jcenter)
	* [jitpack jars](#jitpack-jars)
	* [personal (never mind)](#personal-never-mind)

<!-- /code_chunk_output -->
# Notes
> - Badges declare the latest version~ 
> - Not specifying repository means that it is in `mavenCentral()`

# jars

## JDBC
### MySQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/badge.svg)](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/)
```groovy
compile 'mysql:mysql-connector-java:8.0.11'
```

### SQLite
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc)
```groovy
compile 'org.xerial:sqlite-jdbc:3.21.0.1'
```
### MSSQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```groovy
compile 'com.microsoft.sqlserver:mssql-jdbc:6.5.2.jre9-preview'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.4.0.jre8'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.2.0.jre7'
```
### MongoDB
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.mongodb/mongo-java-driver/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```groovy
compile "org.mongodb:mongo-java-driver:3.7.0"
```
### postgresql
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql/badge.svg)](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql)
```groovy
compile group: 'postgresql', name: 'postgresql', version: '9.0-801.jdbc4'
```

### DB2
```groovy
compile "com.ibm.db2.jcc:db2jcc4:10.1"
```
### Oracle
> Do not ask why it was... Do you know the law company :joy:
```groovy
repositories{
    maven {
        url 'https://raw.github.com/zxj5470/personalMaven/master/'
    }
}
dependencies {
    compile "com.oracle:ojdbc6:11.1.0.7.0"
}
```
## JSON
### gson 
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson)
```groovy
implementation 'com.google.code.gson:gson:2.8.5' 
```
### fastjson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson)

```groovy
compile 'com.alibaba:fastjson:1.2.47'
compile 'com.alibaba:fastjson:1.1.68.android'
```

### Jackson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind/badge.svg)](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind)

```groovy
compile "com.fasterxml.jackson.core:jackson-databind:2.9.5"
```

### json-lib
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib/badge.svg)](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib)

```groovy
compile "net.sf.json-lib:json-lib:2.4"
```


# Repositories

## Maven Central
```groovy
repositories {
    mavenCentral()
}
```

## google
```groovy
repository{
    google()
}
```
## jcenter
```groovy
repository{
    jcenter()
}
```
## jitpack jars
```groovy
repositories {
    maven { url 'https://jitpack.io' }
}
```
## personal (never mind)
```groovy
repositories{
    maven {
        url 'https://raw.github.com/zxj5470/personalMaven/master/'
    }
}
```
