**#JSTB1: function declarations v/s function expressions**
 * main difference is the hoisting.function declaration have the hoisted but function expressions is not hoisted.
   
```
@ declarations-
function sum(a,b){
   return a+b;
}

@ expressions-
let sum = function(a,b){
   return a+b;
}
```

**#JSTB2: function expression v/s anonymous function**

```
@ function expression-

const myFun = function greet() {
    console.log('Hello!');
  };

@ anonymous function-
const myFun = function() {
    console.log('Hello!');
  };
```
**#JSTB3: IIFE**

* self invoking function.it is a function that is called immediately after it is defined.
* IIFE is to obtain data privacy(declare a variable in IIFE. it can nor access outside), and two IIFE terminate by semicolon.
   IIFEs prevent pollution of the global scope.
* iife was popular due to var.  

```   
@ named IIFE-
(function(a,b){
    console.log(a+b)
  })(10,20);

@ without named IIFE-
((a,b)=>{
    console.log(a+b)
  })(10,20)
  Note- ydi 2 IIFE likhne ho to ; ko jarur lga le nhi to next code run hi nhi hota hai
@Imp-  
(function () {
  var message = "IIFE";
  console.log(message);
})();
console.log(message);

@ var case-
(function(a)=>{
var x= a  //this var is now protected
})(2)

console.log(x) // x is not defined
```

**#JSTB4: callback function & high order function**

*  callback- a function passed as an argument to another function, executed after the parent function completes.
*  cb create a pyramid-like structure,reducing code readability & maintainability.each callback depends on the previous one.
*  higher order functions are functions that take one or more functions as arguments, or return a function as their result.
      * map- map method returns a new array and modified the original array.map method is similar to the forEach.
      * forEach- it is only iterable.do'es not return a array.
      * reduce- accumulator-empty variable or container, currentValue- current value of array. return a value.
      * find- gives a first occeranice.
      * every,some,flapmap
  
```
@ map-
let arr = [2,3,4,5,7]
let x= (item)=>{
    return item*2;
}
let res = arr.map(x)
console.log(res);
```

**#JSTB5: hof v/s call back**
```
function cb(){
    console.log('I am  a callback function');
}
function hof(func){
    console.log('I am higher order function')
    func()
}
higherOrderFunction(cb);
```

**#JST6: first order function**

* first-order function is a function that doesn't take other functions as arguments and doesn't return functions as results.
   It can take other data types as arguments and return other data types as results.
   
**#JST7: first class function/citizen**

* assign a variable. and passed as an argument to ther functions. and return from other functions.

```
function greet(name) {
    return name;
  }
  let sayHello=greet; //assigning the function to a variable
  console.log(sayHello("Alice"));
```

**#JSTB8: function composition**
* combining two or more function to produce a new function.

**#JSTB9: pure function** 
  * pure function is a function  which given the same input, always returns the same output.
     and produces no side effects.side effects- Date,math,Random(),http request, data manipulating,use the console (if all ftn is used 
     then ftn is not pure ftn)
```
@ pure-

x=9;
function sqr(x){
    return x*x
}
console.log(sqr(5));

@ Impure ftn-

x=9;
function sqr(){
    return x*x
}
console.log(sqr());

```
**#JSTB10: unary function**

* unary function (i.e. monadic) is a function that accepts only one argument.
```
function sqr(x){
    return x*x
}
console.log(sqr(5));
```

**#JSTB11: object method**

* Object.keys()
* Object.values()
* Object.entries()
* Object.freeze()
* Object.seal()
* hasOwnProperty()

**Object.freeze()**
* not allow modify/add/delete property.
* if object is nested then it can be modified.
```
let person = {
    name:'alok',
    age:35,
    city:'kanpur'
}
Object.freeze(person)
person.name ="kittu"
person.color ="red"
console.log(person)

@@@ object is nested then it is modified-
let person = {
    name:'alok',
    age:35,
    city:'kanpur',
    details:{
        salary:10000
    }
}

Object.freeze(person)
person.id=777
console.log(person);
person.details.salary=20000
person.details.course='html'
console.log(person);
delete person.details.year
console.log(person);


```
**Object.seal()**
only modify no add and delete  property.
if object is nested then can it add/delete/modify
* 
```
let person = {
    name:'alok',
    age:35,
    city:'kanpur'
}
Object.seal(person)
console.log(person);
person.name ="kittu"
person.color = "red" 
console.log(person)

@@@ object is nested then can it add/delete/modify-
let person = {
    name:'alok',
    age:35,
    city:'kanpur',
    details:{
         course:'html',
           salary:15000
            }
}
Object.seal(person)
console.log(person);
person.details.course='react'
person.details.teacher='aman'
delete person.details.salary
console.log(person);
```

**#JSTB12: Cloning an Object**

   *  Spread Operator
   *  Object.assign()
   *  JSON.parse() & JSON.stringify()

     
```
let obj1 = {1:"a", 2:"b"}
let obj2 = {3:"c", 4:"d"}
let obj3 = Object.assign({},obj1,obj2)
console.log(obj3)
```

