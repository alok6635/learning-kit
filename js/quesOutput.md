**# output types**

```
console.log(null>0);
console.log(null==0);
console.log(null>=0);
console.log(undefined== 0);
let data = Number('33abc')
console.log(typeof data);

let data = Number(null);
console.log(data);
console.log(typeof data);

let data = Number(undefined);
console.log(data);
console.log(typeof data);

let valueNum = Number(" ")
console.log(valueNum)
console.log(typeof valueNum);


let data = Number(true)
console.log(data);
console.log(typeof data);


let IsLogin = "alok";
let booleanIsLogin  = Boolean(IsLogin)
console.log(booleanIsLogin)

console.log(false - true);
console.log(!!"false");
console.log(!"");    
console.log(!!"");    
console.log(!!0);
console.log(!!1);
console.log(!!null);
console.log(!!undefined);
console.log(!!"false");
console.log(!!false);
console.log(!!true);


console.log(1 / 0);
console.log(0 || "hello");
console.log(1 || "world");
console.log(0 && "foo");
console.log(1 && "bar");

let a = {};
let b = { key: 'value' };
let c = { key: 'value' };
console.log(a[b] = 123);
console.log(a[c]);

let x = 10;
console.log(x++);
console.log(++x);

* Postfix increment-
let x = 3;
const y = x++;
console.log(x);
console.log(y);

* Prefix increment-
let x = 3;
const y = ++x;
console.log(y)
console.log(x)


var x = 4;
var y = x++;
y += 1;
console.log(y);


let num1=6;
let num2= num1;
num1++;
console.log('after increment :',num1);
console.log('after increment :',num2);

let age =24;
console.log(delete age);

const a = [1,2,3];
a.push(4);
Object.freeze(a);
a[0] = 10;
console.log(a[0]);

```
