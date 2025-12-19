**# Array**

**# copied the next all element in array**

```
let arr=[10,20,30,20,10,40]
output-[10,10,20,20,30,30,40,40]
```

**# given the two array add arr1 index and arr2 index**

```
let arr1=[1,2,3,4,5,6]
let arr2=[2,3,4,]
output-[3,5,7,4,5,6]
```

**# remove falsy values from an array**

```
const myArray = [false, null, 1, 5, undefined];
myArray.filter(Boolean); // [1, 5] // is same as myArray.filter(x => x);
```

**# given a array of object find whoes rollnumber is 100. & add firstName & lastName key and add the main object.**

```
 let student = [
    {firstName:'ashish',lastName:'yadav',rollNumber:100},
    {firstName:'alok',lastName:'singh',rollNumber:101},
    {firstName:'mukesh',lastName:'yadav',rollNumber:102}
]
```

**# given a array of object and find problems**

```
const user=[
    {id:9,name:'ajay',isActive:true,age:220,position: "developer"},
    {id:20,name:'alok',isActive:true,age:10,position: "teacher"},
    {id:13,name:'aman',isActive:false,age:30,position: "developer"},
    {id:8,name:'ankit',isActive:true,age:12,position: "student"},
]

* do the user name first letter is capital in array format.
* find whoes user isActive and give me user name in array format.
* sort user by age desending & used method chaining.
* find position of developer. 
```

**# find last number in threes value**

```
let arr=['13-34-55','32-12-23','45-67-10']
output-55,23,10

```

**# synchronous iteration works**

```
let arr=[10,20,30,40]
```

**# fill a specific number in hole array (empty statement)**


```
let a = [50, 20 ,70, 60, 45, 30];
output- [7,7,7,7,7,7]
```


 **# given a array and looping the array and display the addition original property (chai & code)**


 -------------------

<details>
<summary> array</summary>   

**# given a array of object and find problems**

* do the user name first letter is capital in array format.
```
* map-
let res=user.map((item)=>item.name.charAt(0).toUpperCase()+ item.name.slice(1))
console.log(res);
* foreach-
* for loop-
```

* find whoes user isActive and give me user name in array format.
```
* method chanining(filter & map)-
const res=user.filter((item)=>item.isActive).map((getActive)=>getActive.name)
console.log(res)

* for loop-
let arr=[]
for(let i=0;i<user.length;i++){
if(user[i].isActive){
   arr.push(user[i].name)
}
}
console.log(arr);

* foreach-
let arr=[]
user.forEach((item)=>{
if(item.isActive){
    arr.push(item.name)
}
})
console.log(arr);
```
* sort user by age desending-
  
```
* sort-
 let data=user.sort((a,b)=>a.age<b.age ? 1:-1)
 console.log(data);
* method chanining(filter & sort)-
const res=user.filter((item)=>item.isActive).sort((a,b)=>a.age<b.age ? 1:-1)
console.log(res)
```  

* find position of developer-
``` 
let res=user.filter((item)=> item.position=="developer")
console.log(res);
* for loop
let arr=[]
for(let i=0; i<user.length;i++){
if(user[i].position==='developer')
arr.push(user[i].name)
}
console.log(arr);
```

**# given a array of object find whoes rollnumber is 100. & add firstName & lastName key and add the main object.** 
```
  let student = [
    {firstName:'ashish',lastName:'yadav',rollNumber:100},
    {firstName:'alok',lastName:'singh',rollNumber:101},
    {firstName:'mukesh',lastName:'yadav',rollNumber:102}
]
let res=student.filter((item)=> item.rollNumber==100);
console.log(res);
let final=student.map((item)=>{
    item.fullName=item.firstName+item.lastName 
    return  item;
})
console.log(final);
```
</details>