**#JSTB13: synchronous v/s asynchronous**
* synchronous-
  * j.s. is a synchronous language.synchronus code excute line by line. if first line is not excute then code 
    execution will not move to the next line.then we do our code in asynchronous type.
```
console.log('one');
console.log('two');
console.log('three');
```

* asynchronous-
  * code run in the background without blocking the execution of other code.ex-setTimeout,setInterwal,fetch,event loop.
  * 3-ways handle asynchronous tasks.
   * callback, promises, async & await.
     
```
console.log('one');
setTimeout(()=>{
console.log('two');
},2000)
console.log('three');
```

https://github.com/alok6635/Aeronautics/blob/main/js/concept/demo/synchronus_async.md

**#JSTB14: ES6**

**# rest operator array & Object**

https://github.com/alok6635/Aeronautics/blob/main/js/concept/demo/rest_operator.md

**# Array & Object Destructuring**

* destructuring- extract the data array & object.skip a value, use a comma in the destructuring pattern.ex- [a,b,,e]

https://github.com/alok6635/Aeronautics/blob/main/js/concept/demo/destructring.md


**# default parameter**
```
function add(name ='alok'){
    return name
  }
  console.log(add('hitesh'))
  console.log(add())
```
**#  rest parameter & spread operator**

```
@ rest-
const show =(a,b,c,...rest)=>{
    console.log(a,rest)
}
show(2,3,4,5,6,7,8,9);

@ spread-
const show=(a,b,c,d)=>{
    return a+b+c+d;
}
let arr= [2,3,4,5]
console.log(show(...arr))
```
**# template literal.**


```
* use template literal-
let data= `this is my 
            new dell laptop`
console.log(data);

* use without template literal-
let data= "this is my 
            new dell laptop"
console.log(data);// its give the error

** interploartion of template literal-
let firstName = "alok";
let lastName = "kumar";
let data = ` hello ${firstName} ${lastName}`
console.log(data)
```

* let & const- variable constant
    * arrow function- 

    * default parameter-  not any value pasde function params and it's take default value.
    *  rest & spread operator- works at different context .
          Spread Operators allow us to expand an array or object into its individual elements. Rest Operator allows us to condense 
          multiple elements into a single array.
   
     * classes- to make objects from a particular blue print
     * modules
     * promises- to take care of async part.
     * async & await- to take care of async part but more elegantly.
     * try & catch- to take care of error handling.
      

**# Difference for of loop & for in loop**

**# Difference map & forEach**

* nor modified the original array return a new array.
```
## map-
let arr = [1, 2, 3, 4, 5];
let res = arr.map((item) => item * 2);
console.log(arr);
console.log(res);

## forEach-
let arr = [1, 2, 3, 4, 5];
let res = []; 
arr.forEach((item) => {
  res.push(item * 2); 
});
console.log(arr); 
console.log(res);
```

**JSTB14: web storage.how to access web storage**

   *  local storage- no expiration date.
   *  session storage- close tab it expire.
     
```
localStorage.setItem("logo", document.getElementById("logo").value);
localStorage.getItem("logo");
```

**#JSTB15: Cookies**

*   When a user visits a web page, the user profile can be stored in a cookie.Next time the user visits the page, the cookie remembers 
       the user profile.Cookies are saved as key/value pairs.
```
 document.cookie = "username=John".**
 document.cookie ="username=; expires=Fri, 07 Jun 2019 00:00:00 UTC; path=/";
```

**#JSTB16: differences between cookie, local storage and session storage**



**#JSTB17: check web storage & web workers browser support**

```
@ web storage-
if (typeof Storage !== "undefined") {
  // Code for localStorage/sessionStorage.
} else {
  // Sorry! No Web Storage support..
}
@ web workers-
if (typeof Worker !== "undefined") {
  // code for Web worker support.
} else {
  // Sorry! No Web Worker support..
}

```

**# strict mode in javascript**

```
x = 10; 
console.log(x);

"use strict";
x = 10; 
console.log(x)

```

**# differences between undeclared and undefined variables**

```
## Undefined- not assigning value 
let x;
console.log(x);

## undeclared-  not creating variable.
console.log(x);
```

**#JSTB18: which keywords are used to print the text on the screen.**
* document.write.

**#JSTB19: use of void(0)**
* prevent the page from refreshing and parameter zero is passed while calling.

**#JSTB20: error types in js.**

```
load time error
run time error
logical error 
```

**#JSTB21: find date**

```
let today= new Date()
let dd= String(today.getDate())
console.log(dd);
let mm=String(today.getMonth()+1).padStart(2,'0')
console.log(mm); 
let yy=today.getFullYear()
console.log(yy);
today = dd + "-" + mm + '-' + yy
console.log(today);
```

**#JSTB22: decode or encode a URL in JavaScript**

* encodeURI(), decodeURI(),
* encode characters such as / ? : @ & = + $ # then you need to use encodeURIComponent()
      
**#JSTB23 server-sent events check browser support for server-sent events**

