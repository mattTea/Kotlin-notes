Notes on Kotlin
===============

## Mocking tests

Mocking with [MockK](https://github.com/mockk/mockk)

"Mocking is not rocket science" series of [articles on MockK](https://blog.kotlin-academy.com/mocking-is-not-rocket-science-basics-ae55d0aadf2b)


1. Add `MockK` to gradle dependencies
    - In `build.gradle`, add

```java
dependencies {
    // implementation "org.jetbrains.kotlin:kotlin-stdlib-jdk8"
    testImplementation "io.mockk:mockk:1.9"
}
```

2. Include a mocked version of the dependency class (that which isn't under test)

```java
private val plane = mockk<Plane>()
```

## Running all tests

To run all tests (across all test classes in package)

1. From toolbar menu `Run` -> `Run...`

2. `Edit configurations`

3. Create new configuration by clicking `+`

4. Select `JUnit` as type (if that's the test package you're using)

5. Name the configuration `All tests`

6. Set `Test kind` to `All in package`