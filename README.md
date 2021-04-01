
# Explain how can you submit a form using JavaScript?
To submit a form using JavaScript use document.form[0].submit();
```js
document.form[0].submit();
```

# What are JavaScript Data Types?

Following are the JavaScript Data types:
<ul>
  <li>Number</li>
  <li>String</li>
  <li>Boolean</li>
  <li>Object</li>
  <li>Undefined</li>
</ul>

# Closures
A closure is the combination of a function bundled together (enclosed) with references to its surrounding state (the lexical environment). In other words, a closure gives you access to an outer function’s scope from an inner function. In JavaScript, closures are created every time a function is created, at function creation time

A closure is a feature in JavaScript where an inner function has access to the outer (enclosing) function’s variables — a scope chain.
The closure has three scope chains:
<ul>
<li>it has access to its own scope — variables defined between its curly brackets</li>
<li>it has access to the outer function’s variables</li>
<li>it has access to the global variables</li>
</ul>

```js
function outer() {
   var b = 10;
   function inner() {
        
         var a = 20; 
         console.log(a+b);
    }
   return inner;
}

```

# Describe the properties of an anonymous function in JavaScript?
A function that is declared without any named identifier is known as an anonymous function. In general, an anonymous function is inaccessible after its declaration.

Anonymous function declaration -
```js
var anon = function() {
	alert('I am anonymous');
};
anon();
```


# What are global variables? How are these variable declared and what are the problems associated with using them?

Global variables are those that are available throughout the length of the code, that is, these have no scope. The var keyword is used to declare a local variable or object. If the var keyword is omitted, a global variable is declared.

Example:

// Declare a global globalVariable = "Test";

The problems that are faced by using global variables are the clash of variable names of local and global scope. Also, it is difficult to debug and test the code that relies on global variables.

# What is 'this' keyword in JavaScript?
'This' keyword refers to the object from where it was called.


# call(), apply() and bind() Methods in JavaScript.
Working with JavaScript “this” keyword can be tricky. Not knowing the background rules may end up with the famous “it works, but I don’t know why” or worse: “it doesn’t work and I don’t know why”. It’s good to know the theory before putting things into practice. Call(), Apply() and Bind() methods can come in handy when setting the “this” value.

<h6>Basic rules worth remembering:</h6>
1) “this” always refers to an object.
2> “this” refers to an object which calls the function it contains.
3) In the global context “this” refers to either window object or is undefined if the ‘strict mode’ is used.
```js
var car = { 
    registrationNumber: "GA12345",
    brand: "Toyota",

    displayDetails: function(){
        console.log(this.registrationNumber + " " + this.brand);
    }
}
```
The above will work perfectly fine as long as we use it this way:
```js
car.displayDetails(); // GA12345 Toyota
```
But what if we want to borrow a method?
```js
var myCarDetails =  car.displayDetails;
myCarDetails();
```
Well, this won’t work as the “this” will be now assigned to the global context which doesn’t have neither the registrationNumber nor the brand property.

The bind() Method
For such cases we can use the ECMAScript 5 bind() method of the Function.prototype property. This means bind() can be used by every single function.
```js
var myCarDetails = car.displayDetails.bind(car); 
myCarDetails(); // GA12345 Toyota
```
The bind() method creates a new function where “this” refers to the parameter in the parenthesis in the above case “car”. This way the bind() method enables calling a function with a specified “this” value.

What if we would like to pass a parameter to the displayDetails function? We can use the bind method again. The following argument of the bind() method will provide an argument to the function bind() is called on.

Let me rewrite the car object:
```js
var car = { 
    registrationNumber: "GA12345",
    brand: "Toyota",

    displayDetails: function(ownerName){
        console.log(ownerName + ", this is your car: " + this.registrationNumber + " " + this.brand);
    }
}
```
Example of passing arguments with bind():

var myCarDetails = car.displayDetails.bind(car, "Vivian"); // Vivian, this is your car: GA12345 Toyota
call() and apply() methods
Similar but slightly different usage provide the call() and apply() methods which also belong to the Function.prototype property.

This time there is a car object without the displayDetails function, which is located in the global context.
```js
var car = { 
    registrationNumber: "GA12345",
    brand: "Toyota"
}

function displayDetails(ownerName) {
    console.log(ownerName + ", this is your car: " + this.registrationNumber + " " + this.brand);
}
```
We can use the apply() function:
```js
displayDetails.apply(car, ["Vivian"]); // Vivian, this is your car: GA12345 Toyota
Or

displayDetails.call(car, "Vivian"); // Vivian, this is your car: GA12345 Toyota
```
<b>Note:</b> that when using the apply() function the parameter must be placed in an array. Call() accepts both an array of parameters and a parameter itself. Both are great tools for borrowing functions in JavaScript.

bind(), call() and apply() functions can make your life easier when you need to set the value of ‘this’. Hope the post was helpful.

# Learning Exercise !!!
```js
var func = function() {
    console.log(this)
}.bind(1);

func();
```

