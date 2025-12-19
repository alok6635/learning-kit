*  Normal functions ka this runtime pe decide hota hai (matlab jis context me function call hota hai, this waha se leta hai).
* Arrow functions me this lexically bound hota hai (matlab jo this function likhte waqt hota hai, wahi rahta hai).

```
## normal function-

function Person() {
  this.name = "Dost";
  
  setTimeout(function() {
    console.log(this.name); // ❌ Undefined, kyunki `this` yaha Window object ko refer kar raha hai!
  }, 1000);
}
new Person();

## arrow function-

function Person() {
  this.name = "Dost";
  
  setTimeout(() => {
    console.log(this.name); // ✅ "Dost" (Correct Output)
  }, 1000);
}
new Person();
```

* Arrow Functions Cannot be Used as Constructors-
  
```
## normal function-

function User(name) {
  this.name = name;
}
const user1 = new User("Dost");
console.log(user1.name); // ✅ "Dost"

## arrow function-

const User = (name) => {
  this.name = name;
};
const user1 = new User("Dost"); // ❌ Error: Arrow function cannot be used as a constructor
```

* No Arguments Object in Arrow Functions-
  
```

## normal function-

function showArgs() {
  console.log(arguments);
}
showArgs(1, 2, 3); // ✅ { '0': 1, '1': 2, '2': 3 }

## arrow function-

const showArgs = () => {
  console.log(arguments);
};
showArgs(1, 2, 3); // ❌ Error: arguments is not defined

```
old data- 

```
@ hoisting-
add(2,3)
const add =(a,b)=>{
   console.log(a+b);
    return a+b;
}

@ prototype-
normal function-
function add(a,b){
    console.log(a+b);
}
console.log(add.prototype)
arrow function-

const add1=(a,b)=>{
    console.log(a+b);
}
console.log(add1.prototype)

@ new keyword-
normal-
function add(a,b){
    console.log(a+b);
}
console.log(new add())
arrow-
const add1=(a,b)=>{
    console.log(a+b);
}
console.log(new add1())

@ own this-
let obj={
    name:'alok',
    normal:function(){
        console.log(`my name is ${this.name}`);
    },
    arrow:()=>{
        console.log(`my name is ${this.name}`);
    }
}
obj.normal();
obj.arrow();


@@@ called a object in a function-

* uses of this normal function-
let person={
    name:'alok',
    age:31
}
    function say(){
      return `${this.name} ${this.age}`
    }
    console.log(say.call(person));

* uses of this arrow function-
var name='kittu';
var age=23;
let person={
    name:'alok',
    age:31
    }
 const say=()=>{
   return`${this.name} ${this.age}`
}
console.log(say.call(person));

** ticky point- change result in arrow function- do the let
let name='kittu'; 
let age=2


@@@ called a method in a object-
  
* uses of this normal function-
       let person={
           name:'alok',
           age:31,
           say:function(){
            return ` ${this.name} & ${this.age}` 
           }
        }
      console.log(person.say())

* uses of this arrow function-
var name='kittu'; 
var age=2;
let person={
   name:'alok',
   age:31,
   say :()=>{
       return`${this.name} ${this.age}`
   }
 }
 console.log(person.say());

** ticky point- change result in arrow function- do the let
let name='kittu'; 
let age=2;
  
@@@ uses of argument in function-
  
* normal function-
function add() {
  console.log(arguments);
}
console.log(add(1, 2, 3, 4, 5));

* arrow  function-
const add = () => {
  console.log(arguments);
};
console.log(add(1, 2, 3, 4, 5)); // result undefined

* Imp point -
* I-
function myFun(){
console.log(this);
}
myFun()

function myFun(){
    'use strict'
console.log(this);
}
myFun()

* II-
const myFun=()=>{
console.log(this);
}
myFun()

const myFun=()=>{
    'use strict'
console.log(this);
}
myFun()

* III-
const user= {
    name:'alok',
    age:32,
    about:function(){
       return `${this.name}  & ${this.age}`
    }
 }
 console.log(user.about());
 let myFun=user.about
 console.log(myFun());// undefined undefined
 const myFun=user.about.bind(user)
 console.log(myFun())

* IV-
let obj={ 
    name:'ashish',
    myfun(){
        console.log(this.name)
    }
    }
    let result=obj.myfun
    console.log(result());
```
