# sum of array & average
  
**for loop**
 
```
let arr= [1,2,3,4,5];
let sum =0;
for(let i=0;i<arr.length;i++){
     sum = sum + arr[i]
}
console.log(sum);

### average-
let average = sum/ arr.length
console.log(average);
```

**for of loop**
```
for(let value of arr){
  sum = sum+ value    
}
console.log(sum)
```

**for in loop**

```
for (let value in arr) {
    sum = sum + arr[value]; 
}
console.log(sum); 
```

**reduce**

```
let arr = [1,2,3,4,5]
let sum = arr.reduce((acc,current)=> acc+ current,0)
console.log(sum);
```

**forEach**

```
let arr = [1, 2, 3, 4, 5];
let sum = 0;
arr.forEach((item) => {
  sum = sum + item;
});
console.log( sum);
```

**map**

```
let arr = [1, 2, 3, 4, 5];
let sum = 0;
arr.map((item) => {
  sum = sum + item;
});
console.log( sum);
```

**create a function**

```
function sum(arr){
    let sum=0;
    for(let i=0;i<arr.length;i++){
       sum = sum+arr[i]
    }
    return sum;
}
console.log(sum(arr));
```

# find even& odd count in  array-

```
let evenNum = [];
let oddNum = [];
for (let i = 0; i < arr.length; i++) {
    if (arr[i] % 2 === 0) {
        evenNum.push(arr[i]);
    } else {
        oddNum.push(arr[i]);
    }
}
console.log("Even numbers:", evenNum, "Count:", evenNum.length);
console.log("Odd numbers:", oddNum, "Count:", oddNum.length);
```

# biggest & smallest number of array-

```
let arr = [18, 22, 43, 2,41, 19];

## built in-
### Math()-
let Largest = Math.max(...arr)
let Smallest = Math.min(...arr)
console.log(Largest);
console.log(Smallest);

### sort()-
arr.sort((a, b) => a - b);
console.log('Smallest:', arr[0]);
console.log('Largest:', arr[arr.length - 1]);

## reduce-
let biggest = arr.reduce((max, num) => (num > max ? num : max), arr[0]);
let smallest = arr.reduce((min, num) => (num < min ? num : min), arr[0]);
console.log("Biggest:", biggest);
console.log("Smallest:", smallest);

## for loop-
let max= arr[0]
for(let i=0;i<arr.length;i++){
   if(max<arr[i]){
    max=arr[i]
   } 
}
console.log(max);
let min=arr[0]
for(let i=0; i<arr.length;i++){
    if(min>arr[i]){
        min=arr[i]
    }
}
console.log(min);

## for of loop-
let biggest = arr[0];
let smallest = arr[0];

for (let num of arr) {
    if (num > biggest) {
        biggest = num;
    }
    if (num < smallest) {
        smallest = num;
    }
}

console.log("Biggest number:", biggest);
console.log("Smallest number:", smallest);
```

**# find missing number in array**

```
let arr = [1, 2, 3, 5];
let count = 10;
let newArr = [];
for (let i = 1; i < count; i++) {
  if (!arr.includes(i)) {
    newArr.push(i);
  }
}
console.log(newArr);
```

**# remove dublicate element & then sort by using set & for loop**

```
let arr=[1,10,3,11,4,3,5,7,9,4,5] & ['mukesh','aman','rahul','ram','aman']
* output-[1,10,3,11,4,5,7,9]
* sorting-
* output-[1,3,4,5,7,9,10,11]
* find whoes element is dublicate in the array-
* output-[3,4,5]
```

 **# copied the next all element in array**


```
let arr=[10,20,30,20,10,40];
let duplicatedArr=[];
for (let i=0;i<arr.length;i++){
  duplicatedArr.push(arr[i],arr[i]);
}
console.log(duplicatedArr);

```

**# given the two array add arr1 index and arr2 index**

```
let arr1=[1,2,3,4,5,6]
let arr2=[2,3,4,]
let newArr=[]
for(let i=0;i<arr1.length;i++){
    if(arr2[i]){
        newArr.push(arr2[i]+arr1[i])
    }
else{
    newArr.push(arr1[i])
}
}
console.log(newArr);
```
**# remove falsy values from an array**

```
* for loop
let arr=[1,10,3,11,4,3,5,7,9,4,5]
let obj={}
for(let i=0;i<arr.length;i++){
   if(obj[arr[i]]){
    (obj[arr[i]])=(obj[arr[i]])+1
   }
   else{
    (obj[arr[i]])=1
   }
}
console.log(obj);
* for each
arr.forEach((item)=>{
    if(obj[item]){
    obj[item]= obj[item]+1
    }
    else{
    obj[item]=1
    }
})
console.log(obj);
* for of
for(let item of arr){
    if(obj[item]){
        obj[item]=obj[item]+1
    }
    else{
        obj[item]=1
    }
}
console.log(obj);
```


**#  given a array of object find whoes rollnumber is 100. & add firstName & lastName key and add the main object.**

