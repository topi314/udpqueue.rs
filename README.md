
# udpqueue.rs

This is a rust implementation of the original JDA-NAS natives. This can be used to make a minimal modular jar with only the required target natives.


## Setup

[ ![](https://img.shields.io/maven-central/v/club.minnced/udpqueue-api?color=blue&label=udpqueue-api) ](https://search.maven.org/artifact/club.minnced/udpqueue-api)

Supported native platforms:

[ ![](https://img.shields.io/maven-central/v/club.minnced/udpqueue-native-linux-x86-64?color=blue&label=linux-x86-64&logo=linux&logoColor=white) ](https://search.maven.org/artifact/club.minnced/udpqueue-native-linux-x86-64)
[ ![](https://img.shields.io/maven-central/v/club.minnced/udpqueue-native-linux-x86?color=blue&label=linux-x86&logo=linux&logoColor=white) ](https://search.maven.org/artifact/club.minnced/udpqueue-native-linux-x86)
[ ![](https://img.shields.io/maven-central/v/club.minnced/udpqueue-native-win-x86-64?color=blue&label=win-x86-64&logo=linux&logoColor=white) ](https://search.maven.org/artifact/club.minnced/udpqueue-native-win-x86-64)
[ ![](https://img.shields.io/maven-central/v/club.minnced/udpqueue-native-win-x86?color=blue&label=win-x86&logo=linux&logoColor=white) ](https://search.maven.org/artifact/club.minnced/udpqueue-native-win-x86)
[ ![](https://img.shields.io/maven-central/v/club.minnced/udpqueue-native-darwin?color=blue&label=darwin&logo=linux&logoColor=white) ](https://search.maven.org/artifact/club.minnced/udpqueue-native-darwin)

More platforms can be added on request.

While this project is published to maven-central, the lavaplayer commons dependency is currently only available through jcenter. So you will have to depend on jcenter for now.

1. Add the original [jda-nas](https://github.com/sedmelluq/jda-nas) dependency to your project, and exclude `udp-queue` from its transitive dependencies:

```gradle
repositories {
    mavenCentral()
    jcenter()
}

dependencies {
    implementation("com.sedmelluq:jda-nas:1.1.0") {
        exclude(module="udp-queue")
    }
}
```

2. Add udpqueue natives

```gradle
dependencies {
    implementation("club.minnced:udpqueue-native-linux-x86-64:0.1.1")
}
```

Alternatively, you can also install rustup locally on your target platform and build it yourself.

Use `./install.sh <triplet>` to install the jar for your specific platform in maven local. Example: `./install.sh x86_64-unknown-linux-gnu`
