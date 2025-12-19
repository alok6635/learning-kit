**# Basic**

https://github.com/alok6635/escrKit/blob/main/js/demo/basic.md

**#  print 1 to 20 number without loop**


**# sum of nth number**

**# factorial of 15**

* Factorial (15! = 15 × 14 × 13 × 12 × 11..... ) Ek number ke sare numbers ka multiplication.

**# factors of 15**

* Factors (1, 3, 5, 15) Ek number ko divide karne wale numbers

**# fibnocci series of 15**

* Fibonacci series ek sequence hai jisme har number apne pichle do numbers ka sum hota hai.
* F(n) = F(n-1) + F(n-2)

**# prime numbers 1 to 20**
**# check it 13 20 number is prime or not**

* Prime numbers woh numbers hote hain jo sirf apne aap aur 1 se divisible hote hain, aur 1 se bade hote hain. Jaise: 2, 3, 5, 7, 11, 13

**#  square root of a number**

**# add all arguments by for loop**

**# find biggest in two number**

**# biggest in three number**





<details>
<summary>interviewer asked</summary>


i  have a div i want yo add a class and id in the div.
```
<div></div>
document.querySelector('div').id='unique';
document.querySelector('div').classList.add('common')

```

i have 5 div.one parent & four child.i want to add a id in parent and all child add a class.
 next add class only 2 & 4 child.


```
<div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
<div></div>
</div>

let childDivs = parentDiv.querySelectorAll('div');
childDivs.forEach((item)=>{
    item.classList.add('child'); 
})
```

 * given a div width 300px and border 10px find the inner width of by javascript.

```
<div id="demo"></div>
let divId= document.getElementById('demo')
let res=divId.clientWidth;
console.log(res);
```





<details>
<summary>polyfills & pattren</summary>

* forEach-
```
let arr=[1,2,3,4,5]
function print(el){
    console.log(el);
}
Array.prototype.myfun= function(cb){
    for(let i=0;i<this.length;i++){
        cb(this[i])
    }
}
arr.myfun(print)
```
* map-
```
let arr= [1,2,3,4,5]
function print(el){
   return el*2;
}
Array.prototype.myMap=function(cb){
    let newArr=[]
  for( let i=0;i<this.length;i++){
      newArr.push(cb(this[i]));
  }
   return newArr
}
let res= arr.myMap(print)
console.log(res);
```

**# case-I**
```
*****
*****
*****
*****
*****
```
<details>
<summary>Ans</summary>

```
for(let i=0;i<5;i++){
    for(let j=0;j<5;j++){
      document.write('*');
    }
    document.write('</br>')
          }
```
</details>

**# case-II**
```
*
**
***
****
*****
```

<details>
<summary>Ans</summary>

```
for(let i=0; i<5;i++){
    for(let j=0;j<i;j++){
      document.write('*');
    }
    document.write('</br>')
}
```
</details>

**# case-II**
```
*****
****
***
**
*
```
<details>
<summary>Ans</summary>

```
for(let i=0;i<5;i++){
  for(let j=i;j<5;j++){
    document.write('*');
  }
  document.write('</br>')
        }
```

</details>


**# Can you write a random integers function to print integers with in a range**
```
function randomInteger(min, max) {
  return Math.floor(Math.random() * (max - min + 1)) + min;
}
randomInteger(1, 100);
```

</details>


**# find max in array**

```
let numbers = [1, 2, 5,3, 4];
let res=Math.max(...numbers)
console.log(res);

@@@ fallback-
let numbers = [1, 2 , , 5,3,4]; not working Math.max

```

**# Output types**

```
@@@

let count= 0;
(function add(){
    if(count===0){
       let count=1;  
        console.log(count);
    }
    console.log(count);
})()

@@@
let count= 0;
(function add(){
    if(count===0){
        count=1;  
        console.log(count);
    }
    console.log(count);
})()

@@@
let count= 0;
(function add(){
    if(count===0){
       var count=1;  
        console.log(count);
    }
    console.log(count);
})()

@@@
for(var i=0;i<3;i++){
    (function(i){
        setTimeout(() => {
            console.log(i);
        },1000);
    })(i)
}

@@@
for(var i=0;i<3;i++){
        setTimeout(() => {
            console.log(i);
        },1000);
}
@@@
for(let i=0;i<3;i++){
        setTimeout(() => {
            console.log(i);
        },1000);
}


@@@
console.log(false ==0)
console.log(false =='')
console.log(0=='');
@@@
console.log(true + 1);
@@@
let age =24;
console.log(delete age);
@@@
let x=2;
let y= (x=> ++x)(x);
console.log(x,y)
@@@
const a = [1,2,3];
a.push(4);
Object.freeze(a);
a[0] = 10;
console.log(a[0]);

@@@
function x(){
    setTimeout(() => {
        console.log(i)
    },1000);
    let i=10;
}
x()

@@@
console.log([11,2,31,]+ [4,5,6])

@@@
let a = [1, 2, 3];
let b = [4, 5, 6];
console.log(a + b);

@@@
count of types in array 
arr=[function(){}, new Object(), [],{},NaN,Infinity, undefined,null,0]
let result = arr.reduce((a,c)=>{
    let type = typeof c;
    console.log(type);
    
})

@@@
if(true){
     const username = "alok";
     if(username==="alok"){
         const website="youtube";
         console.log(username+website)
     }
     console.log(website)
 }
 console.log(username)

@@@
let a = 'Hello'; 
function greet() {
    let b = 'World';
   console.log(a + ' ' + b);
    if (b == 'World') {
        let c = 'java';
       console.log(a + ' ' + b + ' ' + c);
    }
 console.log(a + ' ' + b + ' ' + c);
}
greet();
```
### Math-
```
console.log(Math);
console.log(Math.abs(-4));
console.log(Math.round(4.6));
console.log(Math.ceil(4.3));
console.log(Math.ceil(4.9));
console.log(Math.floor(4.3));
console.log(Math.floor(4.9));
console.log(Math.min(4,7,2,3));
console.log(Math.random())
```


console.log(+null); // 0
console.log(+undefined); // NaN
console.log(+false); // 0
console.log(+NaN); // NaN
console.log(+""); // 0


**# an argument is a Number or not**

```
function isNumber(n) {
  return !isNaN(parseFloat(n)) && isFinite(n);
}
```


**# How do you detect primitive or non primitive value type**
```
  var myPrimitive = 30;
var myNonPrimitive = {};
function isPrimitive(val) {
  return Object(val) !== val;
}

isPrimitive(myPrimitive);
isPrimitive(myNonPrimitive);
```


