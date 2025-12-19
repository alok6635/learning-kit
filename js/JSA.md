
**#JSA1: Shallow & Deep copy**
* shallow and deep copy is the method of copy array and object. shallow copy creates a new object or array, but only the top-level 
   values are copied by reference.
* deep copy used to the copy of nested object. deep copy creates a new object or array, where all the nested values are also copied by 
  value. This means that all the properties of the original object or array are duplicated, and no references are retained.
* shallow copy in array- slice(),concat(),spread operator.

https://github.com/alok6635/escrKit/blob/main/js/demo/shallow_deep_copy.md

----------

**#JSA2: Call apply bind**
* call is a function that helps change the context of the invoking function.
* apply is similar to the call function.difference is that in apply you can pass an array as an argument list.
* bind is a function that helps create another function that you can execute later with the new context of this that is provided.

https://github.com/alok6635/escrKit/blob/main/js/demo/call_apply_bind.md

-------------

**#JSA3: PreventDefault() v/s return false & void(0)**

* event.preventDefault() method is used to prevent the default behavior of an event and the link click will be prevented.

https://github.com/alok6635/escrKit/blob/main/js/demo/prevent_default.md

--------------

**#JSA4: Events flow(Bubbling Capturing) or propagation**
* event Bubbling- when an event is triggered on a dom element, it first fires on that element, then on its parent, and so on, 
    propagating up the DOM tree.
* event Capturing -opposite of event bubbling, where the event is captured at the top most parent element and then propagates down to 
    the target element.
* stop propagation- stopPropagation method is used to stop the event from bubbling up the event chain.

https://github.com/alok6635/escrKit/blob/main/js/demo/event_flow.md

--------------

**#JSA5: Event delegation**

* event delegation is a technique where you attach an event listener to a parent element to handle events for its child elements.

https://github.com/alok6635/escrKit/blob/main/js/demo/event_delegation.md

--------------

**#JSA6: var & let & const**
   * scoping behavior
        * var is global & function scope.but it does not have block scope.
        * let & const is global & block scope and.It does not have function scope.
   * hoisting
        * all of them are hoisted but let & const have TDZ.
   * re-declaration
        * var can be re-declared in the same scope. let & const can't re-declared in the same scope.
   * re-assignment
       * var & let can be updated in the same scope but const can't be updated.
         
https://github.com/alok6635/escrKit/blob/main/js/demo/var_let_const.md


--------------

**#JSA7: Hoisting**

* Hoisting is a default behavior of js.variable and function can be used before it has been declared. variables and normal functions 
   are hoisted as undefined.
 * hoisting will not work with curly brackets & arrow function & variable function.

https://github.com/alok6635/escrKit/blob/main/js/demo/hoisting.md


--------------

**#JSA8: Temporal dead zone(TDZ)**
* TDZ is a concept in js that relates to the hoisting of the variables and the visibility of variables    declared with let and const. In the TDZ, a variable exists but it cannot be accessed until it is not declared. This prevents the variable from being used or accessed before a value is assigned to it.

--------------
  

**#JSA9: Normal function v/s arrow function and this keyword**
* normal functions, this is determined at runtime, meaning it depends on the context from which the function is called.
* arrow functions, this is lexically bound, meaning it retains the this value of the scope where the function was 
  defined, regardless of where it is called.
* arrow function does not have own this.It presents one label up or surrounding and we can not change this.
* arrow function's is not hoisted and not accept the arguments and no available prototype and no working new keyword.
* arrow Functions Cannot be Used as Constructors
* this keyword refers to the current context of the object.

https://github.com/alok6635/escrKit/blob/main/js/demo/nrml_ftn_arrow_ftn.md

--------------

**#JSAT10: lexical scope**

In inner ftn we can access the variable of the outer ftn.the child ftn is seen to have lexically bound the parent ftn.
It is also called static scoping.

https://github.com/alok6635/escrKit/blob/main/js/demo/lxcl_scp_closr_currny.md


**#JSA11: closure**

* closures- closures allow functions to remember the variables from the scope where they were created, even if the function is executed in a different scope.
  
https://github.com/alok6635/escrKit/blob/main/js/demo/lxcl_scp_closr_currny.md

--------------
  
**#JSA12: curring**

