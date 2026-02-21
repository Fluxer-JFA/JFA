![Maven Central Version](https://img.shields.io/maven-central/v/net.astr4y/JFA)
![GitHub License](https://img.shields.io/github/license/Fluxer-JFA/JFA)


# Java Fluxer API (JFA)

Hello! This is a very WIP side-project to port Discord JDA over to the Fluxer platform

Fluxer Support Server: https://fluxer.gg/uDRbgH0L

## 📖 Overview
This open source library is intended for implementing bots on Fluxer using the real-time gateway and REST API, and allow for the reletively easy porting of Discord JDA bots to Fluxer. It provides event based functionality to implement bots of any kind, allowing for effective and scalable applications.

## ❗Installation
![Maven Central Version](https://img.shields.io/maven-central/v/net.astr4y/JFA)

This library is available on maven central. The latest version is always shown in the [GitHub Release](https://github.com/Fluxer-JFA/JFA/releases/latest).

The minimum java version supported by JFA is **Java SE 8**. JFA also uses JSR 305 to support solid interoperability with Kotlin out of the box.

> [!NOTE]
> JFA currently does not support audio or video connections. Audio and video port will be added soon.

### Gradle

```gradle
repositories {
    mavenCentral()
}

dependencies {
    implementation("net.astr4y:JFA:$version") { // replace $version with the latest version
      // Optionally disable audio natives to reduce jar size by excluding `opus-java` and `tink`
      // Gradle DSL:
      // exclude module: 'opus-java' // required for encoding audio into opus, not needed if audio is already provided in opus encoding
      // exclude module: 'tink' // required for encrypting and decrypting audio
      // Kotlin DSL:
      // exclude(module="opus-java") // required for encoding audio into opus, not needed if audio is already provided in opus encoding
      // exclude(module="tink") // required for encrypting and decrypting audio
    }
}
```

### Maven

```xml
<dependency>
    <groupId>net.astr4y</groupId>
    <artifactId>JFA</artifactId>
    <version>$version</version> <!-- replace $version with the latest version -->
    <!-- Optionally disable audio natives to reduce jar size by excluding `opus-java` and `tink` -->
    <exclusions>
        <!-- required for encoding audio into opus, not needed if audio is already provided in opus encoding
        <exclusion>
            <groupId>club.minnced</groupId>
            <artifactId>opus-java</artifactId>
        </exclusion> -->
        <!-- required for encrypting and decrypting audio
        <exclusion>
            <groupId>com.google.crypto.tink</groupId>
            <artifactId>tink</artifactId>
        </exclusion> -->
    </exclusions>
</dependency>
```