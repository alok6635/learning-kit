**scopes**

```
@@@ var- (functional scope) 
 function abc() {
    if (true) {
        var count = 10;
        console.log(count);
    }
    console.log(count);
}
abc();

@@@ let- (block scope) 
 function abc() {
    if (true) {
        let count = 10;
        console.log(count);
    }
    console.log(count);
}
abc();

@@@ const- (block scope) 
 function abc() {
    if (true) {
        let count = 10;
        console.log(count);
    }
    console.log(count);
}
abc();
```

**re-assignment**
```
@var-
var a= 10;
 a= 20;
console.log(a);
@let-
let a= 10;
 a= 20; 
console.log(a)
@cosnt-
const a= 10;
 a= 20;
console.log(a)

```

**re-declaration**
```
@var-
var a =10;
var a =20;
console.log(a)

@let-
let a =10;
let a =20;
console.log(a)


```
**hoisting**
```
@var-
console.log(a);
var a =10;

@let-
console.log(a);
let a =10;

@imp-
let x= 'outer value';
(function(){
    console.log(x);
    let x= 'inner value'
}());

```


