# AMA Technical Paper

## Difference between "==" and "===" in JS :

&nbsp;

* ***What is "==" operator :***

	* The ‘==’ operator tests for abstract equality i.e. it does the necessary type conversions before doing the equality comparison.

	&nbsp;
	*	>&nbsp;*Example:*

		```{html}
		<script>
			document.write( 2 == "2");
			document.write( <br>);
			document.write( 0 === false);
		</script>
		```

	*	>&nbsp;*Output:*

		```{text}
		true
		true
		```

	&nbsp;
* ***What is "===" operator :***

	* The ‘===’ operator tests for strict equality i.e it will not do the type conversion hence if the two values are not of the same type, when compared, it will return false.

	&nbsp;
	*	>&nbsp;*Example:*

		```{html}
		<script>
			document.write( 2 === "2");
			document.write( <br>);
			document.write( 0 === false);
		</script>
		```

	*	>&nbsp;*Output:*

		```{text}
		false
		false
		```

&nbsp;

## Node Package Manager or NPM :

 Node Package Manager (NPM) provides two main functionalities −

* Online repositories for node.js packages/modules which are searchable on search.nodejs.org

* Command line utility to install Node.js packages, do version management and dependency management of Node.js packages.

NPM comes bundled with Node.js installables after v0.6.3 version.

&nbsp;
**Installing Modules using NPM**
<br>&nbsp; In Linux :

```{linux}
	npm install <Module Name>;
```

**Uninstalling Modules using NPM**
<br>&nbsp; In Linux :

```{linux}
	npm uninstall <Module Name>;
```

**Show Every Package**
<br>&nbsp; In Linux :

```{linux}
	npm ls;
```

**Updating Modules using NPM**
<br>&nbsp; In Linux :

```{linux}
	npm update <Module Name>;
```

&nbsp;

## Types of variables in Ruby :

&nbsp;

* **Global Variables :**

	Global variables begin with **$**. *Uninitialized global variables have the value **nil*** and produce warnings with the -w option.

	Assignment to global variables alters the global status. It is not recommended to use global variables. They make programs cryptic.

	&nbsp;
	> *Example :*

	```{Ruby}
		$global_variable = 10
		class Class1
		def print_global
			puts "Global variable in Class1 is #$global_variable"
		end
		end
		class Class2
		def print_global
			puts "Global variable in Class2 is #$global_variable"
		end
		end

		class1obj = Class1.new
		class1obj.print_global
		class2obj = Class2.new
		class2obj.print_global
	```

	&nbsp;
	> *Output :*

	```{text}
		Global variable in Class1 is 10
		Global variable in Class2 is 10
	```

	&nbsp;

* **Instance Variables :**

	An instance variable has a name beginning with **@** , and its *scope is confined to whatever object self refers to*.

	Instance variables of ruby *do not need declaration*. This implies a flexible structure of objects. 

	In fact, each instance variable is *dynamically appended* to an object when it is first referenced.

	&nbsp;
	>*Example :*

	```{ruby}
	class InstTest
       def set_foo(n)
         @foo = n
       end
       def set_bar(n)
         @bar = n
       end
    end
	i = InstTest.new

	i.set_foo(2)
	i.set_bar(4)
	```

	> *Output :*

	```{text}
	2
	4
	```

*	**Class Variables :**

	Class variables begin with **@@** and *must be initialized* before they can be used in method definitions.

	Referencing an uninitialized class variable produces an error. Class variables are *shared among descendants of the class or module* in which the class variables are defined.

	&nbsp;
	>*Example :*

	```{ruby}
	class Customer
		@@no_of_customers = 0
		def initialize(id, name, addr)
			@cust_id = id
			@cust_name = name
			@cust_addr = addr
		end
		def display_details()
			puts "Customer id #@cust_id"
			puts "Customer name #@cust_name"
			puts "Customer address #@cust_addr"
		end
		def total_no_of_customers()
			@@no_of_customers += 1
			puts "Total number of customers: #@@no_of_customers"
		end
		end


	cust1 = Customer.new("1", "John", "Wisdom Apartments, Ludhiya")
	cust2 = Customer.new("2", "Poul", "New Empire road, Khandala")


	cust1.total_no_of_customers()
	cust2.total_no_of_customers()
	```

	> *Output :*

	```{text}
	Total number of customers: 1
	Total number of customers: 2
	```

&nbsp;

*	**Local Variables :**

	Local variables begin with a **lowercase letter or _**. The *scope* of a local variable ranges *from class, module, def, or do to the corresponding end* or from a block's opening brace to its close brace {}.

	*Assignment to uninitialized local variables also serves as variable declaration*. The variables start to exist until the end of the current scope is reached.

	&nbsp;
	>*Example :*

	```{ruby}
	class Example
		VAR1 = 100
		VAR2 = 200
		def show
			puts "Value of first Constant is #{VAR1}"
			puts "Value of second Constant is #{VAR2}"
		end
		end

	object = Example.new()
	object.show
	```

	> *Output :*

	```{text}
	Value of first Constant is 100
	Value of second Constant is 200	
	```

