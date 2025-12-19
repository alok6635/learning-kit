```
let arr=[10,20,30,40,50]
let [a,b,c,d,e]=arr;
console.log(a,b,c,d,e);
let arr1=[10,20,30,40,50,80]
let [a,b,,,,e]=arr1;
console.log(a,b,e);

@@@ object-
* I-
let perosn ={
    firstName:'alok',
    age:21,
}
let {firstName,age}=perosn;
console.log(firstName);
* II- concept of alias async-
let perosn ={
    firstName:'alok',
    lastName:'kumar',
    age:21,
}
let firstName ='kittu';
let {firstName:value,lastName,age}=perosn;
console.log(value);
console.log(lastName);

```