# common-gradle
<!-- TOC -->

- [common-gradle](#common-gradle)
- [Notes](#notes)
- [jars](#jars)
    - [Framework](#framework)
        - [Spring](#spring)
            - [spring-boot](#spring-boot)
        - [Vert.x](#vertx)
            - [vertx-core](#vertx-core)
            - [vertx-kotlin and Kotlin-Coroutines](#vertx-kotlin-and-kotlin-coroutines)
    - [JDBC](#jdbc)
        - [MySQL](#mysql)
        - [SQLite](#sqlite)
        - [MSSQL](#mssql)
        - [MongoDB](#mongodb)
        - [postgresql](#postgresql)
        - [DB2](#db2)
        - [Oracle](#oracle)
    - [Parser](#parser)
        - [JSON](#json)
            - [gson](#gson)
            - [fastjson](#fastjson)
            - [Jackson](#jackson)
            - [json-lib](#json-lib)
        - [Toml](#toml)
            - [toml4j](#toml4j)
        - [HTML](#html)
            - [Jsoup](#jsoup)
    - [Kotlin](#kotlin)
- [Repositories](#repositories)
    - [Maven Central](#maven-central)
    - [google](#google)
    - [jcenter](#jcenter)
    - [jitpack jars](#jitpack-jars)
    - [personal (never mind)](#personal-never-mind)

<!-- /TOC -->
# Notes
> - Badges declare that it is the latest version ~ so it may be not the same to `compile 'orgId:pkgName:$version'`
> - Not specifying repository means that it is in the `mavenCentral()`
> - You'd better consider whether to use `implementation` or `api` instead of `compile`

# jars
## Framework
### Spring
#### spring-boot
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.springframework.boot/spring-boot-starter-web/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.springframework.boot/spring-boot-starter-web/)
```gradle
buildscript {
	ext.springBootVersion = "2.0.2.RELEASE"
	dependencies {
        classpath "org.springframework.boot:spring-boot-gradle-plugin:${springBootVersion}"
    }
}
dependencies {
	compile "org.springframework.boot:spring-boot-starter-web"
	testCompile "org.springframework.boot:spring-boot-starter-test"
}
```
### Vert.x
**Notes:**
> Vert.x all packages' latest version is all the same

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.vertx/vertx-core/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.vertx/vertx-core)
#### vertx-core
``` gradle
compile 'io.vertx:vertx-core:+'
```

#### vertx-kotlin and Kotlin-Coroutines
```gradle
compile 'io.vertx:vertx-lang-kotlin:+'
compile 'io.vertx:vertx-lang-kotlin-coroutines:+'
```

## JDBC
### MySQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/)
```gradle
compile 'mysql:mysql-connector-java:8.0.11'
```

### SQLite
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc)
```gradle
compile 'org.xerial:sqlite-jdbc:3.21.0.1'
```
### MSSQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```gradle
compile 'com.microsoft.sqlserver:mssql-jdbc:6.5.2.jre9-preview'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.4.0.jre8'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.2.0.jre7'
```
### MongoDB
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.mongodb/mongo-java-driver/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```gradle
compile "org.mongodb:mongo-java-driver:3.7.0"
```
### postgresql
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql)
```gradle
compile group: 'postgresql', name: 'postgresql', version: '9.0-801.jdbc4'
```

### DB2
```gradle
compile "com.ibm.db2.jcc:db2jcc4:10.1"
```
### Oracle
> Do not ask why it was... Do you know the law company :joy:
```gradle
repositories {
    maven {
        url 'https://raw.github.com/zxj5470/personalMaven/master/'
    }
}
dependencies {
    compile "com.oracle:ojdbc6:11.1.0.7.0"
}
```
## Parser
### JSON
#### gson 
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson)
```gradle
implementation 'com.google.code.gson:gson:2.8.5' 
```
#### fastjson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson)

```gradle
compile 'com.alibaba:fastjson:1.2.47'
compile 'com.alibaba:fastjson:1.1.68.android'
```

#### Jackson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind)

```gradle
compile "com.fasterxml.jackson.core:jackson-databind:2.9.5"
```

#### json-lib
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib)

```gradle
compile "net.sf.json-lib:json-lib:2.4"
```
### Toml
#### toml4j
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.moandjiezana.toml/toml4j/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.moandjiezana.toml/toml4j/)
```gradle
compile 'com.moandjiezana.toml:toml4j:0.7.2'
```
### HTML
#### Jsoup
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.jsoup/jsoup/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.jsoup/jsoup/)
```gradle
compile "org.jsoup:jsoup:1.11.3"
```
## Kotlin
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.jetbrains.kotlin/kotlin-stdlib-jdk8/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.jetbrains.kotlin/kotlin-stdlib-jdk8/)
```gradle
buildscript {
	ext.kotlin_version = '1.2.31'
    repositories {
        mavenCentral()
    }
    dependencies {
        classpath "org.jetbrains.kotlin:kotlin-gradle-plugin:$kotlin_version"
    }
}
dependencies {
    compile "org.jetbrains.kotlin:kotlin-stdlib-jdk8:$kotlin_version"
}

```

# Repositories

## Maven Central
```gradle
repositories {
    mavenCentral()
}
```

## google
```gradle
repositories {
    google()
}
```
## jcenter
```gradle
repositories {
    jcenter()
}
```
## jitpack jars
```gradle
repositories {
    maven { url 'https://jitpack.io' }
}
```
## personal (never mind)
```gradle
repositories {
    maven {
        url 'https://raw.github.com/zxj5470/personalMaven/master/'
    }
}
```
