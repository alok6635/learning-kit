```
@ variable case
  @@ var-
console.log(a)
Var a =20;
  @@ let case-
console.log(a)
let a =20;

@ function case-
say(2,3)
function say(a,b){
    console.log(a+b)
}
 @@ curly brackets-
say(2,3)
{function say(a,b){
    console.log(a+b)
}}

  @@ variable case-
say(2,3)
var say= function(a,b){
    console.log(a+b)
}

  @@ arrow function-
say(2,3)
var say= (a,b)=>{
    console.log(a+b)
}
```
**# promise create & cosume**

```
## create-

  let promise= new Promise((resolve,rejected)=>{
     setTimeout(()=>{
        console.log('Promise initiated')
        // resolve({name:'alok',age:32})
        rejected({name:'kittu',age:12})
     }, 1000);
}) 
promise.then((resp)=>{
    console.log(resp);
})
.catch((err)=>{
    console.log(err);
})
.finally(()=>{
    console.log('request completed')
})

## consume-

fetch('https://jsonplaceholder.typicode.com/users')
.then((resp)=>resp.json())
.then((res)=>console.log(res))
.catch((err)=>console.log(err))
.finally(()=>console.log('request complete'))

@@@ get error-
fetch('https://jsonplaceholder.typicode.com/users')
.then((resp)=>resp.json())
.then((res)=>{
    console.log(res);
    throw new Error('custom error')
})
.catch((err)=>{
 console.log(err);
})
.finally(()=>console.log('request complete'))
```


**# promise all & allsettled & race & any**

```
## all passed-
let data= Promise.all([
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('2 sec');
        },2000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('1 sec');
        },3000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('4 sec');
        },4000);
    })
])
data.then((res)=>{
    console.log(res);
})
.catch((err)=>{
    console.log('catch block',err);
})
##if any one faild-

let data= Promise.all([
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('2 sec');
        },2000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            reject('1 sec');
        },3000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('4 sec');
        },4000);
    })
])
data.then((res)=>{
    console.log(res);
})
.catch((err)=>{
    console.log('catch block',err);
})

## promise allSettled-

	let data= Promise.allSettled([
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('2 sec');
        },2000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            reject('1 sec');
        },3000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('4 sec');
        },4000);
    })
])
data.then((res)=>{
    console.log(res);
})
.catch((err)=>{
    console.log('catch block',err);
})

##promise race-

let data= Promise.race([
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('2 sec');
        },2000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('1 sec');
        },5000);
    }),
    new Promise((resolve,reject)=>{
        setTimeout(() => {
            resolve('4 sec');
        },3000);
    })
])
data.then((res)=>{
    console.log(res);
})
.catch((err)=>{
    console.log('catch block',err);
})

```

**# async & awiat**

```
async function apiCall(){
    try{
        let data= await fetch('https://fakestoreapi.com/products')
        let res= await data.json()
        console.log('result', res);
    }
  catch(err){
    console.log(err);
  }
  document.getElementById('demo').style.background='red'
}
apiCall()
* do the wrong url and show the result div is properly work. 
```


**#  process.nextTick**

```
setTimeout(() => console.log('timeout'), 2000); // timer queue
setImmediate(() => console.log('immediate')); // check handler queue  register
process.nextTick(() => console.log('nextTick')); // call when call stack start 1-
new Promise((resolve,reject)=>{
 resolve('i am promice')
}).then((res)=>{
console.log(res);
})
console.log('norma js ');
```


**# throttling & throttling**


```
@@@ Step-I problem- when key continue press then result is fail.
<input type="text" onkeypress="debounceResult()">

function task(){
   console.log('function call');
}
function debounce(task,time){
    return function(){
        setTimeout(()=>{
            task()
        }, time);
    }
}
let debounceResult= debounce(task,2000)

@@@ step-II
<input type="text" onkeypress="debounceResult()">

function task(){
   console.log('function call');
}
function debounce(task,time){
    let timer;
    return function(){
     clearTimeout(timer)
      timer=  setTimeout(() => {
            task()
        }, time);
    }
}
let debounceResult= debounce(task,2000)
```



**# memoization**

