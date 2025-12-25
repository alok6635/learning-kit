
**# TOPIC ARRAY**
* Array is a object.it is mutable- changes the original array.index start is 0 and length start is 1.
* mutable methods- push,pop,shift,unshift,splice,sort,reverse,fill,copyWithin. 
* immutable methods- concat,slice,map,filter,reduce,join,find,findIndex,includes.


*# slice v/s splice*

* slice- doesn’t change the original array.returns a new array.It returns a new array and works from the start index up to the end index (but not including the end index).
* splice- splice method change the original array.it's use for adds/removes items in array.first argument is the index position.second argument (optional) is the number of elements to remove.extra arguments are elements to add

```
** slice- 
let arr = [1,2,3,4,5,6];
let arr1 = arr.slice(4); 
console.log(arr1);
let arr2 = arr.slice(-1); 
console.log(arr2);
let arr3 = arr.slice(0,2); 
console.log(arr3);
let arr4 = arr.slice(2,3); 
console.log(arr4);

** splice-
let arr = [1, 2, 3, 4, 5];
let res = arr.splice(3);
console.log(res)
console.log(arr)

let arr = [1, 2, 3, 4, 5];
let res = arr.splice(0, 2); 
console.log(res);

let arr=[1,2,3,4,5,6]
let res= arr.splice(2,3,15,20,50)
console.log(res)
console.log(arr)

let arr = [1, 2, 3, 4, 5];
let res = arr.splice(2, 0, 9);
console.log(res);  
console.log(arr);
```
----------------------------------------------------------------------


*# Array.from*
* Array.from does not change the original array.It returns a new array.used to copy arrays or convert array-like/iterable objects into arrays.
```
let arr= [10,20,30]
let res= Array.from(arr);
console.log(res);
console.log(arr);
```
* arr→ original array, Array.from(arr)→ creates a shallow copy of arr.res and arr have same values, but they are different arrays in memory

----------------------------------------------------------------------


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









