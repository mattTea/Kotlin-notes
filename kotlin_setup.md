Kotlin Project Set-up
=====================

[Kotlin Lang docs](https://kotlinlang.org/docs/reference/)

## Global set-up

1. Install JVM SDK (`brew install java`)
2. Install gradle (`brew install gradle`)

------

## Project set-up

3. Create a [new gradle project](https://www.jetbrains.com/help/idea/gradle.html)
    - (This creates a gradle project structure that includes `main` and `test` folders in `src`)

    - `File` -> `New` -> `Project...`

    ![new project](https://github.com/mattTea/Kotlin-notes/blob/master/images/new_project.png)

    - Select `Gradle` on the left
    - Select Java version in `Project SDK` dropdown
    - Select `Kotlin/JVM` checkbox in 'Additional libraries and frameworks' list
    - Click `Next`

    - `GroupId` should be populated as per [Maven naming convention](https://maven.apache.org/guides/mini/guide-naming-conventions.html) if you wish to deploy with Maven
        - (This can be left blank if only to be deployed locally) 

    - `ArtifactId` should be populated with the name of your project 
    - `Version` should be populated by default

    - Suggestion to leave default setting on following page of wizard
        - Use auto-import
        - Group modules: using explicit module groups
        - Create separate module per source set
        - Use default Gradle wrapper (recommended)
        - Gradle JVM: Use project JDK

    ![gradle setup wizard](https://github.com/mattTea/Kotlin-notes/blob/master/images/kotlin_gradle_setup.png)


    - Click `Next`

    - Check project name and location and click `Finish`

    - Project should build and include a `src` folder containing `main` and `test` folders

    ![project structure](https://github.com/mattTea/Kotlin-notes/blob/master/images/gradle_project_structure.png)

------

## Write tests

4. Write your first test

    - Not quite perfectly test-driven, but create your first class file in `/src/main/kotlin`
        - `New` -> `Kotlin File/Class`

    ```kotlin
    class Greeting {

    }
    ```

    - Create a test
        - Click on class name (`Greeting` in the above example)
        - Press `alt` + `Return` or click the lightbulb icon and click `Create test`

        ![create test](https://github.com/mattTea/Kotlin-notes/blob/master/images/create_test.png)

        - Select testing library (e.g. JUnit4)
        - If this library is not found in module, click `Fix` and add with default values
        - Choose destination directory as `../src/test/kotlin`

        - Then write your first test...

        ```kotlin
        import org.junit.Assert.assertEquals
        import org.junit.jupiter.api.Test
        
        class GreetingTest {

            private val greeting = Greeting()

            @Test
            fun `Returns 'hello'`() {
                assertEquals("Hello", greeting.greet())
            }
        }
        ```
    
    - Run the test to see it fail

    - Fill out the original class file to pass the test...

        ```kotlin
        class Greeting {

            fun greet(): String {
                return "Hello"
            }
        }
        ```

    - Run tests and hopefully see it pass!


5. Notes if build doesn't compile, check gradle settings, the following work for my simple projects. Check...

    - `Use auto-import`
    - `using explicit module groups`
    - Delegate settings, both set to `IntelliJ IDEA`

![gradle setting](https://github.com/mattTea/Kotlin-notes/blob/master/images/gradle_settings.png)


------

## Resources & references

### Git

- I got this error when doing a `git add .` -> `fatal: CRLF would be replaced by LF in gradlew.bat.`
- This [SO](https://stackoverflow.com/questions/20168639/git-commit-get-fatal-error-fatal-crlf-would-be-replaced-by-lf-in) suggested `git config --global core.autocrlf false`
- So I did that, and it allowed me to add and commit files 


### IDE and SDK

- IntelliJ IDEA (IDE)
- JVM (SDK)
  - `java -version` to check
  - Otherwise install using homebrew -> `brew install java`


### Gradle

- [Creating a new gradle project](https://www.jetbrains.com/help/idea/gradle.html#gradle_create_project)

- [Configuring and using a Gradle test runner](https://www.jetbrains.com/help/idea/gradle.html#configure_gradle_test_runner)

- [Gradle](https://docs.gradle.org/current/userguide/what_is_gradle.html) is a build automation tool


### Test-driving with Kotlin

- [TDD with intelliJ](https://www.jetbrains.com/help/idea/tdd-with-intellij-idea.html)


### Test frameworks

- [kotlin.test](https://kotlinlang.org/api/latest/kotlin.test/index.html)
- [KotlinTest](https://github.com/kotlintest/kotlintest)
- [JUnit5]()
- [Spek](https://github.com/spekframework/spek)
- [Spek user guide](https://spekframework.github.io/spek/docs/latest/) <--
- JBehave?

- Mockk (for mocking)


### Links

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


[Gradle testing in JVM projects](https://docs.gradle.org/current/userguide/java_testing.html)
- Includes good info on config in `build.gradle`