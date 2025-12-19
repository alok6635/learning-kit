 *  objects have a special property called prototype.
   
**# creating an method of object**

* using Object keyword  
    
```
let obj = Object()
obj.name='alok'
console.log(obj);
```

* Object literal 

```
let person={
     name:'alok',
    "hobbies":['coding','reading']
     show:function(){
        return this.name;
     }
  }
 console.log(person);
 console.log(person.show());

@ access Properties-
 dot Notation- console.log(person.name);
 bracket notation- console.log(person['hobbies'])
 Add extra property- person.color = 'red';
 Modified property- person.age=666;
 Delete Properties- delete person.id

@@@ Nested Objects-
     const person = {
    name :'alok',
    age:23,
    marks:{
        science:48,
        math:44,
    }
}
console.log(person.marks);
console.log(person.marks.math);

@@@ dynamic key-
const key = 'email';
const person ={
    name:'alok',
}
person[key]='alokyadav2757@gamil.com'
console.log(person);

```
    
* function constructor (using new keyword)

```
function Person(name,age){
 this.name=name;
 this.age=age
}
let person1= new Person('alok',12)
let person2= new Person('aman',1112)
console.log(person1,person2);
```
 
* factory function

```
function person(name,age){
    return {
        name: name,
        age: age
      };
}

let person1= person('alok',32)
let person2= person('kittu',2)
console.log(person1);
console.log(person2);
```

* creating by class
```
class person{
    constructor(name){
        this.name=name;
    }
show=()=>{
  return this.name;
}
}
let person1= new person('alok',26)
console.log(person1);
console.log(person1.show());
```

* object.create-
  * Object.create is a method that allows you to create a new object with a specified prototype object.
```
const obj1={
name: 'alok',
 age: 12,
 }
const obj2 = Object.create(obj1);
console.log(obj2);

@ check proto in object-
Object.getPrototypeOf()
console.log(Object.getPrototypeOf(obj2));

```

**# if createing the multiple users objects then following the apporach**

```
@@@   step-I (Object literal) it is very long process if creating multiple users objects.
const user1={
    firstName:'harshit',
    lastName:'kumar',
    email:'alokyadav6635@gmail.com',
    address:'new ashok nagar',
    about:function(){
        return `${this.firstName} is ${this.age}`
    },
    is18:function(){
        return this.age>=18;
    }

}

@@@   step-II  (about method is show to all users(user1,user2)
function user(name,age){
     let obj={}
     obj.name=name,
     obj.age=age,
     obj.about=function(){
          return `${this.name} & ${this.name}`
     }
     return obj;
}
let user1= user('alok',23,)
let user2= user('aman',3,)
console.log(user2);

@@@ step-III
const methodObj={
    about(){
    return `${this.name} & ${this.age}`
}
}
function user(name,age){
     let obj={}
     obj.name=name,
     obj.age=age;
     obj.about=methodObj.about;
     return obj;
}
let user1= user('alok',23,)
let user2= user('aman',3,)
   console.log(user1);
   console.log(user2);
   console.log(user1.about());

@@@ step-IV ( best approach using the proto or proto-chaining.)

const methodObj={
    about(){
    return `${this.name} & ${this.age}`
}
}
function user(name,age){
     let obj=Object.create(methodObj)
     obj.name=name,
     obj.age=age;
     return obj;
}
let user1= user('alok',23,)
let user2= user('aman',3,)
   console.log(user1);
   console.log(user2);
   console.log(user1.about());

@@@   step-V (using prototype)-

function user(name,age){
     let obj=Object.create(user.prototype)
     obj.name=name,
     obj.age=age;
     return obj;
}

user.prototype.about=function(){
     return` ${this.name} & ${this.age}`
}

let user1= user('alok',23,)
let user2= user('aman',3,)
   console.log(user1);
   console.log(user2);
   console.log(user1.about());

@@@ new Keyword-
* new keyword is used to create an instance of an object by calling the constructor method.

function CreateUser(fName,age){
    this.fName=fName;
    this.age=age
}

CreateUser.prototype.about=function(){
    return ` ${this.fName} & ${this.age}`
}

const user1= new CreateUser('alok',23)
const user2= new CreateUser('aman',13)
console.log(user1);
console.log(user2);
console.log(user1.about());

@@@ show  keys in prototypes-
for(let key in  user1){
    console.log(key);
}
@@@ not show key in prototypes-
for(let key in  user1){
    if(user1.hasOwnProperty(key)){
        console.log(key)
    }
}

```
* Prototype property is a simple object. where we can attach methods and properties in a prototype object.
  which enables all the other objects to inherit these methods and properties.

 **# Classes**
* a classes is a blueprint of an object. & class is a instance of object.
  
```
class CreateUser{
   constructor(fName,lName,age){
    this.fName=fName;
    this.lName=lName;
    this.age=age;
   }
   about(){
        return `${this.fName} & ${this.age}`
    }
}
const user1=  new CreateUser('alok','kumar',32)
const user2= new  CreateUser('kittu','kumar',2)
console.log(user1);
console.log(user2);
console.log(Object.getPrototypeOf(user1));
 ```

```
@@@ case-I

class Animal{
    constructor(name,age){
    this.name=name;
    this.age=age
    } 
    eat(){
            return `${this.name} is eating`
    }
    isAge(){
        return this.age<=10;
    }
}

class Dog extends Animal{
}
const tommy= new Dog('Tommy',3)
console.log(tommy);
console.log(tommy.isAge());


@@@ case-II
class Animal{
    constructor(name,age){
    this.name=name;
    this.age=age
    } 
    eat(){
            return `${this.name} is eating`
    }
}

class Dog extends Animal{
    constructor(name,age,speed){
        super(name,age);
        this.speed=speed;
    }
   run(){
        return ` ${this.name} is running ${this.speed} km/h`
    }
}
const tommy= new Dog('tommy',3,60)
const july= new Dog('july',13,40)
console.log(tommy);
console.log(july);
console.log(tommy.eat());
console.log(tommy.run());
```

**# setter & getter**
```
@@@ getter-
class Person{
    constructor(fName,lName,age){
     this.fName=fName;
     this.lName=lName;
     this.age=age;
    }
    get fullName(){
        return `${this.fName} & ${this.lName}`
    }
}

const person1=new Person('alok','kumar',29)
console.log(person1.fullName);

@@@ setter-
class Person{
    constructor(fName,lName,age){
     this.fName=fName;
     this.lName=lName;
     this.age=age;
    }
    get fullName(){
        return `${this.fName}  ${this.lName}`
    }
  set fullName(fullName){
    const[fName,lName]=fullName.split(' ')
    this.fName=fName
    this.lName-lName
}
}
const person1=new Person('alok','kumar',29);
person1.fullName='mohit kumar'
console.log(person1.fullName);
```

 *  object can only have 2 type of properties string & symbol.
 *  symbol is used for making hidden properties.
 *  for in loop ignore Symbol.
 *  also Object.keys() ignore  the symbol.
```
const  id = Symbol('id')
let person={
 name:'john',
 [id]:1
}
console.log(person[id])
```
