```
* object case-
* issue-
let obj1={
    name:"alok",
    age:21,
} 
obj2=obj1;
console.log(obj1);
console.log(obj2);
obj2.name='kittu';
console.log(obj1);
console.log(obj2);

* soluation shallow copy-
* spread-
let obj1={
    name:"alok",
    age:21,
} 
obj2={...obj1}
obj2.name='kittu'
console.log(obj2);
console.log(obj1);

* object.assign-
let obj1={
    name:"alok",
    age:21,
} 
obj2=Object.assign({},obj1) 
obj2.name='kittu'
console.log(obj2);
console.log(obj1);

* fallback of shallow copy- nexted object
let obj1 ={
   name:"alok",
   age:21,
   address:{
   city:"Kanpur",
   }
}
obj2=obj1;
obj1.address.city='lucknow'
console.log(obj1);
console.log(obj2);

* deep copy(soluation of shallow copy)-
let obj1 ={
    name:"alok",
    age:21,
    address:{
    city:"Kanpur",
    }
}
let obj2=JSON.parse(JSON.stringify(obj1))
obj2.address.city="lucknow";
console.log(obj1);
console.log(obj2);

@@@ array Case-

// issue-
let arr1=[10,20,30]
arr2=arr1
console.log(arr2);
console.log(arr1);
arr2[1]=50
console.log(arr2);
console.log(arr1);

// shallow copy-
let arr1=[10,20,30]
arr2=[...arr1]
arr2[1]=24
console.log(arr2);
console.log(arr1);

// fallback in shallow copy (nexted array)-
let arr1=[10,20,[40,50,22],30]
arr2=[...arr1]
arr2[2][0]=66
console.log(arr2);
console.log(arr1);

// deep copy-
let arr1=[10,20,[40,50,22],30]
arr2=JSON.parse(JSON.stringify(arr1))
arr2[2][0]=66
console.log(arr2);
console.log(arr1);
```

