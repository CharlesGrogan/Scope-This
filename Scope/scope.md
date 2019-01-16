## JavaScript Scope

Scope determines the accessibility (visibility) of variables.

JavaScript Function Scope
In JavaScript there are two types of scope:

* Local scope
* Global scope

JavaScript has function scope: Each function creates a new scope.

Scope determines the accessibility (visibility) of these variables.

Variables defined inside a function are not accessible (visible) from outside the function.

Local JavaScript Variables
Variables declared within a JavaScript function, become LOCAL to the function.

Local variables have Function scope: They can only be accessed from within the function.
-------------------------------------------------------
<html>
<body>

<h2>JavaScript Scope</h2>

<p>Outside myFunction() carName is undefined.</p>

<p id="demo1"></p>

<p id="demo2"></p>

<script>
myFunction();

function myFunction() {
  var carName = "Volvo";
  document.getElementById("demo1").innerHTML = typeof carName + " " + carName;
} // return string Volvo

document.getElementById("demo2").innerHTML = typeof carName; // return undefined

</script>
</body>
</html>
-------------------------------------------------------
Since local variables are only recognized inside their functions, variables with the same name can be used in different functions.

Local variables are created when a function starts, and deleted when the function is completed.

## Global JavaScript Variables
A variable declared outside a function, becomes GLOBAL.

A global variable has global scope: All scripts and functions on a web page can access it. 
-------------------------------------------------------
<html>
<body>

<h2>JavaScript Scope</h2>

<p>A GLOBAL variable can be accessed from any script or function.</p>

<p id="demo"></p>

<script>
var carName = "Volvo";
myFunction();

function myFunction() {
  document.getElementById("demo").innerHTML = "I can display " + carName;
} // return I can display Volvo

</script>
</body>
</html>
-------------------------------------------------------

## JavaScript Variables
In JavaScript, objects and functions are also variables.

Scope determines the accessibility of variables, objects, and functions from different parts of the code.

## Automatically Global
If you assign a value to a variable that has not been declared, it will automatically become a GLOBAL variable.

This code example will declare a global variable carName, even if the value is assigned inside a function.
-------------------------------------------------------
<html>
<body>

<p>If you assign a value to a variable that has not been declared, it will automatically become a GLOBAL variable:</p>

<p id="demo"></p>

<script>
myFunction();
// code here can use carName as a global variable
document.getElementById("demo").innerHTML = "I can display " + carName;
function myFunction() {
  carName = "Volvo";
}
// return I can display Volvo

</script>
</body>
</html>
-------------------------------------------------------

##Strict Mode
All modern browsers support running JavaScript in "Strict Mode".

You will learn more about how to use strict mode in a later chapter of this tutorial.

Global variables are not created automatically in "Strict Mode".

## Global Variables in HTML
With JavaScript, the global scope is the complete JavaScript environment.

In HTML, the global scope is the window object. All global variables belong to the window object.
-------------------------------------------------------
<html>
<body>

<h2>JavaScript Scope</h2>

<p>In HTML, global variables defined with <b>var</b>, will become window variables.</p>

<p id="demo"></p>

<script>
var carName = "Volvo";

// code here can use window.carName
document.getElementById("demo").innerHTML = "I can display " + window.carName;
// return I can display Volvo

</script>
</body>
</html>
-------------------------------------------------------

## Warning
Do NOT create global variables unless you intend to.

Your global variables (or functions) can overwrite window variables (or functions).
Any function, including the window object, can overwrite your global variables and functions.

## The Lifetime of JavaScript Variables
The lifetime of a JavaScript variable starts when it is declared.

Local variables are deleted when the function is completed.

In a web browser, global variables are deleted when you close the browser window (or tab), but remain available to new pages loaded into the same window.

## Function Arguments
Function arguments (parameters) work as local variables inside functions.

## Resources
http://www.digital-web.com/articles/scope_in_javascript/

http://web.archive.org/web/20110725013125/http://www.digital-web.com/articles/scope_in_javascript/

https://scotch.io/tutorials/understanding-scope-in-javascript