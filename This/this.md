## What is 'This'?

The JavaScript 'this' keyword refers to the object it belongs to.

It has different values depending on where it is used:

* In a method, this refers to the owner object.

* Alone, this refers to the global object.

* In a function, this refers to the global object.

* In a function, in strict mode, this is undefined.

* In an event, this refers to the element that received the event.

* Methods like call(), and apply() can refer this to any object.

## 'this' in a Method
In an object method, this refers to the "owner" of the method.

In the example on the top of this page, this refers to the person object.

The person object is the owner of the fullName method.

## Example
<script>
// Create an object:
var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

// Display data from the object:
document.getElementById("demo").innerHTML = person.fullName(); // Return John Doe
</script>
-------------------------------------------------------------------------------------------------------
## this Alone
When used alone, the owner is the Global object, so this refers to the Global object.

In a browser window the Global object is [object Window]:

<script>
"use strict"
var x = this;
document.getElementById("demo").innerHTML = x;

// x returns [object Window]
</script>

------------------------------------------------------------------------------------------------------

## this in a Function (Default)
In a JavaScript function, the owner of the function is the default binding for this.

So, in a function, this refers to the Global object [object Window].

<html>
<body>

<h2>The JavaScript <b>this</b> Keyword</h2>

<p>In this example, <b>this</b> represents the object that "owns" myFunction:</p>

<p id="demo"></p>

<script>
document.getElementById("demo").innerHTML = myFunction();
function myFunction() {
  return this;
}

// this returns [object Window]
</script>

</body>
</html>
-------------------------------------------------------------------------------------------------------

## this in a Function (Strict)
JavaScript strict mode does not allow default binding.

So, when used in a function, in strict mode, this is undefined.

<html>
<body>

<h2>The JavaScript <b>this</b> Keyword</h2>

<p>In a function, by default, <b>this</b> refers to the Global object.</p>
<p>In strict mode, <b>this</b> is <b>undefined</b>, because strict mode does not allow default binding:</p>

<p id="demo"></p>

<script>
"use strict";
document.getElementById("demo").innerHTML = myFunction();
function myFunction() {
  return this;
}

// this returns undefined
</script>

</body>
</html>
-------------------------------------------------------------------------------------------------------

## this in Event Handlers
In HTML event handlers, this refers to the HTML element that received the event:

<html>
<body>

<h2>The JavaScript <b>this</b> Keyword</h2>

<button onclick="this.style.display='none'">Click to Remove Me!</button>

<!-- the button will disappear in this example -->
</body>
</html>
-------------------------------------------------------------------------------------------------------

## Object Method Binding
In these examples, this is the person object (The person object is the "owner" of the function):

<html>
<body>

<h2>The JavaScript <b>this</b> Keyword</h2>

<p>In this example, <b>this</b> represents the person object that "owns" the fullName method.</p>

<p id="demo"></p>

<script>
// Create an object:
var person = {
  firstName  : "John",
  lastName   : "Doe",
  id     : 5566,
  myFunction : function() {
    return this;
  }
};

// Display data from the object:
document.getElementById("demo").innerHTML = person.myFunction();

// person.myFunction() returns [object Object]

</script>

</body>
</html>
-------------------------------------------------------------------------------------------------------

<html>
<body>

<h2>The JavaScript <b>this</b> Keyword</h2>

<p>In this example, <b>this</b> represents the <b>person</b> object.</p>
<p>Because the person object "owns" the fullName method.</p>

<p id="demo"></p>

<script>
// Create an object:
var person = {
  firstName: "John",
  lastName : "Doe",
  id     : 5566,
  fullName : function() {
    return this.firstName + " " + this.lastName;
  }
};

// Display data from the object:
document.getElementById("demo").innerHTML = person.fullName();

// person.fullName() returns John Doe
</script>

</body>
</html>
-------------------------------------------------------------------------------------------------------

## Explicit Function Binding
The call() and apply() methods are predefined JavaScript methods.

They can both be used to call an object method with another object as argument.

You can read more about call() and apply() later in this tutorial.

In the example below, when calling person1.fullName with person2 as argument, this will refer to person2, even if it is a method of person1:

<html>
<body>

<h2>The JavaScript this Keyword</h2>
<p>In this example <strong>this</strong> refers to person2, even if it is a method of person1:</p>

<p id="demo"></p>

<script>
var person1 = {
  fullName: function() {
    return this.firstName + " " + this.lastName;
  }
}
var person2 = {
  firstName:"John",
  lastName: "Doe",
}
var x = person1.fullName.call(person2); 
document.getElementById("demo").innerHTML = x; 

// returns John Doe

</script>

</body>
</html>
-------------------------------------------------------------------------------------------------------

## Resources
https://javascriptissexy.com/understand-javascripts-this-with-clarity-and-master-it/

https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this

https://stackoverflow.com/questions/3127429/how-does-the-this-keyword-work