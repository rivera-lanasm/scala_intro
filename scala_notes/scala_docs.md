
#### https://docs.scala-lang.org/tour/tour-of-scala.html

#### ============================================
## Part 1
#### ============================================
scala is **pure OO** --> every value is an object <br>
**types and behaviors** of objects are described by **classes and traits** <br>
Classes can be **Extended by subclassing** <br>
**mixin-based composition** replaces multiple inheritance 



scala is functional --> **every function is a value** <br>
support for **currying, higher order functons, singelton objects, pattern matching, nested functions, for comprehensions, extractor objects, and case classes**


#### ============================================
## Part 2
#### ============================================

**named results --> values** --> `val x = 1`

**Variables are like values**, except you can re-assign them <br>
`var x = 1`

**combine expressions** by surrounding them with `{}` <br>
`println({`<br>
  `val x = 1 + 1` <br>
  `x + 1 })`

**lambda functions** `(x: Int) => x + 1` <br>
**named functions** `val add = (x: Int, y: Int) => x + y + 1` <br>

**methods vs. functions**
https://tpolecat.github.io/2014/06/09/methods-functions.html
- eta expansion --> methods as function values
- methods can have multiple parameter lists
`def add(x: Int, y: Int): Int = x + y`


**Classes**
`class Greeter(prefix: String, suffix: String) {` <br>
`  def greet(name: String): Unit = ` <br>
`    println(prefix + name + suffix)  }`

- return type: **Unit** --> nothing meaningful to return...caries no info 
- use **new** to instantiate class <br>
`val greeter = new Greeter("Hello, ", "!")`



**Case Classes: FP**
- plain and immutable data-holding objects that should exclusively depend on their constructor arguments
- instances of cc are immutable by default
- compared by value, whereas class instances are compared by reference --> useful for pattern matching

`case class Point(x: Int, y: Int)` <br>
- You can instantiate case classes without the new keyword:
`val point = Point(1, 2)`
- instances of case classes are compared by value, not by reference:


**Objects**
- single instances of own definitions
- singletons of their own classes

`object IdFactory { `<br>
`  private var counter = 0` <br>
`  def create(): Int = { `<br>
`    counter += 1 `<br>
`    counter ` <br>
`  }  } `

- access object by referring to its name 
`val newId: Int = IdFactory.create()`


**Traits**
- abstract data types with fields and methods 
- Scala inheritance: a class can only extend one other class, but it can extend **multiple traits**

~~~
trait Greeter {
  def greet(name: String): Unit
}
~~~

**extends and override: Traits**
~~~
class DefaultGreeter extends Greeter

class CustomizableGreeter(prefix: String, postfix: String) extends Greeter {
  override def greet(name: String): Unit = {
    println(prefix + name + postfix)
  }
}

val greeter = new DefaultGreeter()
greeter.greet("Scala developer") // Hello, Scala developer!

val customGreeter = new CustomizableGreeter("How are you, ", "?")
customGreeter.greet("Scala developer") // How are you, Scala developer?
~~~

**Main Method**
- JVM requires a main method, named main
- takes one argument, an array of strings

~~~
object Main {
  def main(args: Array[String]): Unit =
    println("Hello, Scala developer!")
}
~~~

#### ============================================
## Part 3: Unified Types
#### ============================================

**type hierarchy**
- all values have a type
- **Any** is supertype of a ll types --> defines universal methods like equals, hashCode, etc.
- Any two direct subclasses --> 1) AnyVal 2) AnyRef
- **AnyVal** represents value types
- **AnyRef** represents reference types --> all non value types
- exanoke of Any:
~~~
val list: List[Any] = List(
  "a string",
  732,  // an integer
  'c',  // a character
  true, // a boolean value
  () => "an anonymous function returning a string"
)
~~~


**Type Casting**
- Casting is **unidirectional**

**Nothing and Null**
- Nothing is a subtype of all types --> the botton type
- no value has type Nothing
- **Null** is a subtype of all reference types (AnyRef) --> **rarely used**


#### ============================================
## Part 4: Defining a class
#### ============================================

- **new** used to create instance of class

~~~
class Point(var x: Int, var y: Int) {

  def move(dx: Int, dy: Int): Unit = {
    x = x + dx
    y = y + dy
  }

  override def toString: String =
    s"($x, $y)"
}

val point1 = new Point(2, 3)
point1.x  // 2
println(point1)  // prints (2, 3)
~~~

- class members include variables and methods
- **the class constructor** is the **class signature** --> `(var x: Int, var y: Int)`

**Constructors**