* Currying in JavaScript transforms a function with multiple arguments into a nested series of functions, each taking a single argument.
  Currying helps you avoid passing the same variable multiple times, and it helps you create a higher order function.  

https://github.com/alok6635/escrKit/blob/main/js/demo/lxcl_scp_closr_currny.md

--------------

**#JSA13: Promises**
* promise is an objects. promises is manage to asynchronous task- Db calls, networks call, cryptography, handling of asynchronously tasks and 
    avoiding callback hell.
* three states is promises-
    * pending- default state of a defined promise.
    * resolved- state of a successful promise.
    * rejected- state of a failed promise. 
* once created a promise & consume, promises expose several methods for handling their resolution and rejection states.
    * then()- attaches a callback function to be executed when the promise is fulfilled.
    * catch(): attaches a callback function to be executed when the promise is rejected.
    * finally(): attaches a callback function to be executed regardless of the promise's state(whether fulfilled or rejected).
      
* types of promise-
   * when multiple promise working at parralely then use of all, allsettled, race. but it's output is different everyone.
   * all- when resolve the all promises then gives result.if any one promises it failed the result is failed all.
   * allsettled- when resolve the all promises then gives result how many promises failed and how many resolved.
   * race- gives output whoes promises resolve first.
   * any-
  
https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md

----------

**#JSA14: async & awit**
* async & await make promises easier to write resolve dot then problems. async functions return a promise, await makes a function wait for a promises.
   * promises v/s async & await-
      * promises-
        * state- pending,resolve,rejected
        * handling- .then(),.catch(),.finally()
        * ES6(2015)
        * promises chains become difficult to sometimes.
      * async-
         * state- no any state
         * handling- .try(),.catch(),.finally()
         * ES7(2017)
         * async/await makes it easier to read & understand the program.
           
https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md

------------

**#JST15 difference of import & require()**
* import and require() are both used to load modules, but they belong to different module systems.
* execution- require- synchronous(blocking) & import-  asynchronous(non-blocking)
* require() part of CommonJS. & part of ES6.

**#JSA16: throttling**

https://github.com/alok6635/escrKit/blob/main/js/demo/hoisting.md

------------

**#JSA17: Debouncing** 

https://github.com/alok6635/escrKit/blob/main/js/demo/hoisting.md

------------

**#JSA18: memoization** 

* memoization is a optimization technique that can be used to reduce time-comsuming calculations by saving previous input to something called cache and returning the result from it. 
  
 https://github.com/alok6635/escrKit/blob/main/js/demo/hoisting.md


------------

**#JSA19: fetch v/s axios v/s ajax**

* fetch- fetch is used to make network requests, typically to fetch resources from a server. It returns a promise that resolves to the Response object 
 representing the response to the request.
* axios-
* ajax- without reload page we can communicate with server

* api call by fetch-
  
https://github.com/alok6635/study-kit/blob/main/demo/js/fetch-api.html

------------

**#JSA20: how to handle Abort in fetch**

* cancel an API request, we can use AbortController.
  
----------

**#JSA21: cors error**
* when we send a request from one domain (frontend) to another domain (backend API), the browser may block it due to security reasons.
* resolve front End side- use proxy
  
```
package.json-
"proxy": "http://localhost:5000"
``` 

----------


**#JSA22: HTTP methoed (CRUD)**

* every HTTP interaction includes a request and a response.HTTPS for a secure version of HTTP.All HTTP messages have one or more headers,followed by an 
   optional message body. body contains the data that will be sent with the request or the data received with the response.
* four HTTP methods- get(read),put(update),post(create),delete.
  
------------

**#JSA23: status code**

* there are five groups of status codes.
* 100-199— informational response.
* 200-299— responses successfull.
* 300-399— redirection message.
* 400-499— client error message.
* 500-599— server error message.

------------

**#JSA24: Event loop**

* hanlde asynchronous programming(timers,setTimeout,api). js is a single-threaded language.

------------

**#JSA25: difference between process.nextTick() and setImmediate**

* setTimeOut and setinterval- setTimeout function calls only on time at spoecified time.setInterval call again and again at spoecified time.it's gives a id we can clearTimeOut(id).

https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md

----------

**#JSA26 server sent events & client sent events**

----------


