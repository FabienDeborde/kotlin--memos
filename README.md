# Kotlin

- val -> *const*
- var -> *let*

![Strings](https://place-hold.it/175x50/16a085/ffffff&text=Strings&bold&fontsize=24)
- Raw strings (multiline strings)
```java
""" some raw string """
```
- ##### Methods
	- Trim margins between 1st char and | symbol (use an arg for other symbols)
	```java
	str.trimMargin()
	```
	- Iterate on each chars in a string
	```java
	for ( char in str ) { }
	```
	- Compare 2 strings
	```java
	str.contentEquals("some string")
	```
	- Check if a string contains another string, the second argument is a boolean, set it to true to ignore the case
	```java
	str.contains("...", bool)
	```
	- Change the string case
  ```java
	str.toUpperCase()
	str.toLowerCase()
	```
	- Convert other types to String
	```java
	~.toString()
	```
	- Return the chars between start and end indexes
	```java
	str.subSequence(startIndex, endIndex)
	```
- ![#27ae60](https://placehold.it/10/27ae60/000000?text=+) Templating *(can use methods on the vars, but only inside { })*
	```java
"$var1 some text, $var2 some other text, text $var3...."
"text ${var1.length}...."
```

![Functions](https://place-hold.it/175x50/8e44ad/ffffff&text=Functions&bold&fontsize=24)
- Basic function invocation
```java
functionName()
```
- Basic function declaration
```java
fun functionName() { ..... }
```
- ![#f39c12](https://placehold.it/10/f39c12/000000?text=+) Function declaration with multiple args and a returning type
```java
fun functionName( arg1: Int, arg2: Int) : Int { ...... }
```
- ![#f39c12](https://placehold.it/10/f39c12/000000?text=+) Function declaration with default value if no arg provided
```java
fun functionName( arg: String = "default value" ) { .... }
```

![Switch](https://place-hold.it/175x50/34495e/ffffff&text=Switch&bold&fontsize=24)
```java
when( x ) {
	1 -> // do something
	2 -> // do something
	else -> // do something
}
```

![Collections](https://place-hold.it/175x50/f39c12/ffffff&text=Collections&bold&fontsize=24)
- #### Immutable Lists
  ```java
	 val someList = listOf("some", "text", "list", ...)  
	 ```
  - ###### Methods
    - Sort array
		```java
		someList.sorted()
		```
    - Return the first item
		```java
		list.first()
		``
    - Return the last item
		```java
		list.last()
		```
    - Check if the list contains arg
		```java
		list.contains(arg)
		```
- #### Mutable Lists
  ```java
	val newList = arrayListOf("item1", "item2", "item3", ...)
	```
  - ###### Methods
    - Return the list size
		```java
		newList.size
		```
    - Add new item at the end of the list
		```java
		newList.add("item4")
		```
    - Add new item at the specified index
		```java
		newList.add(0, "item0")
		```
    - Return the index of the specified item
		```java
		newList.indexOf("item1")
		```
    - Remove the specified item from the list (can also be remove by its index)
		```java
		newList.remove("item4")
		```

![Maps](https://place-hold.it/175x50/d35400/ffffff&text=Maps&bold&fontsize=24)
- #### Immutable Maps
	```java
	val someMap = mapOf("key1" to "value1", "key2" to "value2", ...)
	```
	- ###### Methods
		- Return the value paired to a key
		```java
		someMap["key1"]
		someMap.get("key1")
		```
		- ![#27ae60](https://placehold.it/10/27ae60/000000?text=+) Return the value paired to a key, if there is none return a default message
		```java
		someMap.getOrDefault("someKey", "Custom default message")
		```
		- Return the list of keys
		```java
		someMap.keys
		```
		- Return the list of values
		```java
		someMap.values
		```
- #### Mutable Maps
	```java
	val newMap = hashMapOf("key1" to "value1", "key2" to "value2", ...)
	```
	- ###### Methods
		- Change value paired to a key
		```java
		newMap["key1"] = "newValue1"
		```
		- Add a new key/value pair
		```java
		newMap.put("key3", "value3")
		```
		- Remove a key/value pair
		```java
		newMap.remove("key2")
		```
		- Remove all key/value pairs
		```java
		newMap.clear
		```
		- Check if the Map is empty, return a boolean
		```java
		newMap.isEmpty
		```

![Loops](https://place-hold.it/175x50/27ae60/ffffff&text=Loops&bold&fontsize=24)
- ![#f39c12](https://placehold.it/10/f39c12/000000?text=+) Iterate through a List
	```java
	val itemList = arrayListOf("item1", "item2", "item3", ...)
	for ( item in itemList ) {
		//do something
	}
	```
- ![#f39c12](https://placehold.it/10/f39c12/000000?text=+) Iterate through a Map
	```java
	val otherList = hashMapOf("key1" to "value1", "key2" to "value2", ...)
	for ( (key, value) in otherList ) {
		//do something
	}
	```

![Nullability](https://place-hold.it/175x50/8e44ad/ffffff&text=Nullability&bold&fontsize=24)
- Declare a String variable that is nullable
```java
var nullableVar: String? = "some text"
```
- Null check
```java
var length = 0
if ( nullableVar != null ) {
	length = nullableVar.length
} else {
	length = -1
}
```
- ![#f39c12](https://placehold.it/10/f39c12/000000?text=+) More concise null check, declare and gives a value in a single line
```java
val l = if( nullableVar != null ) nullableVar.length else -1
```
- Safe Call Operator: way to work on a nullable variable directly, will return the length if it's not null, else will return null
```java
nullableVar?.length
```
- ![#f39c12](https://placehold.it/10/f39c12/000000?text=+) Elvis Operator: if there is a null value return -1 (can set a default value if null)
```java
var len = nullableVar?.length ? : -1
```
- Ignore the null check: only use when 100% sure the variable is not null
```java
nullableVar!!.length
```

![Classes](https://place-hold.it/175x50/2980b9/ffffff&text=Classes&bold&fontsize=24)
- Long Constructor declaration
```java
class Car constructor(make: String, model: String) {
	val make = make
	val model =model
}
```
- Class instance creation
```java
val car = Car("Toyota", "Prius")
```
- ![#e74c3c](https://placehold.it/10/e74c3c/000000?text=+) Short Constructor declaration (declare var in arg)
```java
class Car(val make: String, val model: String) {}
```
	- No getters / setters, val will set getter, var will set getter/setter automatically in the background


- ![#e74c3c](https://placehold.it/10/e74c3c/000000?text=+) Inheritance
```java
open class Vehicle(val make: String, val model: String){}
class Car(make: String, model: String, color: String) : Vehicle(make, model) {}<
```
	- need the parent class to be open as in Kotlin all classes are final by default
	- need the args inside the child class so it can pass it to the parent class
	- need to open methods inside the parent class to be able to Override them in the child class

![Lambdas](https://place-hold.it/175x50/c0392b/ffffff&text=Lambdas&bold&fontsize=24)
- ![#e74c3c](https://placehold.it/10/e74c3c/000000?text=+) Lambda expression
```java
val printMsg = { message: String -> println(message) }
```
- Always surrounded by {  }
- It's a function litteral, a function not declared but passed immediatly
- Parameters are on the left, the body of the function is on the right of the arrow ( Similar to ES6 arrow function (arg) => {body} )
- ![#e74c3c](https://placehold.it/10/e74c3c/000000?text=+) Other lambda expressions
```java
val sumA = { x: Int, y: Int -> x + y }
val sumB: (Int, Int) -> Int = {x, y -> x + y}
```
- ![#e74c3c](https://placehold.it/10/e74c3c/000000?text=+) Units (similar to Java's Void)
```java
fun downloadData(url: String, completion: () -> Unit) {
	//Sent download request, got data back, no error case
	completion()
}
// Call download function
downloadData("randomURL.com", {
	println("the code here will only run after completion()")
})
```

(Feels a lot like callbacks and anonymous functions in JS )