```
@@@ using template literal-
function sum() {
    let obj = {};
    return function(a, b) {
       console.log(obj);
       if (!obj[`${a},${b}`]) {
          console.log('inside if');
          obj[`${a},${b}`] = a + b;
       }
       return obj[`${a},${b}`];
    };
 }
 
 let memozedSum = sum();
 console.log(memozedSum(3,4));
 console.log(memozedSum(3,4));

@@@ using without template literal-
function sum() {
   let obj = {};
   return function(a, b) {
      console.log(obj);
      let key = a + ',' + b;
      if (!obj[key]) {
         console.log('inside if');
         obj[key] = a + b;
      }
      return obj[key];
   };
}

let memozedSum = sum();
console.log(memozedSum(2, 5));
console.log(memozedSum(2, 5));

@@@@ thrid use
const sqrt = ()=>{
    let cache = {}
    return(n)=>{
        if(n in cache){
            console.log('Cache')
            return cache[n]
        }
        else{
            console.log('sqrt')
            let result = n*n
            cache[n]=result;
              return result
        }
    }
}
const obj = sqrt()
console.log(obj(5))
```

**# sets**

```
let set = new Set();
let obj1 = {name:'alok'};
let obj2 = {name:'aman'};
let obj3 = {name:'anish'};
set.add(obj1)
set.add(obj2)
set.add(obj3)
set.add(obj2)
set.add(obj3)
set.size;
set.keys();
set.values();
set.entries()
let r = [...set.keys()]
console.log(r);
```

**# Maps**

```
let map = new Map();
let person ={name:'alok'}
let perBalance ={balance:5000};
map.set('1','str1');
map.set(1,'num1');
map.set(true,'bool1');
map.set(person,perBalance);

map.get(1)
map.get('1')
map.get(true)
map.get(person);
map.size;
map.keys();
map.values();
map.entries();
map.has(1);
let x= [...map.keys()];
console.log(x)

## some other use case-

let obj={a:1,b:2,c:3}
let map = new Map(Object.entries(obj))
console.log(map)

let map = new Map();
map.set('a',1);
map.set('b',2);
map.set('c',3);
let obj = (Object.fromEntries(map.entries()))
console.log(obj)
```

**# Genaerator**

```
function *Genaerator(){
    yield 1;
    yield 2;
    yield 3;
    yield 4;

}
let data = Genaerator();
// console.log(...data); // itable 
console.log(data.next()); //itrator 
console.log(data.next());
console.log(data.next());
console.log(data.next());
console.log(data.next());

### other case-

```
function* genertorFunction(){
 yield 1;
 yield 2;
 yield 3;
} 
let genertor = genertorFunction();
console.log(genertor.next())
console.log(genertor.next())
console.log(genertor.next())

@ return case-
function* genertorFunction(){
 yield 1;
 yield 2;
 yield 3;
 return;
} 
let genertor = genertorFunction();
genertor.next();
genertor.next();
genertor.next();


@ genertor iterator to hai upr example me but genertor iterable bhi hota hai seen below ex-
function* genertorFunction(){
 yield 1;
 yield 2;
 yield 3;
} 
let genertor = genertorFunction();
console.log([...genertor])
genertor.next();
genertor.next();

@@@ other better example-
function* range(start,end){
     for(let value = start; value<= end; value++){
        yield value
     }
} 
let generator = range(1,5)

console.log([...generator])
```

```

**# iterables**

```
let iterable ={
    name:'alok',
    age:11,
    [Symbol.iterator](){
        return iterator
    }
}
@ already avaiable iterable-

let num =[1,2,3];
let it = num[Symbol.iterator]();
it.next();
it.next();
it.next();
 * array ek iterable hota hai. and array iterator return kr skta hai.
let num =[1,2,3];
let it=num[Symbol.iterator]();
console.log(it.next());
console.log(it.next());
* iterator is run to the on demand(next()). & iterable run in the loop.

```

* Ex- of iterator-
  
```
let iterator={
 i:0,
  next:function (){
        return { value: this.i, done:this.i++ >5};
  }
} 
```
** infinite iterable to ho nhi skta hai.
```
let num =[1,2,3];
let it = num[Symbol.iterator]();
it.next();
it.next();
it.next();

* but infinite iterator ho skta hai. 
 kyuki iterator next call pr value return krta hai aur last me infinite de dega. 
```


**# Prototypical inheritance**
```
let animal ={eats: true};
let dog = {barks: true};
dog.__proto__= animal;
console.log(dog.barks)
console.log(dog.eats)
```


**# configurations properties of Objects**

```
let obj ={property:32}
// console.log(obj)

Object.defineProperties(obj,{
    property:{
        value:32,
        writable:false,
        enumerable:true,
        configurable:true
    }
})
obj.property= 43
console.log(obj)
``` 
