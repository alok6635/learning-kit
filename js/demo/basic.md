**# print 1 to 20 number without loop**

```
function add(start,end){
   console.log(start)
   if(start < end){
      add(start+1,end)
   }
   return start
} 
add(1,100)
```

**# sum of nth number**

```
function sumNth(num){
    let sum =0;
    for(let i=0;i<=num;i++){
        sum=sum+i;
    }
    return sum;
}
let res=sumNth(20)
console.log(res)
```
**# factorial of 15**

```
function factorial(num){
    let res=1;
   for(let i=num;i>0;i--){
     res= res*i
   }
   console.log(res)
}
factorial(10)
```

**# factor  of 15**

```
function fact(num){
    let arr=[]
    for(let i=0;i<=num;i++){
        if(num % i ===0){
            arr.push(i)
        }
    }
    console.log(arr)
}
fact(15);
```

**# fibnocci series of 15**

```
let res =[0,1]
for(let i=2;i<15;i++){
    res.push(res[i-2]+res[i-1])
}
console.log(res)
```
**# add all arguments by for loop**
```
function add() {
    let res = 0; 
    for (let i = 0; i < arguments.length; i++) {
        res = res + arguments[i];  
    }
    console.log(res); 
}
add(2, 3, 4, 5, 6, 7);

@ other
// I-
function arg(...data){
    let sum=0
     data.forEach((item)=>{
        sum=sum+item
     })
  console.log(sum);
  }
arg(1,2,3,4,5,6,7,8,9)
// 2rd-
function arg(...data) {
    let sum = 0;
    for (let i = 0; i < data.length; i++) {
        sum += data[i];  
    }
    console.log(sum);
}
arg(1, 2, 3, 4, 5, 6, 7, 8, 9);
// 3rd-
function add(value) {
    let res = [...value];  
    let sum = 0;  
    for (let i = 0; i < res.length; i++) {
      sum += res[i];  
    }
    console.log(sum); 
  }
  let value = [1, 2, 3, 4, 5, 6, 7, 8, 9];
  add(value); 
  
```
**# prime numbers**

```
function prime(num) {
    if (num <= 1) return false; 
    for (let i = 2; i < num; i++) { 
        if (num % i === 0) {
            return false
        }
    }
    return true; 
}
console.log(prime(10)); 
console.log(prime(13));
```
**# square root of a number**
* square root of 25  is 5

```
@ Math.sqrt-
let num=25;
let res=Math.sqrt(num);
console.log(res);
@ other-
function squareRoot(num) {
    if (num < 0) return NaN; 
    for (let i = 0; i <= num; i++) {
        if (i * i === num) {
            return i; 
        }
        if (i * i > num) {
            return null;
        }
    }
}
console.log(squareRoot(25));  
console.log(squareRoot(16));  
console.log(squareRoot(10));

```

**# find biggest in two number**
* method- if,else,terinary, AND, OR
```
let num1=75757756789;
let num2=75757756889;

@ AND -
function bigNum(num1,num2){
    if(num1 > num2 && num2>num1 ){
     return num1 >num2 ? num1 :num2
    }
 }
 let res=bigNum(num1,num2)
 console.log(res);

@ OR-
function bigNum(num1,num2){
    if(num1 > num2 || num2>num1 ){
     return num1 >num2 ? num1 :num2
    }
 }
 let res=bigNum(num1,num2)
 console.log(res);
```

**# biggest in three number**

* AND, Math.max(),ternariry.
```
let num1=75757756789;
let num2=75757756989;
let num3=75757756889;

@ AND-

if (num1 > num2 && num1 > num3) {
    console.log("num1 is the largest: " + num1);
} else if (num2 > num1 && num2 > num3) {
    console.log("num2 is the largest: " + num2);
} else {
    console.log("num3 is the largest: " + num3);
}

@ OR-

if (num1 > num2 || num1 > num3) {
    console.log("num1 is the largest: " + num1);
} else if (num2 > num1 || num2 > num3) {
    console.log("num2 is the largest: " + num2);
} else {
    console.log("num3 is the largest: " + num3);
}

@ terniary-
let num1=75757756789;
let num2=75757756989;
let num3=75757756889;
let largest = (num1 > num2 && num1 > num3) ? num1 : (num2 > num1 && num2 > num3) ? num2 : num3;
console.log("The largest number is: " + largest);

```
