```
* spread-
let str = 'kittu';
let obj={...str}
console.log(obj);

* Object.assgin-
let str='kittu';
let obj=Object.assign({},str)
console.log(obj);

* for in
let str='kittu';
let obj={}
for(let key in str){
    obj[key]=str[key]
}
console.log(obj);

* for of
let str='kittu';
let obj={}
for(let [index,item] of str.split('').entries()){
    obj[index]=item
}
console.log(obj);

* for loop
let str='kittu';
let obj={};
for (let i=0;i<str.length;i++){
     obj[i]=str[i]
}
console.log(obj);

```
