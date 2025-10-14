A programming paradigm is a fundamental approach or style for conceptualizing and structuring computer programs, influencing how code is written, organized, and executed.

There are mainly 4 types of Programming Paradigms:-

##### 1. Monolithic Programming
Write the whole program as one continuous block of code. Example: Basic and Assembly
```
	...
	...
	...
```

##### 2. Procedural Programming
Break the program into **procedures (functions)**. Example: C
```
function1()
	...
	...
	
function2()
	...
	...
	
main()
	fuction1()
	function2()
```
##### 3. Modular Programming
Extension of procedural. Program divided into modules (separate files/components) with interfaces.
```
Structure info
	data 1
	data 2
	
function1()
	...
	...
	
function2()
	...
	...
	
main()
	Struct Info()
	fuction1()
	function2()
```

##### 4. Object Oriented Programming
Organize code into **objects** (data + methods). Example: Java, C++, Python, etc.
**Features:**
- **Encapsulation:** Hide data inside objects.
- **Inheritance:** Reuse code from parent classes.
- **Polymorphism:** Same interface, different behavior.
- **Abstraction:** Hide implementation details.
```
class
	Structure info
		data 1
		data 2
		
	function1()
		...
		...
		
	function2()
		...
		...
		
main()
	Struct Info()
	fuction1()
	function2()
```

##### 5. Aspect-Oriented Programming
In **OOPs**, you separate code into classes and objects.  
But some concerns (like **logging, security, transactions, error handling**) appear **everywhere** — these are called **cross-cutting concerns**.
Instead of repeating the same code in every function/class, AOP separates them into **aspects** and automatically applies them wherever needed.
In short: **AOP = separation of concerns**


