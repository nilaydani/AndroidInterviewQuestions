# Android Interview Questions
Based on the feedback provided, it seems the candidate has a strong foundation in Android development and Kotlin, with some gaps in understanding and experience in certain areas. To address these gaps and enhance the candidate's knowledge, here is a list of questions and answers that cover the mentioned topics in detail.

### Kotlin Basics

**Q1: What is the difference between `==` and `===` in Kotlin?**

**A1:**
```kotlin
// `==` checks for structural equality (i.e., content equality) and is equivalent to calling the equals() method.
val a = "Kotlin"
val b = "Kotlin"
println(a == b) // true

// `===` checks for referential equality (i.e., whether both references point to the same object).
val c = a
println(a === c) // true
println(a === b) // false, because b is a copy of a, not the same reference.
```

**Q2: How does primitive boxing work in Kotlin, and what is the default access modifier?**

**A2:**
Kotlin handles primitive types and their boxed counterparts seamlessly. When a primitive type is used in a context where an object is required, Kotlin automatically boxes the primitive. The default access modifier in Kotlin is `public`, meaning if no modifier is specified, the declaration is visible everywhere.

### Kotlin Coroutines

**Q3: Can you describe when to use `SupervisorJob` in coroutines?**

**A3:**
`SupervisorJob` is used when you want failure in one of the child coroutines to not propagate to other children or cancel the parent coroutine. It's useful in cases where child coroutines are independent of each other.

**Q4: Explain the difference between Flow and Channels in Kotlin Coroutines.**

**A4:**
- **Flow**: Cold streams that are sequences of values emitted over time. They are not active until collected, making them suitable for representing asynchronous data streams that are triggered on demand.
- **Channels**: Hot streams that are capable of broadcasting values to multiple subscribers. They are active once created, suitable for communication between coroutines in a more imperative way, like sending and receiving messages.

### MVI Architecture Pattern

**Q5: How would you describe the MVI architecture pattern?**

**A5:**
MVI (Model-View-Intent) is an architectural pattern where the `Model` represents the state, `View` displays the state and listens for user actions, and `Intent` represents user actions that change the state. It's a cycle where user actions generate intents, which modify the model, and the new model updates the view.

### SOLID Principles

**Q6: Can you name and describe the SOLID principles?**

**A6:**
- **Single Responsibility Principle**: A class should have only one reason to change, meaning it should have only one job.
- **Open/Closed Principle**: Objects or entities should be open for extension but closed for modification.
- **Liskov Substitution Principle**: Objects of a superclass should be replaceable with objects of a subclass without affecting the correctness of the program.
- **Interface Segregation Principle**: No client should be forced to depend on methods it does not use.
- **Dependency Inversion Principle**: High-level modules should not depend on low-level modules. Both should depend on abstractions.

### Testing in Mobile

**Q7: What are Unit tests and Instrumentation tests in the context of Android development?**

**A7:**
- **Unit tests**: Test the smallest units of code in isolation (e.g., functions or classes) and run on the JVM without needing an Android device or emulator.
- **Instrumentation tests**: Run on a real device or emulator and are used to test the integration of components within the application, including activities, services, and the use of Android framework APIs.

### CI/CD

**Q8: How would you use CI/CD in mobile app development?**

**A8:**
CI/CD (Continuous Integration/Continuous Deployment) automates the building, testing, and deployment of mobile applications. In CI, every change made in the application's codebase is automatically built and tested. If the tests pass, CD automates the deployment of the application to the testing or production environment.

### OkHttp and Interceptors

**Q9: How can interceptors be used in OkHttp for testing?**

**A9:**
Interceptors can modify requests and responses in OkHttp. For testing, you can use interceptors to mock responses or add additional logging for debugging purposes. This allows you to test network interactions in isolation without hitting the actual network.

```kotlin
val okHttpClient = OkHttpClient.Builder()
    .addInterceptor { chain ->
        // Check for specific requests and return mock responses
        val response = /* create mock response */
        response
    }
    .build()
```


Learn collection operators/higher order functions like map, sort, groupby, filter, sumby, fold, reduce, etc. Practice string manipulations like splitting, substring, conversion to int, etc. Learn Collections, Sequences, Pair, etc.

kotlin basics(data class, inheritence, delegation, sealed classes, etc), data class in depth. kotlin collections and high order functions (map, filter, groupby etc) kotlin flow and channels coroutines in depth Architecture patterns MVVM, MVI Solid principles Unit and UI testing Jetpack Compose Advise : Keep your answers brief and very accurate. No long answers jumping here and there, Be technical and to the point.
