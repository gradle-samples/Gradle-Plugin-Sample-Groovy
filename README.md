# Gradle Plugin Sample Groovy

NOTE: You can open this sample inside an IDE using the [IntelliJ native importer](https://www.jetbrains.com/help/idea/gradle.html#gradle_import_project_start) or [Eclipse Buildship](https://projects.eclipse.org/projects/tools.buildship).

This sample shows how to build a Gradle plugin in the Java language.

greeting-plugin/build.gradle:
```groovy
plugins {
    // Apply the Java Gradle plugin development plugin to add support for developing Gradle plugins
    id 'java-gradle-plugin'
}

repositories {
    // Use Maven Central for resolving dependencies.
    // You can declare any Maven/Ivy/file repository here.
    mavenCentral()
}

dependencies {
    // Use JUnit test framework for unit tests
    testImplementation 'junit:junit:4.13'
}

gradlePlugin {
    // Define the plugin
    plugins {
        greeting {
            id = 'com.example.plugin.greeting'
            implementationClass = 'com.example.plugin.GreetingPlugin'
        }
    }
}
```

For a more guided tour with plugin development, see link:[the guides for plugin development](https://gradle.org/guides/?q=Plugin%20Development).

You can also generate this project locally using link:[`gradle init`](https://docs.gradle.org/current/userguide/build_init_plugin.html#sec:java_gradle_plugin).