* Sort()- logic behind sort check return value negative,zero,positive

```
@@@ find dublicate by set & then sort -
let res = new Set(arr)
let data =Array.from(res)
let finalSort=data.sort((a,b)=>(a-b)-(b-a))
console.log(finalSort);

@@@ find dublicate & sort then by for loop-

* dublicate by indexOf-
let arr=[1,10,3,11,4,3,5,7,9,4,5]
let newArr=[]
for(let i=0;i<arr.length;i++){
  if(newArr.indexOf(arr[i])===-1){
    newArr.push(arr[i])
  }
}
console.log(newArr);

* dublicate by includes-
// for (let i = 0; i < arr.length; i++) {
//   if (!newArr.includes(arr[i])) {
//     newArr.push(arr[i]);
//   }
// }
// console.log(newArr)

@@@ sorting-
   for(let i=0;i<newArr.length-1;i++){
    for (let j=0;j<newArr.length-1;j++){
        if(newArr[j]>newArr[j+1]){
          let  temp=newArr[j]
            newArr[j]=newArr[j+1]
              newArr[j+1]=temp;
        }
    }
   }
   console.log(newArr);

@@@  whoes element is dublicate in the array
let arr=[1,10,3,11,4,3,5,7,9,4,5]
* filter-
let result= arr.filter((val,index,self)=>{
return  self.indexOf(val) !== index;
})
  console.log(result);

*for loop-
 let findDuplicates = (arr) => {
  let duplicates = [];
  let seen = {};
  for (let i = 0; i < arr.length; i++) {
    const element = arr[i];
    if (seen[element]) {
      duplicates.push(element);
    } else {
      seen[element] = true;
    }
  }
  return duplicates;
}

```

**# given a array of object and find problem**

```
## do the user name first letter is capital in array format-
* map-
let res=user.map((item)=>item.name.charAt(0).toUpperCase()+ item.name.slice(1))
console.log(res);
* foreach-
* for loop-

## find whoes user isActive and give me user name in array format-

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

## sort user by age desending-
* sort-
 let data=user.sort((a,b)=>a.age<b.age ? 1:-1)
 console.log(data);
* method chanining(filter & sort)-
const res=user.filter((item)=>item.isActive).sort((a,b)=>a.age<b.age ? 1:-1)
console.log(res);

## find position of developer-
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

**# find last number in threes value**

```
let newData=[]

for(let i=0;i<arr.length;i++){
    let updated=arr[i].split('-');
    newData.push(updated=updated[2])
}
console.log(newData);
```

**# synchronous iteration works**

```
let iterator =arr[Symbol.iterator]()
console.log(iterator.next());
console.log(iterator.next());
console.log(iterator.next());
```

**# fill a specific number in hole array (empty statement)**

```
let a = [50, 20 ,70, 60, 45, 30];
for (let i = 0; i < a.length; a[i++]=7);
console.log(a);
```

 **# given a array and looping the array and display the addition original property (chai & code)**
```
Array.prototype.extraProperty='alok'
let newArr=[1,2,3,4,5]
for(let item in newArr){
    console.log(item);
}

//hasOwnProperty not displayed the add protoptpes property-
for(let item in newArr){
    if(newArr.hasOwnProperty(item)){
        console.log(item);
    }
}
```

**# Count negative numbers in an array**

```
let arr = [2, -3, 5, -1, -7, 4];
let NegCount=0;
for (let i = 0; i < arr.length; i++) {
    if (arr[i] < 0) {
        NegCount++;
    }
}
console.log(NegCount);
```

**# Given an array let arr = [2, 3, 5, 2, 1, 7, 4] and search for a number (for    num = 5) and check whether it exists in the array or not ac**

```
let arr = [2, 3, 5, 2, 1, 7, 4];
let num =5
let exists = true;
for (let i = 0; i < arr.length; i++) {
  if (arr[i] === num) {
    exists = true;
    break; 
  }
}
if (exists) {
  console.log(`${num} exists in the array`);
} else {
  console.log(`${num} does not exist in the array`);
}
```

## STRING


**# check it is string or not**

```
let str = 1234;
function checkStr(str){
   if(typeof str ==='string'){
    console.log('it is string');
   }
   else if(typeof str=== 'number'){
    console.log('it is number');
   }
   
}
checkStr(str)

```
**# check if a string starts with another string.**

```
let res= str.startsWith('Good')
console.log(res);
let res1= str.startsWith("morning")
console.log(res1);
```
**# revere a string**
  
```
@@@ built-in method-

let res= str.split('').reverse().join('')
console.log(res);

@@@ for loop-
let newStr='';
for (let i=str.length-1;i>=0;i--){
  newStr+=str[i];
}
console.log(newStr);

@@@  reverse each character  in the string without blank comma-
let str = 'alok yadav';
let result = str.split('').reverse().filter((item)=>item !== ' ').join('')
let final= result.slice(0,5) + " " + result.slice(5, 9)
console.log(result);
console.log(final);
```

