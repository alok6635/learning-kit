let person = {
     name:'alok',
     age:35,
     city:'kanpur'
 }


**# find key/values & using by entries**

```
@ keys,values-
let res = Object.keys(person)
let res = Object.values(person)
console.log(res)

@ Object.entries(return key & value array format)-
let res = Object.entries(person)
 let res1=res.flat()
 console.log(res1);

@ for in-
for(let key in person){
    console.log(` Key: ${key}  value: ${person[key]}`)
}
@ for of-
for (let [key,value] of Object.entries(person)){
    console.log(`Key: ${key} value: ${value}`);
}

```

let person = {
     name:'alok',
     age:35,
 }
 
**# key exists in object**

```
@ Using in operator-
console.log('name' in person);

@ hasOwnProperty-   
console.log(person.hasOwnProperty('age'));

@ using undefined comparison-
console.log(person.name !==undefined);
console.log(user.age !== undefined);
```

**# how many keys present in object**

```
  console.log(Object.keys(person).length);
```

**# how to check an empty object**

* Using Object entries.
* Using hasOwnProperty.
* Using Object keys.length

```
if(Object.keys(person).length===0){
    console.log("object is empty");
}
else{
    console.log("object is present value");
}
```

**# enumerable propery in object**
      
```
* if we want to hide a key then use it. and it set to enumerable(false).
Object.defineProperty(person,"age",{
    enumerable:false,
})
console.log(person);

* if we want to set a key then enumerable(true).
Object.defineProperty(person,'course',{
    enumerable:true, 
    value:'html'
})
console.log(person);
```

**# change the object key and value**

```
 let obj = {a:1,b:2,c:3}
 let newObj = {}
  for(let key in obj){
       newObj[obj[key]]=key;
  }
  console.log(newObj);
```

**# add the value of a object**

```
 let obj = {'0': 2, '1': 3, '2': 4};


 let sum = 0;
for (let item in obj) {
    if (obj.hasOwnProperty(item)) {
        sum += obj[item];
    }
}
console.log(sum);
```


**# Object.isExtensible()**

* method is used to determine if an object is extendable or not. i.e, Whether it can have new properties added to it or not.


**# Object.preventExtensions()**

* Object.preventExtensions() method is used to prevent new properties from ever being added to an object.but delete allow

**# object non-extensible in 3 ways**

```
Object.preventExtensions
Object.seal
Object.freeze
```

**# determine two values same or not using object**
Object.is() method determines whether two values are the same value
```
Object.is("hello", "hello"); // true
Object.is(window, window); // true
Object.is([], []); // false
```



**#  freeze & seal method**
* can not add & modified any property  on first level but nexted lavel allow.
* we can use freeze in array
```
let arr=[10,20,30,[40,90]]
Object.freeze(arr)

arr[3][2]=89
console.log(arr);

@@@ seal- only modify allow in first level. and next level add/delete/modify  .
```
**# How do you determine whether object is frozen or not 
```
const obj = {
  property: "Welcome JS world",
};
Object.freeze(obj);
console.log(Object.isFrozen(obj));
```

**# checking for seal**
* isSealed()
  
**# detect javascript disabled in the page**
<noscript></noscript>



**# define single property in object** 

* Object.defineProperty()- add a new key in object it is not editable
  
```
  var user = {
    firstName: "John",
    lastName: "Abraham",
}

Object.defineProperty(user,'language',{
    value:'en',
    writable: true,
})
user.language='franch'

 console.log(user);

```
**# Object.defineProperties() method**
*  used to define new or modify existing properties directly on an object and returning the object**
```
const newObject = {};

Object.defineProperties(newObject, {
  newProperty1: {
    value: "John",
    writable: true,
  },
  newProperty2: {},
});
```




**# determine two values same or not using object**
Object.is() method determines whether two values are the same value
```
Object.is("hello", "hello"); // true
Object.is(window, window); // true
Object.is([], []); // false
```



 **# Imp Point**
 
* if we set a key in prototype then it is not showing in these method(key,value,entries,hasOwnProperty).it is show for in loop.
```
    let person = {
    name:'alok',
    age:35,
    city:'kanpur'
}
Object.prototype.id= 200;

for(let key in person){
    console.log(key);
}

```


**#  freeze & seal method**
* can not add & modified any property  on first level but nexted lavel allow.
* we can use freeze in array
```
let arr=[10,20,30,[40,90]]
Object.freeze(arr)

arr[3][2]=89
console.log(arr);

@@@ seal- only modify allow in first level. and next level add/delete/modify  .
```
**# How do you determine whether object is frozen or not 
```
const obj = {
  property: "Welcome JS world",
};
Object.freeze(obj);
console.log(Object.isFrozen(obj));
```

**# checking for seal**
* isSealed()

**# define single property in object** 

* Object.defineProperty()- add a new key in object it is not editable
  
```
  var user = {
    firstName: "John",
    lastName: "Abraham",
}

Object.defineProperty(user,'language',{
    value:'en',
    writable: true,
})
user.language='franch'

 console.log(user);

```
**# Object.defineProperties() method**
*  used to define new or modify existing properties directly on an object and returning the object**
```
const newObject = {};

Object.defineProperties(newObject, {
  newProperty1: {
    value: "John",
    writable: true,
  },
  newProperty2: {},
});
```

**# What is a WeakSet ?**
**# What is a WeakMap ?**




