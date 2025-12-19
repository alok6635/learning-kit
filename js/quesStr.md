**# String**

https://github.com/alok6635/escrKit/edit/main/js/demo/strAns.md

**# check if a string starts with another string.**

 
**# remove duplicate characters from string. & return duplicate character of string.**
 
**# replace a word in string**

**# Palindrome**
 
**# check anagrams string**
 
**# count string character**


**# object**

https://github.com/alok6635/escrKit/edit/main/js/demo/obj.md

```
let person = {
     name:'alok',
     age:35,
     city:'kanpur'
 }

```

**# find key/values & using by entries**

**# key exists in object**

**# how many keys present in object**

**# how to check an empty object**

**# enumerable propery in object**

**# change the object key and value**



**# output Types**



##1-

```
let count= 0;
(function add(){
    if(count===0){
       let count=1;  
        console.log(count);
    }
    console.log(count);
})();
```

##2-

```
let count= 0;
(function add(){
    if(count===0){
        count=1;  
        console.log(count);
    }
    console.log(count);
})()

```

##3-
```


let count= 0;
(function add(){
    if(count===0){
       var count=1;  
        console.log(count);
    }
    console.log(count);
})()

```
##4-
```

for(var i=0;i<3;i++){
    (function(i){
        setTimeout(() => {
            console.log(i);
        },1000);
    })(i)
}

```

##5-
```

for(var i=0;i<3;i++){
        setTimeout(() => {
            console.log(i);
        },1000);
}
```

##6-
```



for(let i=0;i<3;i++){
        setTimeout(() => {
            console.log(i);
        },1000);
}

```


##7-
```

function x(){
    setTimeout(() => {
        console.log(i)
    },1000);
    let i=10;
}
x()
```


##8-
```

count of types in array 
arr=[function(){}, new Object(), [],{},NaN,Infinity, undefined,null,0]
let result = arr.reduce((a,c)=>{
    let type = typeof c;
    console.log(type);
    
})
```

##9-
```

if(true){
     const username = "alok";
     if(username==="alok"){
         const website="youtube";
         console.log(username+website)
     }
     console.log(website)
 }
 console.log(username)
```

##10-

```
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

##11-

```
const accountId=14545;
let accountEmail= 'alok556';
var accountPass='12345';
acountCity='jaipur';
let accountState;
 accountEmail= 'kittu@6632'; //show error if mention-let,var,const
 accountPass='2323242';//show error if mention-let,const
acountCity='kanpur';
console.table([accountId,accountEmail,accountPass,acountCity,accountState])
```

##12-

 * hoisting- function expressions is Not Hoisted.
```
sayHi();
var sayHi = function() {
  console.log('Hi!');
};

```
##13-

```
var x = 10;
function outer(){
  console.log(x); 
  var x = 20;
  function inner(){
    console.log(x);
  }
  inner();
}
outer();
```

##14-

```
let x = 10;
function myFunction() {
  console.log(x);
}
myFunction();
```

##15-

```
function myFunction() {
  console.log(x);
}
myFunction();
let x = 10;

```

##16-

```
var a = 2;
var b = 0;
while(a <= 4){
    a++;
    b += a * 2;
    console.log(b);
}
```

##17-

```
{
    var a=10;
    {
        var a =30;
    }
    console.log(a)
    }
