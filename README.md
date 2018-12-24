<!-- vscode-markdown-toc -->
* 1. [Framework](#Framework)
	* 1.1. [Spring](#Spring)
		* 1.1.1. [spring-boot](#spring-boot)
	* 1.2. [Vert.x](#Vert.x)
		* 1.2.1. [vertx-core](#vertx-core)
		* 1.2.2. [vertx-kotlin and Kotlin-Coroutines](#vertx-kotlinandKotlin-Coroutines)
* 2. [JDBC](#JDBC)
	* 2.1. [MySQL](#MySQL)
	* 2.2. [SQLite](#SQLite)
	* 2.3. [MSSQL](#MSSQL)
	* 2.4. [MongoDB](#MongoDB)
	* 2.5. [postgresql](#postgresql)
	* 2.6. [DB2](#DB2)
	* 2.7. [Oracle](#Oracle)
* 3. [Parser](#Parser)
	* 3.1. [JSON](#JSON)
		* 3.1.1. [gson](#gson)
		* 3.1.2. [fastjson](#fastjson)
		* 3.1.3. [jackson](#jackson)
		* 3.1.4. [json-lib](#json-lib)
	* 3.2. [Toml](#Toml)
		* 3.2.1. [toml4j](#toml4j)
	* 3.3. [HTML](#HTML)
		* 3.3.1. [jsoup](#jsoup)
* 4. [Utils](#Utils)
	* 4.1. [Apache commons](#Apachecommons)
	* 4.2. [Guava](#Guava)
	* 4.3. [vavr](#vavr)
* 5. [Kotlin](#Kotlin)
	* 5.1. [Arrow.kt](#Arrow.kt)
* 6. [Http](#Http)
* 7. [Android](#Android)
	* 7.1. [android-ktx](#android-ktx)
* 8. [Maven Central](#MavenCentral)
* 9. [google](#google)
* 10. [jcenter](#jcenter)
* 11. [jitpack jars](#jitpackjars)
* 12. [personal (never mind)](#personalnevermind)
* 13. [Use gradle.properties instead of `ext.xxx` in buildscript](#Usegradle.propertiesinsteadofext.xxxinbuildscript)

<!-- vscode-markdown-toc-config
	numbering=true
	autoSave=true
	/vscode-markdown-toc-config -->
<!-- /vscode-markdown-toc --># common-gradle


# Notes
> - Badges declare that it is the latest version ~ so it may be not the same to `compile 'orgId:pkgName:$version'`
> - Not specifying repository means that it is in the `mavenCentral()`
> - You'd better consider whether to use `implementation` or `api` instead of `compile`

# jars
##  1. <a name='Framework'></a>Framework
###  1.1. <a name='Spring'></a>Spring
####  1.1.1. <a name='spring-boot'></a>spring-boot
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
###  1.2. <a name='Vert.x'></a>Vert.x
**Notes:**
> Vert.x all packages' latest version number is all the same

[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.vertx/vertx-core/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.vertx/vertx-core)
####  1.2.1. <a name='vertx-core'></a>vertx-core
``` gradle
compile 'io.vertx:vertx-core:+'
```

####  1.2.2. <a name='vertx-kotlinandKotlin-Coroutines'></a>vertx-kotlin and Kotlin-Coroutines
```groovy
compile 'io.vertx:vertx-lang-kotlin:+'
compile 'io.vertx:vertx-lang-kotlin-coroutines:+'
```

##  2. <a name='JDBC'></a>JDBC
###  2.1. <a name='MySQL'></a>MySQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/mysql/mysql-connector-java/)
```groovy
compile 'mysql:mysql-connector-java:8.0.11'
```

###  2.2. <a name='SQLite'></a>SQLite
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.xerial/sqlite-jdbc)
```groovy
compile 'org.xerial:sqlite-jdbc:3.21.0.1'
```
###  2.3. <a name='MSSQL'></a>MSSQL
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```groovy
compile 'com.microsoft.sqlserver:mssql-jdbc:6.5.2.jre9-preview'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.4.0.jre8'
compile 'com.microsoft.sqlserver:mssql-jdbc:6.2.0.jre7'
```
###  2.4. <a name='MongoDB'></a>MongoDB
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.mongodb/mongo-java-driver/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.microsoft.sqlserver/mssql-jdbc)
```groovy
compile "org.mongodb:mongo-java-driver:3.7.0"
```
###  2.5. <a name='postgresql'></a>postgresql
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/postgresql/postgresql)
```groovy
compile group: 'postgresql', name: 'postgresql', version: '9.0-801.jdbc4'
```

###  2.6. <a name='DB2'></a>DB2
```groovy
compile "com.ibm.db2.jcc:db2jcc4:10.1"
```
###  2.7. <a name='Oracle'></a>Oracle
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
##  3. <a name='Parser'></a>Parser
###  3.1. <a name='JSON'></a>JSON
####  3.1.1. <a name='gson'></a>gson 
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.google.code.gson/gson)
```groovy
implementation 'com.google.code.gson:gson:2.8.5' 
```
####  3.1.2. <a name='fastjson'></a>fastjson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.alibaba/fastjson)

```groovy
compile 'com.alibaba:fastjson:1.2.47'
// or for Android
compile 'com.alibaba:fastjson:1.1.68.android'
```

####  3.1.3. <a name='jackson'></a>jackson
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.fasterxml.jackson.core/jackson-databind)

```groovy
compile "com.fasterxml.jackson.core:jackson-databind:2.9.5"
```

####  3.1.4. <a name='json-lib'></a>json-lib
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/net.sf.json-lib/json-lib)

```groovy
compile "net.sf.json-lib:json-lib:2.4"
```
###  3.2. <a name='Toml'></a>Toml
####  3.2.1. <a name='toml4j'></a>toml4j
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.moandjiezana.toml/toml4j/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.moandjiezana.toml/toml4j/)
```groovy
compile 'com.moandjiezana.toml:toml4j:0.7.2'
```
###  3.3. <a name='HTML'></a>HTML
####  3.3.1. <a name='jsoup'></a>jsoup
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.jsoup/jsoup/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.jsoup/jsoup/)
```groovy
compile "org.jsoup:jsoup:1.11.3"
```

##  4. <a name='Utils'></a>Utils
###  4.1. <a name='Apachecommons'></a>Apache commons
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.apache.commons/commons-lang3/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/org.apache.commons/commons-lang3/)
```groovy
compile 'org.apache.commons:commons-lang3:3.7'
```

###  4.2. <a name='Guava'></a>Guava
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.google.guava/guava/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/com.google.guava/guava/)
```groovy
compile 'com.google.guava:guava:25.1-jre'
// or, for Android:
api 'com.google.guava:guava:25.1-android'
```

###  4.3. <a name='vavr'></a>vavr
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/io.vavr/vavr/badge.svg?style=flat-square)](https://maven-badges.herokuapp.com/maven-central/io.vavr/vavr/)
```groovy
compile 'io.vavr:vavr:0.9.2'
```

##  5. <a name='Kotlin'></a>Kotlin
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

###  5.1. <a name='Arrow.kt'></a>Arrow.kt
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
##  6. <a name='Http'></a>Http
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.squareup.okhttp3/okhttp/badge.svg?style=flat-square)](https://mvnrepository.com/artifact/com.squareup.okhttp3/okhttp)
```groovy
dependencies {
    implementation 'com.squareup.okhttp3:okhttp:3.12.1'
}
```

##  7. <a name='Android'></a>Android
###  7.1. <a name='android-ktx'></a>android-ktx
```groovy
repositories {
    google()
}

dependencies {
    implementation 'androidx.core:core-ktx:1.0.0-alpha1'
}
```

# Repositories

##  8. <a name='MavenCentral'></a>Maven Central
```groovy
repositories {
    mavenCentral()
}
```

##  9. <a name='google'></a>google
```groovy
repositories {
    google()
}
```
##  10. <a name='jcenter'></a>jcenter
```groovy
repositories {
    jcenter()
}
```
##  11. <a name='jitpackjars'></a>jitpack jars
```groovy
repositories {
    maven { url 'https://jitpack.io' }
}
```
##  12. <a name='personalnevermind'></a>personal (never mind)
```groovy
repositories {
    maven {
        url 'https://raw.github.com/zxj5470/personalMaven/master/'
    }
}
```

##  13. <a name='Usegradle.propertiesinsteadofext.xxxinbuildscript'></a>Use gradle.properties instead of `ext.xxx` in buildscript
