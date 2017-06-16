If you wish to log messages, the recommended way is to use [kotlin-logging](https://github.com/MicroUtils/kotlin-logging) (slf4j + logback backend), which is included in the core project. You can use slf4j or logback classes if required.

## Example
```kotlin
class MyClass {

    companion object: KLogging()
    
    fun doStuff() {

        /*
         * Each message will show up with a "finer" log level than the last
         * It will only be logged if the message's log level is greater or equal to
         * the set log level. For production, INFO is recommended. For debugging,
         * DEBUG is recommended. For even finer debugging, TRACE is recommended
         */

        logger.fatal("This will show up with the FATAL tag")
        logger.error("This will show up with the ERROR tag")
        logger.info("This will show up with the INFO tag")
        logger.debug("This will show up with the DEBUG tag")
        logger.trace("This will show up with the TRACE tag")
    }
}
```

## Lazy Logging
If you have a big `StringBuilder` or formatted string which won't always be logged depending on the log level, you may want to consider lazy logging:
```kotlin
logger.debug { 
    StringBuilder()
        .append("This ")
        .append("is ")
        .append("going ")
        .append("to ")
        .append("take ")
        .append("a ")
        .append("while")
    .toString()
}
```

The lambda passed to `debug` will only be executed if the log level is correct.