```

##18-

```
{
    let a= 4;
    {
    let a=5;
    }
    console.log(a)
}
```

##20-

```
 {  
    let a=20;
    {
       a=21;
    }
    console.log(a)
}
```


****# pending readings-

#00
  {  
    let a=20;
    {
      var a=21;
    }
    console.log(a)
}
#00
  {  
    const a=20;
    {
      var a=21;
    }
    console.log(a)
}


#00
function add(){
  a=10; 
}
add()
console.log(a);

#00
let name = 'alok';
function getName(){
    console.log(name);
    var/let name = 'anil'
}
getName();

#00
let name = 'alok';
function getName(){
    console.log(name);
     name = 'anil'
}
getName();

#00
function greet([firstName, lastName]) {
    console.log(`${firstName} ${lastName}`)
  }
  greet(['John', 'Doe'])

#00
function example() {
  var x = 10;
  let y = 20;
  if (true/false) {
    var x = 30;
    let y = 40;
    console.log("Inside if block - var x:", x);
    console.log("Inside if block - let y:", y);
    }
  console.log("Outside if block - var x:", x); 
  console.log("Outside if block - let y:", y); 
}
example();

#00
function varTest(){
  var x=31;
  if(true){
    var x=71;
    console.log(x);
  }
  console.log(x);
}
varTest()

#00
function greet([firstName, lastName]) {
    console.log(`${firstName} ${lastName}`)
  }
  greet('John', 'Doe')

#00
 function func1() {
    setTimeout(() => {
        console.log(x);
        console.log(y);
    },9000)
}
var x = 2;
let y = 12;
func1()

#00
let counter = 0;
function incrementCounter() {
  counter++;
  console.log("Counter:",counter);
  if(counter === 5){
    clearInterval(intervalId);
    console.log("Interval stopped.");
  }
}
let intervalId = setInterval(incrementCounter, 1000);


var arr1=[];
for(let i=0; i<10;i++){
    arr1.push(setTimeout(()=>{
        console.log(i);
    },1000))
}


#00
 function hello(){
  for(var i=0;i<3;i++){
      setTimeout(()=>{
          console.log(i);
      },1000)}}
  hello()

#00
function hello(){
for(let i=0;i<3;i++){
    setTimeout(()=>{
        console.log(i);
    },2000)}}
hello()

#00
let x={}, y={name:'ram'}, z={name:'alok'};
x[y]={name:'vivek'};
x[z]={name:'kittu'};
console.log(x[y]);

#00
let a=a+1;
console.log(a);
A-NaN;
B-1;
C-a;
D-RefereceError

#00
var arr=[1,2,3,4]
arr.concat([5])
console.log(arr.length);

#00
refresh webpage in J.s. by using-
A-window.reload
B-location.reload
C-window.refresh
D-page.refresh

#00
function foo(){
  let x = (y = 0);
  x++;
  y++;
  return x;
}
console.log(foo(), typeof x, typeof y);

#00
var y = 1;
if (function f(){}) {
  y += typeof f;
}
console.log(y);


</details>

#00
 function foo() {
    return;
    {
      message: "Hello World";
    }
  }
  console.log(foo());

#00-
const obj = {
  prop1: function () {
    return 0;
  },
  prop2() {
    return 1;
  },
  ["prop" + 3]() {
    return 2;
  },
};
console.log(obj.prop1());
console.log(obj.prop2());
console.log(obj.prop3());

#00
const set = new set([1,1,2,3,4]);
console.log(set);

#00
const result = false || {} || null;
console.log(result);
const result = false || 20 || null;
console.log(result);
const result = false || {} || 20 || null;
console.log(result);
const result = null || '' || false;
console.log(result);
const result = null || false || '';
console.log(result);
const result =[] || 0 || true;
console.log(result);

#00
let a=5, b=0, c=7
console.log(a&&b&&c);


#00
var myChars = ["a", "b", "c", "d"];
delete myChars[0];
console.log(myChars);
console.log(myChars[0]);
console.log(myChars.length);

#00
var array1 = new Array(3);
console.log(array1);
var array2 = [];
array2[2] = 100;
console.log(array2);
var array3 = [, , ,];
console.log(array3);


#00
if( -1 ) {
    console.log("true")
}
else {
    console.log("false")
}

#00
if("") {
  console.log("true")
}
else {
  console.log("false")
}

#00
if(" ") {
  console.log("true")
}
else {
  console.log("false")
}


#00



#00
var a=10;
console.log(a+=2);
console.log(a*=2);
console.log(a++);
console.log(++a);

#00
let data ={name:"anil",age:23};
console.log(delete data);

#00
// find the number and the number of occurrence
let arr=[1,1,2,3,1,4]
const count={}
for(const ele of arr){
    if(count[ele]){
        count[ele]+=1;
    }
    else{
        count[ele]=1;
    }
}
console.log(count);
```


## new add-

// array-
let x = ['alok', 'aman']
let name1= x[0];
let name2= x[1]
console.log(name1); 
console.log(name2); 
// array destr-
[name1,name2]=['alok','aman']
console.log(name1); 
console.log(name2); 

// object-
// I-
const student ={
    name:'alok',
    roll:2,
    sub:'math'
}
console.log(student.name);
console.log(student.roll);
console.log(student.sub);

// obj destr-
// const{roll,name,sub}= student ={
//     name:'alok',
//     roll:2,
//     sub:'math'
// }
// console.log(name);
// console.log(roll);
// console.log(sub);

//overloading in  obj destr-
// II-
const name='ram'
const{roll, name:fullName,sub}= student ={
    name:'alok',
    roll:2,
    sub:'math'
}
console.log(name);
console.log(fullName);

// III-
// const school={
//     one:{
//         english:'ram',
//         math:'sunil'
//     },
//     two:{
//      english:'ronak',
//         math:'alok'
//     }
// }
// console.log(school.one.english);

// des III-
const {one:{english,math},two:{english:englishTwo,math:mathTwo}}={
        one:{
            english:'ram',
            math:'sunil'
        },
        two:{
         english:'ronak',
            math:'alok'
        }
    }
    console.log(english);
    console.log(englishTwo);

// obj & arry des differ-
// obj key name same & array indexing is not changeable
// alias resolve dublicase problems


```

### Math-
```
console.log(Math);
console.log(Math.abs(-4));
console.log(Math.round(4.6));
console.log(Math.ceil(4.3));
console.log(Math.ceil(4.9));
console.log(Math.floor(4.3));
console.log(Math.floor(-4.7));
console.log(Math.floor(4.9));
console.log(Math.min(4,7,2,3));
console.log(Math.random())
```


