# lombok-module-jdk10

To reproduce: `./gradlew -Dorg.gradle.java.home=<path.to.your.jdk10> build`

The error I receive is:
```
> Task :compileJava FAILED
/Users/bflint/IdeaProjects/lombok-module-jdk10/src/main/java/module-info.java:2: error: module not found: lombok
    requires lombok;
             ^
1 error

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':compileJava'.
> Compilation failed; see the compiler error output for details.

* Try:
Run with --stacktrace option to get the stack trace. Run with --info or --debug option to get more log output. Run with --scan to get full insights.

* Get more help at https://help.gradle.org

BUILD FAILED in 0s
1 actionable task: 1 executed
```

## My Setup
* MacOS X Sierra (10.12.6)
* Gradle Wrapper Version: 4.7 (this is what the build uses)
* JDK: 10.0.1 (retrieved from https://download.java.net/java/GA/jdk10/10.0.1/fb4372174a714e6b8c52526dc134031e/10/openjdk-10.0.1_osx-x64_bin.tar.gz)
* Gradle Version: 4.4.1 (uses JDK 1.8 for runtime)
* Lombok Version: lombok-edge.jar, version 1.16.21

## Notes
* Also fails using JAVA_HOME instead of org.gradle.java.home property
* I also tried installing lombok-edge in my local maven repo and using the gradle-apt-plugin. I receive the same error as above.
* Also tried using the gradle-lombok plugin with lombok-edge. I receive the same error.