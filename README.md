# common-gradle
<!-- TOC -->autoauto- [common-gradle](#common-gradle)auto- [Notes](#notes)auto- [jars](#jars)auto    - [Framework](#framework)auto        - [Spring](#spring)auto            - [spring-boot](#spring-boot)auto        - [Vert.x](#vertx)auto            - [vertx-core](#vertx-core)auto            - [vertx-kotlin and Kotlin-Coroutines](#vertx-kotlin-and-kotlin-coroutines)auto    - [JDBC](#jdbc)auto        - [MySQL](#mysql)auto        - [SQLite](#sqlite)auto        - [MSSQL](#mssql)auto        - [MongoDB](#mongodb)auto        - [postgresql](#postgresql)auto        - [DB2](#db2)auto        - [Oracle](#oracle)auto    - [Parser](#parser)auto        - [JSON](#json)auto            - [gson](#gson)auto            - [fastjson](#fastjson)auto            - [jackson](#jackson)auto            - [json-lib](#json-lib)auto        - [Toml](#toml)auto            - [toml4j](#toml4j)auto        - [HTML](#html)auto            - [jsoup](#jsoup)auto    - [Utils](#utils)auto        - [Apache commons](#apache-commons)auto        - [Guava](#guava)auto        - [vavr](#vavr)auto    - [Kotlin](#kotlin)auto        - [Arrow.kt](#arrowkt)auto    - [Android](#android)auto        - [android-ktx](#android-ktx)auto- [Repositories](#repositories)auto    - [Maven Central](#maven-central)auto    - [google](#google)auto    - [jcenter](#jcenter)auto    - [jitpack jars](#jitpack-jars)auto    - [personal (never mind)](#personal-never-mind)auto    - [Use gradle.properties instead of `ext.xxx` in buildscript](#use-gradleproperties-instead-of-extxxx-in-buildscript)autoauto<!-- /TOC -->

# Notes
> - Badges declare that it is the latest version ~ so it may be not the same to `compile 'orgId:pkgName:$version'`
> - Not specifying repository means that it is in the `mavenCentral()`
> - You'd better consider whether to use `implementation` or `api` instead of `compile`

# jars
## Framework
### Spring
#### spring-boot
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.springframework.boot/spring-boot-starter-web/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.springframework.boot/spring-boot-starter-web/)
```groovy
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
> Vert.x all packages' latest version number is all the same

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.vertx/vertx-core/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.vertx/vertx-core)
#### vertx-core
``` gradle
compile 'io.vertx:vertx-core:+'
```

#### vertx-kotlin and Kotlin-Coroutines
```groovy
compile 'io.vertx:vertx-lang-kotlin:+'
compile 'io.vertx:vertx-lang-kotlin-coroutines:+'
```

## JDBC
### MySQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/)
```groovy
compile 'mysql:mysql-connector-java:8.0.11'
```

### SQLite
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc)
```groovy
compile 'org.xerial:sqlite-jdbc:3.21.0.1'
```
### MSSQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```groovy
compile 'com.microsoft.sqlserver:mssql-jdbc:6.5.2.jre9-preview'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.4.0.jre8'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.2.0.jre7'
```
### MongoDB
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.mongodb/mongo-java-driver/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```groovy
compile "org.mongodb:mongo-java-driver:3.7.0"
```
### postgresql
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql)
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
```groovy
implementation 'com.google.code.gson:gson:2.8.5' 
```
#### fastjson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson)

```groovy
compile 'com.alibaba:fastjson:1.2.47'
// or for Android
compile 'com.alibaba:fastjson:1.1.68.android'
```

#### jackson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind)

```groovy
compile "com.fasterxml.jackson.core:jackson-databind:2.9.5"
```

#### json-lib
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib)

```groovy
compile "net.sf.json-lib:json-lib:2.4"
```
### Toml
#### toml4j
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.moandjiezana.toml/toml4j/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.moandjiezana.toml/toml4j/)
```groovy
compile 'com.moandjiezana.toml:toml4j:0.7.2'
```
### HTML
#### jsoup
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.jsoup/jsoup/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.jsoup/jsoup/)
```groovy
compile "org.jsoup:jsoup:1.11.3"
```

## Utils
### Apache commons
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.apache.commons/commons-lang3/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.apache.commons/commons-lang3/)
```groovy
compile 'org.apache.commons:commons-lang3:3.7'
```

### Guava
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.google.guava/guava/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.google.guava/guava/)
```groovy
compile 'com.google.guava:guava:25.1-jre'
// or, for Android:
api 'com.google.guava:guava:25.1-android'
```

### vavr
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.vavr/vavr/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.vavr/vavr/)
```groovy
compile 'io.vavr:vavr:0.9.2'
```

## Kotlin
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.jetbrains.kotlin/kotlin-stdlib-jdk8/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.jetbrains.kotlin/kotlin-stdlib-jdk8/)
```groovy
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

### Arrow.kt
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.arrow-kt/arrow-core/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.arrow-kt/arrow-core/)
```groovy
dependencies {
    compile 'io.arrow-kt:arrow-core:0.7.2'
    compile 'io.arrow-kt:arrow-syntax:0.7.2'
    compile 'io.arrow-kt:arrow-typeclasses:0.7.2' 
    compile 'io.arrow-kt:arrow-data:0.7.2' 
    compile 'io.arrow-kt:arrow-instances-core:0.7.2'
    compile 'io.arrow-kt:arrow-instances-data:0.7.2'
    kapt    'io.arrow-kt:arrow-annotations-processor:0.7.2' 
}
```
see more at [arrow-kt/arrow](https://github.com/arrow-kt/arrow)
## Http
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.squareup.okhttp3/okhttp/badge.svg?style=flat-square)](https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp)
```groovy
dependencies {
    implementation 'com.squareup.okhttp3:okhttp:3.12.1'
}

## Android
### android-ktx
```groovy
repositories {
    google()
}

dependencies {
    implementation 'androidx.core:core-ktx:1.0.0-alpha1'
}
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
repositories {
    google()
}
```
## jcenter
```groovy
repositories {
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
repositories {
    maven {
        url 'https://raw.github.com/zxj5470/personalMaven/master/'
    }
}
```

## Use gradle.properties instead of `ext.xxx` in buildscript
