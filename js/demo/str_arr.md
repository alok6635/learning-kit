
```
* spread
let str = "kittu"
let arr=[...str]
console.log(arr);

* split
 let str = "kittu"
 let arr= str.split('')
 console.log(arr);

*  Array.from
 let str = "kittu";
let arr = Array.from(str)
console.log(arr);

* reduce
let str = 'kittu';
let arr = Array.from(str).reduce((accumulator, current, index) => {
  return [...accumulator, current];
},[]);
console.log(arr);

* forEach
let str='kittu'
let arr=[]
str.split('').forEach((item)=>{
arr.push(item)
})
console.log(arr);

* for of loop
let str='kittu'
let arr=[]
for(let item of str){
    arr.push(item)
}
console.log(arr);

* for in loop
let str = "kittu";
 let arr=[];
 for (key in str){
   arr[key]=str[key]
 }
 console.log(arr);
 console.log(typeof (arr));

 * for loop
let str="kittu";
let arr=[]
 for(let i=0;i<str.length;i++){
 arr[i]=str[i]
 }
 console.log(arr);

```

