# What are JavaScript Data Types?

Following are the JavaScript Data types:

Number
String
Boolean
Object
Undefined

# What are global variables? How are these variable declared and what are the problems associated with using them?

Global variables are those that are available throughout the length of the code, that is, these have no scope. The var keyword is used to declare a local variable or object. If the var keyword is omitted, a global variable is declared.

Example:

// Declare a global globalVariable = "Test";

The problems that are faced by using global variables are the clash of variable names of local and global scope. Also, it is difficult to debug and test the code that relies on global variables.

# What is 'this' keyword in JavaScript?
'This' keyword refers to the object from where it was called.

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


