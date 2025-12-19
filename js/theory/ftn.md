**# functional programing benifit**

* more concise, easy to debug, test, resuablity the code.

**# function arguments**

```
@ passsed a single argument & single parameter

function add1(userName){
  return `${userName} just Logged in`
}
console.log(add1('js'))

 @ when pass a blank string in argument

function add1(userName){
  return `${userName} just Logged in`
}
console.log(add1(''));

 @ when passed a blank argument

function add1(userName){
  return `${userName} just Logged in`
}
console.log(add1())
```

**# passed differnt type data in argument in a function**

```
@I
function add(num1,num2){
  console.log(num1+num2) 
 }
console.log(add(5,"a"));

@II
function add(num1,num2){
  console.log(num1+num2) 
 }
console.log(add(5,null));

```

**# function return v/s console**

```
@return
function  add1(num1,num2){
    return num1+num2;
  }
   console.log(add1(4,3)) 
  let res = add1(4,3)
  console.log('Res', res)

@ console
 function  add1(num1,num2){
    console.log(num1+num2)
  }
   add1(4,3)
  let res = add1(4,3)
  console.log('Res', res);
   
```

**# types of functions**

  * named (normal) function
  * IIFE
  * callback
  * high order
  * function expression
  * anonymous function
    
```
create a function without name is called anonymous ftn.
I
let  show = function(name){
    console.log(name);
}
show('alok')
II
anynomus normal ftn-
document.addEventListener('click', function(){
    console.log("clicked ..")
});
anynomus normal arrow-
document.addEventListener('click', () => console.log(" arrow clicked"));
```

* arrow function
    
```
@ Implict return (single line return)-
let sayAB = (a,b) => a+b;
let sayAB = (a,b) => (a+b); //same  result
let sayAB = (a,b) => {return a+b}; 
console.log(sayAB(9,3));
Note- a+b ko curly braces me wrap kiya to return likhna padega parenthasis me nhi likhna pdega
```

* function constructor-
  
```
 function Person(name, age) {
     this.name = name;
     this.age = age;
     this.greet = function() {
       console.log(`Hello, my name is ${this.name} and I'm ${this.age} years old.`);
     };
   }
let person1 = new Person("alok", 32);
  let person2 = new Person("alkittuok", 12);
 person1.greet()
 person2.greet()
 
```

* function is the object in the java script. many property exit in the function (name,lenght,call,apply,bind)
  
```
function say(name){
    return name
} 
say('alok')
console.log(say.name)
console.log(say.length)

```
* we can add a self created property in the function
```
function say(name){
    return name
} 
console.log(say.age=20 ) 
```


**# NFE (named function expression) or recusion**
```
let sayHello = function fx(user){
    if(user){
        return "hello" + user
    }
    else{
        return fx('recusion')
    }
}

let sayHi = sayHello
sayHello= null;
console.log(sayHi())
```

** note - function ko modified krne k liye decorator pattren(memoization) use krte hai.





