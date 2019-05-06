# Set-up

[Kotlin Lang docs](https://kotlinlang.org/docs/reference/)

1. Install JVM SDK (`brew install java`)
2. Install gradle (`brew install gradle`)
3. Create a [new gradle project](https://www.jetbrains.com/help/idea/gradle.html#gradle_create_project) (this creates a much richer project structure including `main` and `test` folders in `src`)
4. (Following steps in _TDD with intelliJ_ below)
    - _NOTE: None of the following steps so far required_
    - Add JUnit on the project classpath, either by [adding a test library](https://www.jetbrains.com/help/idea/configuring-testing-libraries.html), or adding a dependency in [Gradle](https://www.jetbrains.com/help/idea/gradle.html) (link better [here](https://www.jetbrains.com/help/idea/gradle.html#gradle_source_sets)) or [Maven](https://www.jetbrains.com/help/idea/maven-support.html).

5. Write your [first test](https://www.jetbrains.com/help/idea/tdd-with-intellij-idea.html#102374cc)

6. GIT (for future ref!)
    - I got this error when doing a `git add .` -> `fatal: CRLF would be replaced by LF in gradlew.bat.`
    - This [SO](https://stackoverflow.com/questions/20168639/git-commit-get-fatal-error-fatal-crlf-would-be-replaced-by-lf-in) suggested `git config --global core.autocrlf false`
    - So I did that, and it allowed me to add and commit files 

## IDE and SDK

- IntelliJ IDEA (IDE)
- JVM (SDK)
  - `java -version` to check
  - Otherwise install using `homebrew`


## Gradle

- [Creating a new gradle project](https://www.jetbrains.com/help/idea/gradle.html#gradle_create_project)

- [Configuring and using a Gradle test runner](https://www.jetbrains.com/help/idea/gradle.html#configure_gradle_test_runner)

- [Gradle](https://docs.gradle.org/current/userguide/what_is_gradle.html) is a build automation tool


# Test-driving with Kotlin

- [TDD with intelliJ](https://www.jetbrains.com/help/idea/tdd-with-intellij-idea.html)

## Which framework?

- [kotlin.test](https://kotlinlang.org/api/latest/kotlin.test/index.html)
- [KotlinTest](https://github.com/kotlintest/kotlintest)
- [JUnit5]()
- [Spek](https://github.com/spekframework/spek)
- [Spek user guide](https://spekframework.github.io/spek/docs/latest/) <--
- JBehave?

- Mockk (for mocking)


### Useful links

Gradle, Spek and Kotlin guide... https://medium.com/@98elements/kotlin-gradle-spek-2-junit-5-a-simple-guide-4c8ab3ce6359 <--
- Framework is inspired heavily by RSpec so Ruby developers will feel at home and find familiar keywords, like describe, context, and it blocks - yay!
- JUnit 5 dependency is required as Spek 2 doesn’t provide any assertions library. See JUnit 5 User Guide for a detailed documentation. Alternatives include kotlin-test, HamKrest, Expekt, and Kluent.

Best practice and an overview of a few Kotlin and Java test libraries... https://phauer.com/2018/best-practices-unit-testing-kotlin/

Spek examples... https://academy.realm.io/posts/kau-laura-kogler-kotlin-testing/

JUnit (I think) examples... https://spin.atomicobject.com/2018/10/07/kotlin-unit-testing/

Java TDD with JUnit 4 example (highlights possible file structure)... https://www.jetbrains.com/help/idea/tdd-with-intellij-idea.html

https://developerlife.com/2018/10/21/kotlin-testing-setup/

https://jl.githost.io/build-camp/base-camp

JUnit 4 examples file and structure... https://github.com/abreslav/introduction-to-kotlin/blob/master/kotlin-examples/src/_07_annotations/Tests.kt

Kotlin example tests... https://github.com/JetBrains/kotlin-examples/blob/master/gradle/mixed-java-kotlin-hello-world/src/test/kotlin/tests.kt