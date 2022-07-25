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

The example was inspired from reading: https://wiki.lappsgrid.org/technical/dsl.html

Check out tests in https://github.com/rogerhu/groovy-dsl-example/blob/main/app/src/test/kotlin/groovy/dsl/example/AppTest.kt:

* Example test 1: shows how you need to specify the specific function name (in this case, the `square` function).
* Example test 2: implements a basic `methodMissing` function to capture the function call to `square` in a hashmap.
* Example test 3: implements recursive `methodMissing` function call to invoke the Closures and set the results to a hash map.

# References

* https://github.com/apache/groovy/blob/e6ce56fc27e7640664946eb1a99bdee6fb63547e/src/test/groovy/util/DelegatingScriptTest.groovy
