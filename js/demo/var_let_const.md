**scopes**

```
@@@ var- (functional scope) 
 function abc() {
console.log(count);
    if (true) {
        var count = 10;
        console.log(count);
    }
    console.log(count);
}
abc();

@@@ let- (block scope) 
 function abc() {
console.log(count);
    if (true) {
        let count = 10;
        console.log(count);
    }
    console.log(count);
}
abc();

@@@ const- (block scope) 
 function abc() {
console.log(count);
    if (true) {
        const count = 10;
        console.log(count);
    }
    console.log(count);
}
abc();

@@@ Important function & block scope-
for(var i=1;i<=3;i++){
    setTimeout(()=>{
    console.log(i)
    },1000)
}
for(let i=1;i<=3;i++){
    setTimeout(()=>{
    console.log(i)
    },1000)
}
```


**re-assign**
```
@@@ var (do it)-
var a= 10;
 a= 20;
console.log(a);

@@@ let (do it)-
let a= 10;
 a= 20; 
console.log(a)
@@@ const (do not it)-
const a= 10;
 a= 20; 
console.log(a)

```

**re-declaration**

```
@@@ var (do it)-
var a =10;
var a =20;
console.log(a)

@@@ let (do not it)-
let a =10;
let a =20;
console.log(a)

@@@ const (do not it)-
const a =10;
const a =20;
console.log(a)
```
**hoisting**
```
@@@ var-
console.log(a);
var a =10;

@@@ let-
console.log(a);
let a =10;
```

** other ques-
let x= 'outer value';
(function(){
    console.log(x);
    let x= 'inner value'
}());