```js
var func = function() {
    console.log(this)
}.bind(1);
 
 var obj = {
    callFun : func
 }
obj.callFun.func();
```

```js
function checkFun(a, b, c){
    console.log(this);
    console.log(a);
    console.log(b);
    console.log(c);
}
checkFun.call(1,2,3,4);
```

```js
function checkFun(a, b, c){
    console.log(this);
    console.log(a);
    console.log(b);
    console.log(c);
}
checkFun.apply(1,[2,3,4]);
```

```js
function sumOfNumbers() {
    var total = 0;
    for(var i = 0; i < arguments.length; i++){
        total += arguments[i];
    }
    return total;
}
var sum = sumOfNumbers(1,2,3);
console.log(sum);
```

```js
var updateZipCode = function (newZip, country) {
    console.log(newZip + ' ' + country);
};
var zipCode = {
    zip: '11787'
};
updateZipCode.call(zipCode, '11888', 'us');
```

```js
var updateZipCode = function (newZip, country) {
    console.log(newZip + ' ' + country);
};
var zipCode = {
    zip: '11787'
};
updateZipCode.apply(zipCode, ['11888', 'us']);
```


# Does JavaScript support automatic type conversion?
Yes JavaScript does support automatic type conversion, it is the common way of type conversion used by JavaScript developers

# How can the style/class of an element be changed?

It can be done in the following way:

document.getElementById("myText").style.fontSize = "20";
or
document.getElementById("myText").className = "anyclass";

# Explain how to detect the operating system on the client machine?

In order to detect the operating system on the client machine, the navigator.platform string (property) should be used.

# What is the function of delete operator?

The delete keyword is used to delete the property as well as its value.

Example
```js
var student= {age:20, batch:"ABC"};
delete student.age;
```
# What is the data type of variables of in JavaScript?

All variables in the JavaScript are object data types.

# What is the difference between an alert box and a confirmation box?

An alert box displays only one button which is the OK button.

But a Confirmation box displays two buttons namely OK and cancel.

# What are escape characters?

Escape characters (Backslash) is used when working with special characters like single quotes, double quotes, apostrophes and ampersands. Place backslash before the characters to make it display.

Example:
```js
document.write "I m a "good" boy"
document.write "I m a \"good\" boy"
```

# What are JavaScript Cookies?

Cookies are the small test files stored in a computer and it gets created when the user visits the websites to store information that they need. Example could be User Name details and shopping cart information from the previous visits.

# Whether JavaScript has concept level scope?

No. JavaScript does not have concept level scope. The variable declared inside the function has scope inside the function.

# What is break and continue statements?

Break statement exits from the current loop.

Continue statement continues with next statement of the loop.

# How generic objects can be created?

Generic objects can be created as:
```js
var I = new object();
```
# What is the use of type of operator?
'Typeof' is an operator which is used to return a string description of the type of a variable.

# Which keywords are used to handle exceptions?
Try… Catch---finally is used to handle exceptions in the JavaScript
```js
Try{
	Code
}
Catch(exp){
	Code to throw an exception
}
Finally{
	Code runs either it finishes successfully or after catch
}
```
# Which keyword is used to print the text in the screen?
document.write("Welcome") is used to print the text – Welcome in the screen.

# What is the use of blur function?
Blur function is used to remove the focus from the specified object.

# What is variable typing?
Variable typing is used to assign a number to a variable and then assign string to the same variable. Example is as follows:
```js
i= 8;
i="john";
```

# What are the different types of errors in JavaScript?
There are three types of errors:
<ul>
<li>Load time errors: Errors which come up when loading a web page like improper syntax errors are known as Load time errors and it generates the errors dynamically.</li>
<li>Run time errors: Errors that come due to misuse of the command inside the HTML language.</li>
<li>Logical Errors: These are the errors that occur due to the bad logic performed on a function which is having different operation.</li>
<ul>
  
# What is the use of Push method in JavaScript?
The push method is used to add or append one or more elements to the end of an Array. Using this method, we can append multiple elements by passing multiple arguments

# What is unshift method in JavaScript?
Unshift method is like push method which works at the beginning of the array. This method is used to prepend one or more elements to the beginning of the array.

# What is the way to get the status of a CheckBox?
The status can be acquired as follows -

alert(document.getElementById('checkbox1').checked);

If the CheckBox will be checked, this alert will return TRUE.

# Explain window.onload and onDocumentReady?
The onload function is not run until all the information on the page is loaded. This leads to a substantial delay before any code is executed.

onDocumentReady loads the code just after the DOM is loaded. This allows early manipulation of the code.



# Explain the working of timers in JavaScript? Also elucidate the drawbacks of using the timer, if any?
Timers are used to execute a piece of code at a set time or also to repeat the code in a given interval of time. This is done by using the functions <b>setTimeout</b>, <b>setInterval</b> and <b>clearInterval</b>.

The <b>setTimeout(function, delay)</b> function is used to start a timer that calls a particular function after the mentioned delay. The <b>setInterval(function, delay)</b> function is used to repeatedly execute the given function in the mentioned delay and only halts when cancelled. The <b>clearInterval(id)</b> function instructs the timer to stop.