```
if (typeof EventSource !== "undefined") {
  // Server-sent events supported. Let's have some code here!
} else {
  // No server-sent events supported
}
```

**# excucation context**
Three terms-
1.Global Execution Context: global cxecution context refer the "window" object.(locate this).
2.functional excutation context-functions execution contexts are created as needed and removed from the stack when finished. stacks fallow the LIFO(last in first out)
3.eval excutation context- it is a property of the global object. no need of read yet time. 

*code run in the two phases-
 When js code start run.first code run in the global excution. and locate in the this keyword.and then memory creation and excution phase.
1.memory creation phase : space located of the variables.
2.Execution Phase: Running the code.

**# preventDefault**
 remove to default behavior in js.
 
**# Event Listener**
addEventListner() is a js method that allows adding more than one handler for an event.
```
<button id="btnsubmit">submit</button>
document
```

**# Local storage & session**
allows you to save data in the browsers.it has no expiration date.when browser is closed, no data is deleted.
session storage has fixed expiration date.when browser is closed and change the tab data is deleted.
```
localStorage.setitem("username","alok");
localStorage.getitem("username");
localStorage.removeitem("username");
localStorage.clear()
```

======================== promise quesion  start here ================

* What is a promise & What is promise chaining & What is promise.all & Promise.race.
    * chaining - then=>then=>then
@@@ promise all
```
Promise.all([Promise1, Promise2, Promise3]) .then(result) => {   console.log(result) }) .catch(error => console.log(`Error in promises ${error}`))

@@@ promise race-
var promise1 = new Promise(function (resolve, reject) {
  setTimeout(resolve, 500, "one");
});
var promise2 = new Promise(function (resolve, reject) {
  setTimeout(resolve, 100, "two");
});

Promise.race([promise1, promise2]).then(function (value) {
  console.log(value); // "two" // Both promises will resolve, but promise2 is faster
});
```

**#  various statements in error handling**
```
try,catch,finally
throw-generate custom error
```

**# two types of loops in javascript**
```
entry control- for,while
exit control- do while
```

**# event loop**
* event loop monitor callstack & event queue.

**# What is call stack**
* Lifo

**# event queue**
* It is also known as the Callback Queue or Macrotask Queue.
* event queue- settimeout()
* micro queue- promises


**# What is a decorator ?**

**# Unary operator (+)**

```
var x = "100";
var y = +x;
console.log(typeof x, typeof y); 
var a = "Hello";
var b = +a;
console.log(typeof a, typeof b, b);
```


**# Is it possible to add CSS to console messages**

```
console.log(
  "%c The text has blue color, with large font and red background",
  "color: blue; font-size: x-large; background: red"
);
```

**# do you disable right click in the web page**
```
<body oncontextmenu="return false;"></body>
```

**#  difference between shim and polyfill**

* A shim is a library that brings a new API to an older environment
* polyfill is a piece of code (or plugin) that provides the technology  expect the browser to provide natively.

**# What is babel**

* JavaScript transpiler to convert ECMAScript 2015+ code into a backwards compatible version of JavaScript in current and older browsers or environments

**# How do you check an object is a promise or not**

* Promise.resolve(value)

**# what are generator function**
```
function* myGenFunc() {
    yield 1;
    yield 2;
    yield 3;
  }
  const genObj = myGenFunc();

  console.log(genObj.next());
  console.log(genObj.next());
```

**# nullish coalescing operator (??)**

* It is a logical operator that returns its right-hand side operand when its left-hand side operand is null or undefined, and otherwise returns its left-hand side operand.

```
console.log(null ?? true); // true
console.log(false ?? true); // false
console.log(undefined ?? true); // true
```
**#  dense and sparse arrays?**
```
An array contains items at each index starting from first(0) to last(array.length - 1) is called as Dense array. Whereas if at least one item is missing at any index, the array is called as sparse.
```

**# How do you reverse an array without modifying original array?**

```
you can use reverce but it will change orignal array so 
use slice then reverse
spread and reverse
```

**# hw to check it is array**
* instanceof operator:
* Array.isArray
```
@@@ console.log(arr instanceof Array); 
@@@ Checking constructor type-
const numbers = [1, 2, 3];
const user = { name: "John" };
console.log(numbers.constructor === Array); // true
console.log(user.constructor === Array); // false
```

**#  Hosting -I**

```
**# console.log(10 == [10]); it will convert [10] is 10 when compare opertot
**# console.log([1, 2] + [3, 4]) // 1,23,4
**# Nan == or === Nan because it never equal

**#
```
const sym1 = Symbol("one");
const sym2 = Symbol("one");

const sym3 = Symbol.for("two");
const sym4 = Symbol.for("two");

console.log(sym1 === sym2, sym3 === sym4);// true,false

```
Symbol.for() function creates a symbol in a global symbol registry list. But it doesn't necessarily create a new symbol on every cal




**# !! return the false value**

```
function checkName(){
    return !! this.name
}
console.log(checkName('alok'))
```








