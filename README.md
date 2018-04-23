# kotlin-reading-group
Some Kotlin's lambdas examples for kotlin reading group meeting.

(5.1)
1. Basics 
Syntax:     
* x: Int, y: Int -> x + y}
** brackets around whole lamda, not only body
** does not need context
    
* simplier: {x, y -> x + y }
* simplier: { it.doSth()} - default parameter, don;t abuse it, sometimes better to name it different for clean code
* by method reference people.maxBy(Person::age)
* bound member  Person p    p::age
* local methods ::someMethod  listing 5.2
* map.forEach { _, value -> println("$value!") }  - ignore unused variables

 Listing 3.1
 
 2. Running lambdas
 * {print("Hello")}()
 * run({print("Hello"})
 
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
 
