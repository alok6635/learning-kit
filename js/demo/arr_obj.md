```
let arr = [10,20,30,40]

@@@ spread-
let res= {...arr}
console.log(res);

@@@ array method-
* forEach-
 let obj={};
 arr.forEach((item,index)=>{
     obj[index]=item
 })
 console.log(obj)

* Array.entries with for of loop-
let obj={};
for(let [index,item] of arr.entries()){
    obj[index]=item
}
console.log(obj);

* reduce-
let obj={}
let res=arr.reduce((accu,current,index)=>{
      return{...accu,[index]:current}
},0)
console.log(res);

@@@ Object method-
* Object.assign()-
let res=Object.assign({},arr)
console.log(res);

* Object.entries with Object.fromEntries-
let res = Object.entries(arr) 
let data= Object.fromEntries(res)
console.log(data);

Imp note- Object.entries with Object.fromEntries- behavior is the same array & object-

@@@ for loop-
let obj={}
for(let i=0;i<arr.length;i++){
    obj[i]=arr[i]
}
console.log(obj);

@@@ for in loop-
let obj={};
for(let item in arr){
  obj[item]=arr[item]
}
console.log(obj);

@@@ for of loop-
let obj={}
let i=0;
for(let item of arr){
obj[i++]=item
}
console.log(obj);
```


