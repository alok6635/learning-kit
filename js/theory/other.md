

**# What is the difference between document load and DOMContentLoaded events**
* DOMContentLoaded-   initial HTML document has been completely loaded and parsed, without waiting for
      assets(stylesheets, images, and subframes) to finish loading. 
* document load-    whole page has loaded, including all dependent resources(stylesheets, images).


**# number data type**
```
const num =400;
console,log(num);
@@@ Number-
const balance = new Number(100)
console.log(balance)
```

```
@@@ to fixed-
let num = 100;
console.log(num.toFixed(3))

@@@ toPrecision-
// let num = 23.8966;
// let num = 123.8966;
let num = 1123.8966;
console.log(num.toPrecision(3));

@@@ toLocaleString-
const  count =1000000;
console.log(count.toLocaleString())
console.log(count.toLocaleString('en-IN'))

```

**# date**

```
let myDate = new Date()
console.log(myDate)
console.log(typeof myDate)
console.log(myDate.toString())

let mycreateDate = new Date(2023,0,23)
console.log(mycreateDate.toDateString())
let mycreateDate1 = new Date(2023,0,23,5,3)
console.log(mycreateDate1.toLocaleString())
```

**# falsy value**

false- 0, -0, BigInt 0n, "", nulll,undefined, Nan.
truthy- "0", "false", " ", [], {}, empty ftn-(function(){})


**# flow control**
 * if ,else, else if, switch case.

**# add to dom**
```
<div class="CreateDom">  
    <p>This is a first para</p>
    <p>This is a second para</p>
</div>
<script>
    let newElement= document.createElement("h2");
newElement.textContent = "Add to Dom";
document.querySelector(".CreateDom").prepend(newElement);
</script>
```   
**# Nullish Coalescing operator (??):null undefined**
```
let val1; 
val1 =5 ?? 10; //
val1 =null ?? 10; //
val1 =undefined ?? 15; //
val1 = null ?? 10 ?? 10
console.log(val1)
```

**# purpose JSON stringify**
  * When sending data to a server, the data has to be in a string format.used- Json.stringify()

**# parse JSON string**
   * When receiving the data from a  server the data is always in a string format. used- Json.parse()
     

**# convert date to another timezone in javascript**
 * You can use the toLocaleString() method to convert dates in one timezone to another
   
**# properties used to get size of window**
* innerWidth, innerHeight, clientWidth

**# eval method**  
   * eval() function is used to run text as code.
     
**#  uneval()**
 * deprecated but recommended toString(). it converts code to string.

**# set in object**
  * looking like a array find the unique number. method aviaible  keys, values, entries, forEach, clear.


**# rest parameter**
Rest parameter is an improved way to handle function parameters. rest parameter should be the last argument.

**# detect javascript disabled in the page**
<noscript></noscript>

**# purpose of double exclamation**
   * ensures the resulting type is a boolean
     

**# What is isNaN**
```
isNaN("Hello"); 
isNaN("100"); 
```

**# isFinite function  ?**
* for checking infinite number

