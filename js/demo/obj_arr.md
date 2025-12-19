    
```
* Object method- 
let obj={
    name:"alok",
    age:23,
}
let arr =Object.keys(obj);
let arr2 =Object.entries(obj);
console.log(arr); 
console.log(arr2); 

* for in loop-
let arr=[]
for(let key in obj){
    arr.push(obj[key])
}
console.log(arr);

* for of loop-
let arr=[]
for(let [key,value] of Object.entries(obj)){
    arr.push(value)
}
console.log(arr);
```

