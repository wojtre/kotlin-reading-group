# kotlin-reading-group
Some Kotlin's lambdas examples for kotlin reading group meeting.

(5.1)
1. Basics 
Syntax:     
* {x: Int, y: Int -> x + y} - brackets around whole lamda, not only body - does not need context
    
* simplier: {x, y -> x + y }
* simplier: { it.doSth()} - default parameter, don;t abuse it, sometimes better to name it different for clean code
* by method reference people.maxBy(Person::age)
* bound member  Person p    p::age
* local methods ::someMethod  listing 5.2
* map.forEach { _, value -> println("$value!") }  - ignore unused variables

 Listing 3.1
 
 2. Running lambdas
 * {print("Hello")}()
 * run({print("Hello")})
 
 As func argument
 fun test (myLamda:(Int, Int -> Unit))
 * test({x,y->print(x+y)}
 * test() {x,y -> print(x+y)}
 * test {x,y -> print(x+y)}
 
 Listing 3.2, 3.3
 
 3. Returning values
 * list.map({el -> el*2})  - last row as return
 * list.map {el -> return@map el*2}                   - qualified return (without it returns from local function)
 https://kotlinlang.org/docs/reference/returns.html#return-at-labels
 * list.map @qualifier{el -> return@qualifier el*2}
 
 4. Variables scope
 * in contrary to java we can access final variables
 * in java new double[0], in kotlin var a = 323.32 
 * values are stored with lambdas code in wrappers
 
 
 Listing 4.2
 
(5.2)
5. Functional APIs for collection
* map, filter
* all, any, count, find
* groupBy
* flatten, flatMap
* between every operation is a new collection being created

6. Lazy collections
* intermediate operations: map, filter
* terminal operations: toList, find
* same concept as streams in java 8
* in sequences doesnt matter if first filter
* generating sequence with genarateSequence and takeWhile

7. Running code from java with kotlin lambdas
* works with functional interfaces (interface with one function) and with SAM (single abstract method)
* kotlin lambdas are converted into anonymous class

8. Lambdas with receivers
* not language feature but library
* with(someVar) {this.toString()} - returns the last expresion
* apply(someVar) {this.doStuff()} - returns received object (this)