&nbsp;

## Hoisting in JS :

A strict definition of hoisting suggests that variable and function declarations are physically moved to the top of your code, but this is not in fact what happens. 

Instead, the variable and function declarations are put into memory during the compile phase, but stay exactly where you typed them in your code.

&nbsp;
>*Example :*

```{javaScript}
catName("Chloe");

function catName(name) {
  console.log("My cat's name is " + name);
}
```

The above mentiones function will work without even though we call the function first before the function is written.

Hoisting doesn't work for the variables who are initialized by let or const.

&nbsp;

## let, var, const, global variables in JS :

&nbsp;

* **var :**

	The scope of a variable defined with the keyword “var” is limited to the “function” within which it is defined. If it is defined outside any function, the scope of the variable is global.
	var is “function scoped”.

	> *Declaration :*

	```{javascript}
		var a = <value>;
	```

* **let :**

	The scope of a variable defined with the keyword “let” or “const” is limited to the “block” defined by curly braces i.e. {} .
	“let” and “const” are“block scoped”.

	> *Declaration :*

	```{javascript}
		let a = <value>;
	```

* **const :**

	The scope of a variable defined with the keyword “const” is limited to the block defined by curly braces. However if a variable is defined with keyword const, it cannot be reassigned.

	“const” cannot be re-assigned to a new value. However it CAN be mutated.

	> *Declaration :*

	```{javascript}
		const a = <value>;
	```

* **Global Variable :**

	A variable declared outside a function, becomes GLOBAL.

	A global variable has global scope: All scripts and functions on a web page can access it. 

	> *Declaration :*

	```{javascript}
		 a = <value>;
		 function myFunction(){
			 #Something in this function.
		 }
	```

&nbsp;

## Query Selector in JS :

The querySelector function takes an argument, and this argument is a string that represents the CSS selector for the element you wish to find.

What gets returned by querySelector is the first element it finds - even if other elements exist that could get targeted by the selector

>*Example :*

```{javascript}
var element = document.querySelector("< CSS selector >");
```

&nbsp;

## VARCHAR and TEXT in SQL :

* **TEXT :**

	* Fixed max size of 65535 characters (you cannot limit the max size).

	* Takes 2 + c bytes of disk space, where c is the length of the stored string.

	* Cannot be (fully) part of an index. One would need to specify a prefix length.

* **VARCHAR(M) :**

	* Variable max size of M characters.

	* M needs to be between 1 and 65535.

	* Takes 1 + c bytes (for M ≤ 255) or 2 + c (for 256 ≤ M ≤ 65535) bytes of disk space where c is the length of the stored string.

	* Can be part of an index

&nbsp;

## Media Queries :

Media queries are useful when you want to modify your site or app depending on a device's general type (such as print vs. screen) or specific characteristics and parameters (such as screen resolution or browser viewport width).

Media queries are used for the following:

* To conditionally apply styles with the CSS @media and @import at-rules.
* To target specific media for the style, link, source, and other HTML elements with the media= attribute.
* To test and monitor media states using the Window.matchMedia() and MediaQueryList.addListener() JavaScript methods.

A media query is composed of an optional media type and any number of media feature expressions.

A media query computes to true when the media type (if specified) matches the device on which a document is being displayed and all media feature expressions compute as true. Queries involving unknown media types are always false.

**Media Types**

* **all :**

	Suitable for all devices.

* **print :**

	Intended for paged material and documents viewed on a screen in print preview mode. 

* **screen :**

	Intended primarily for screens.

* **speech :**

	Intended for speech synthesizers.

&nbsp;

## Font Sizes in CSS :

&nbsp;

* **Absolute Units :**

	* PX:
		
		Pixels (px) are considered absolute units, although they are relative to the DPI and resolution of the viewing device.

&nbsp;

* **Flexible Units :**

	* EM: 
		
		* Relative to the parent element.

		* It is based on the font size of the parent element. If a parent element has a different size than the root element, the EM calculation will be based off of the parent element, and not the root element.

	* REM:
		
		* Relative to the root element (HTML tag).

		* Every child element that uses REM will then use the HTML root size as its calculation point, regardless of whether or not a parent element has any different sizes specified.

	* %:
		* Relative to the parent element.
		
		* It reflects a percentage of the parent element’s size, regardless of the viewport’s size.

	* VW:
		
		* Relative to the viewport’s width.
		
		* VW stands for “viewport width”, which is the viewable screen’s width. 100VW would represent 100% of the viewport’s width, or the full width of the screen.

	* VH:

		* Relative to the viewport’s height.
		
		* VH stands for “viewport height”, which is the viewable screen’s height. 100VH would represent 100% of the viewport’s height, or the full height of the screen.
