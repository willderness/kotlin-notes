# Kotlin Notes

## Class Declaration

**Java**

package.com.mclean.fun

```java
public class Foo {
	int bar;
	
	public Foo(int bar) {
		this.bar = bar;
	}
	
	int setBar(int bar) {
		this.bar = bar;
	}
}
```

**Kotlin**

Fun.kt

```kotlin
class Foo( var bar: int) {
	var bar: int set() {
		// Setter
	} 
}
```

- Classes are public by default
- Packages are not hierarchical

## Functions

**Returns can be implicit if the compiler can figure out the typing**

**All params must be explicitly typed**

```kotlin
fun fooBar(name: String) = name + " FooBar"
```

**Void functions return a Unit object**

```kotlin
// returns Unit
fun fooBar() {
  println("Foobar")
}
```
**Functions are first class entities in the Kotlin language**

```kotlin
fun foo(): String = "Foo"
fun bar(): String = "Bar"

fun fooBar(fooFun: () -> String, barFun: () -> String): String {
	return fooFun() + barFun()
}

fun main(args: Array<String>) {
	println(fooBar(::foo, ::bar))
}
```

**Kotlin supports lambdas**

```kotlin
val doubled = ints.map { value -> value * 2 }
```

**"it" is the implicit name of a single paramater**

```kotlin
ints.map { it * 2 }
```