**#JSA27 Prototypical inheritance**
* objects are extended from other Objects. and we can re-use them properties and method.
* objects are chained in prototypical inheritance.
* objects have a hidden property called prototype.

* .__proto__
   * .__proto__ is a getter/setter for [[Prototype]]
   * .__proto__ is not  used now & recomded way is to use Object.getPrototypeOf() &  Object.setPrototypeOf()

https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md


**# iterables & iterators**
* iterables-
  * iterables are objects which we can make array like iteration (exaple using for of loop of spread operators)
  * array & string are iterables.
  * to make any object iterables we have these conditions
  *  implement a Symbol.iterator property which should be a function which return in iterartor object.
    
```
iteraable[Symbol.iterator]()=>Iterator
```
* iterator-
* iterator are a object which have a next () method which return a object which is of  format {value:-some-value-,done:-boolean}.
* value is the value we are interested in while done tell us when to stop. Genaerally when done:true the value undefined.

https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md
      
----------

**# iterable V/s Array-like**
* iterable objects are based on Symbol.iterator method. 
* Array-like objects are based on array protocols(index & length); 

----------

**# conversion Array-like to array**

 * Array.from()
```
let arrayLike ={
    0:0,
    1:5,
    length:2
}
console.log(Array.from(arrayLike))

* set proper array nhi hota hai Array-like hota hai. 
```
----------


**#JSA26: sets**

* set is another iterable.
* set only contains uniques elements.
* map me key & value hoti hai but set me only ek value store hote hi (jo ki hme keys(),values(),entries() me dkhne ko milegi).

https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md

----------


**JST22 create a array using by set**
* Set is a built-in object that represents a collection of unique values.
* It is similar to an array but with some key differences.
* it is not show duplicate number & not working push pop array method & foreach method is worked.
* it some method- add,delete,has,values

```
let data=new Set([1,2,3,4])
let arr=Array.from(data)
console.log(arr);
```
----------

**#JSA27: compare Object and Map**
  
* Object can be keys is Strings and Symbols.map can be key functions, objects, and any primitive.
* keys in a Map are ordered while keys added to Object are not.

* map method-
   *  it is alos a iterable.
   *  special  this is can have key also as numbers,boolean,objects.
   *  also map maintain the order of keys added. this property not maitain to the object.
   * A Map holds key-value pairs where the keys can be any datatype.
   * A Map remembers the original insertion order of the keys.
   * A Map has a property that represents the size of the map.
     
```
set(), get(),clear(),delete(),has(),forEach(),entries(),keys(),values().
## Create a Map-
const fruits = new Map([["apples", 500], ["bananas", 300],["oranges", 200]])
```
------------

**#JST21 generator**
* easy way to create an iterator & iterable.
* it is special function before function always .and it have yield as normal function return and here it can retun more then one 
and it will itable(like array ) and itrator (means get next value .next )

https://github.com/alok6635/escrKit/edit/main/js/demo/hoisting.md

--------------


**# weakMap & weakset**

* Thesre are 2 alternative way of creating Map or Set Like data types - when only objects key are considered.
* they have very limited operations and doesn't support all functionality.
* main purpose is that when keys are marked as null they are garbage collected.so this helps in better memory management.
  
--------------


**#JST JWT Token**
"JWT (JSON Web Token) is a secure way of exchanging data between the server and client. It is a compact token structure primarily used for authentication and authorization. A JWT consists of three parts: Header, Payload, and Signature. The Header defines the algorithm and type, the Payload contains claims (such as user ID, role, etc.), and the Signature ensures that the token hasn't been tampered with. Because JWT is stateless, the server doesn't need to fetch the user's information repeatedly.

--------------

**# configurations properties of Objects**

* writeable- true/false
* configuration- true/false
* value- value of property
--------------




**# Topics related Videos**

* var & let & const-
https://www.youtube.com/watch?v=mtzV1HtRZ_s

* Hoisting
https://www.youtube.com/watch?v=PLT8BsjaOmQ

* memoization
https://www.youtube.com/watch?v=tkQ2nMHbSqo&t=285s
 
* Normal function v/s arrow function and this keyword
https://www.youtube.com/watch?v=695X6ktpq6c

* JWT Token-
 https://www.youtube.com/watch?v=uuvc4Gl-wEs

 https://www.youtube.com/watch?v=O4tJrcRCyco 







