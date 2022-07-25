# Groovy DSL Parsing Examples

We can learn how to consume basic Groovy DSLs by a few examples.

Let's assume we have this DSL:

```groovy

square {
  android {
    namespace 'com.squareup.apos'
    useVectorDrawablesSupportLibrary true
  }
}
```

Each brace block (`{`) encapsulates a closure statement.

Check out tests in https://github.com/rogerhu/groovy-dsl-example/blob/main/app/src/test/kotlin/groovy/dsl/example/AppTest.kt:

* Example test 1: shows how you need to specify the specific function name.
* Example test 2 & 3: shows how you can take advantage of the `methodMissing` function to convert these declarations into hashes.

# References

* https://github.com/apache/groovy/blob/e6ce56fc27e7640664946eb1a99bdee6fb63547e/src/test/groovy/util/DelegatingScriptTest.groovy
* https://wiki.lappsgrid.org/technical/dsl.html