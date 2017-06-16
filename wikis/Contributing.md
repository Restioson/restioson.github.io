If you're a kind soul and wish to contribute to Kettle, please read through this document.

## How to Contribute
First, you'll need to [fork this repository](https://github.com/Restioson/kettle-engine/fork). Create a separate branch labeled according to the feature you're introducing (some good names are `optimization-rendering`, `feature-sound`, etc). Make your changes, commit (try to have clear messages) & push them, and start a pull request.

## Style

- No [Hungarian Notation](https://en.wikipedia.org/wiki/Hungarian_notation)
- No `m_` member prefixes
- Always, when possible, use `this`
- Keep the open braces on the same line. E.g:
```kotlin
if (condition) {
    /* ... */
}
```
- Don't put other keywords stuff on end brace lines. E.g:
```kotlin
// Don't do this
try {
    /* ... */
} catch (e: Exception) {
   /* ... */
}

// Do this
try {
   /* ... */
}

catch (e: Exception) {
   /* ... */
}
```
- Use whitespace!
- If necessary, break stuff up into different lines
- Keep style consistent

## General
- Please, *please*, don't break Gradle
- Use pooling where possible
- Make APIs simple and clear
- Avoid unnecessary and temporary allocations
- Use interfaces to generalise if needed
- Do *not* use `I[interface]`! E.g `IMyInterface`
- Where you do you interfaces, try to provide a base implementation (call it something along the lines of `Base[interface]`)
- Use American English in code. This does not apply in comments
- Avoid breaking API changes. Breaking changes are less likely to get merged (there's still a good chance they will be!)
- That being said, where you can, use [defender methods](https://docs.oracle.com/javase/tutorial/java/IandI/defaultmethods.html) in interfaces.
- Use [KDoc](https://kotlinlang.org/docs/reference/kotlin-doc.html) comments!


## Licensing and Attributions
- This project is licensed under the Apache 2.0 license. All your code contributed to this project must be Apache 2.0.
- Do not use `@author` - Git already tracks your contribution
- Don't put copyright statements
- If you copy code from somewhere (preferably don't!) attribute the owner
- Assets included must be licensed under the Creative Commons license (again preferably don't include assets; Content Packages should do this)