Timers are operated within a single thread, and thus events might queue up, waiting to be executed.

# What are undeclared and undefined variables?

Undeclared variables are those that do not exist in a program and are not declared. If the program tries to read the value of an undeclared variable, then a runtime error is encountered.

Undefined variables are those that are declared in the program but have not been given any value. If the program tries to read the value of an undefined variable, an undefined value is returned.

# What are the JavaScript data types?
There are two types of data types in JavaScript:

<p> 1. Primitive Data Types - The primitive data types are as follows:
  <table class="alt">
    <tbody><tr><th>Data Type</th><th>Description</th></tr>
    <tr><td>String</td><td>represents a sequence of characters, e.g., "hello"</td></tr>
    <tr><td>Number</td><td>represents numeric values, e.g., 100</td></tr>
    <tr><td>Boolean</td><td>represents boolean value either false or true</td></tr>
    <tr><td>Undefined</td><td>represents an undefined value</td></tr>
    <tr><td>Null</td><td>represents null, i.e., no value at all</td></tr>
    </tbody>
   </table>
  </p>
<p> 2. Non-primitive Data Types - The non-primitive data types are as follows:
<table class="alt">
  <tbody><tr><th>Data Type</th><th>Description</th></tr>
  <tr><td>Object</td><td>represents an instance through which we can access members</td></tr>
  <tr><td>Array</td><td>represents a group of similar values</td></tr>
  <tr><td>RegExp</td><td>represents regular expression</td></tr>
  </tbody>
</table>
</p>

# How to use external JavaScript file?
```js 
  <script type="text/javascript" src="message.js"></script>  
 ```
 
# Is JavaScript case sensitive language?
 Yes, JavaScript is a case sensitive language.
 
# What is DOM? What is the use of document object?
 DOM stands for Document Object Model. A document object represents the HTML document. It can be used to access and change the content of HTML.
 
 # What is the use of window object?
 The window object is created automatically by the browser that represents a window of a browser. It is not an object of JavaScript. It is a browser object.

The window object is used to display the popup dialog box. Let's see with description.
Method	Description
<table>
  <tbody><tr><th>Method</th><th>Description</th></tr>
  <tr><td>alert()</td><td>displays the alert box containing the message with ok button.</td></tr>
  <tr><td>confirm()</td><td>displays the confirm dialog box containing the message with ok and cancel button.</td></tr>
  <tr><td>prompt()</td><td>displays a dialog box to get input from the user.</td></tr>
  <tr><td>open()</td><td>opens the new window.</td></tr>
  <tr><td>close()</td><td>closes the current window.</td></tr>
  <tr><td>setTimeout()</td><td>performs the action after specified time like calling function, evaluating expressions.</td></tr>
  </tbody>
</table>

# How to write a comment in JavaScript?
There are two types of comments in JavaScript.

1) Single Line Comment: It is represented by // (double forward slash)
2) Multi-Line Comment: Slash represents it with asterisk symbol as /* write comment here */


# What is the difference between == and ===?
The == operator checks equality only whereas === checks equality, and data type, i.e., a value must be of the same type.

# How to write normal text code using JavaScript dynamically?
The innerText property is used to write the simple text using JavaScript dynamically. Let's see a simple example:
```js 
document.getElementById('mylocation').innerText="This is text using JavaScript";   
```

# What is the difference between undefined value and null value?
Undefined value: A value that is not defined and has no keyword is known as undefined value. For example:
```js  
  int number;//Here, a number has an undefined value.  
 ```
Null value: A value that is explicitly specified by the keyword "null" is known as a null value. For example:
```js  
  String str=null;//Here, str has a null value.
 ```
# What is the difference between View state and Session state?
"View state" is specific to a page in a session whereas "Session state" is specific to a user or browser that can be accessed across all pages in the web application.

# What are the pop-up boxes available in JavaScript?
<ul>
  <li>Alert Box</li>
  <li>Confirm Box</li>
  <li>Prompt Box</li>
<ul>

Example of alert() in JavaScript
```bah
<script type="text/javascript">  
function msg(){  
 alert("Hello Alert Box");  
}  
</script>  
<input type="button" value="click" onclick="msg()"/>  
```

Example of confirm() in JavaScript
```bah
<script type="text/javascript">  
function msg(){  
var v= confirm("Are u sure?");  
if(v==true){  
alert("ok");  
}  
else{  
alert("cancel");  
}  
  
}  
</script>  
  
<input type="button" value="delete record" onclick="msg()"/>  
```
Example of prompt() in JavaScript
```bah
<script type="text/javascript">  
function msg(){  
var v= prompt("Who are you?");  
alert("I am "+v);  
  
}  
</script>  
  
<input type="button" value="click" onclick="msg()"/>  
```<script type="text/javascript">  
function msg(){  
var v= prompt("Who are you?");  
alert("I am "+v);  
  
}  
</script>  
  
<input type="button" value="click" onclick="msg()"/>  
```


