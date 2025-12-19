**var case**

```
** Global Scope-
var a = 10;
function test() {
  console.log(a); 
}
test();
console.log(a);

** Function Scope-
function test() {
  var x = 20;
  console.log(x);
}
test();
console.log(x); // ❌ ReferenceError

** No Block Scope-
if (true) {
  var y = 30;
}
console.log(y); //leaks outside block

** Re-declare & Re-assign-
var z = 10;
var z = 20; 
z = 30;
console.log(z);

**Hoisting-
console.log(a); 
var a = 5;

```

**let case**

```
**global scope-
let a = 10;
function test() {
  console.log(a); 
}
test();
console.log(a);

**function scope**
function test() {
  let x = 20;
  console.log(x);
}
test();
console.log(x)

**Block Scope-
if (true) {
  let a = 10;
  console.log(a);
}
console.log(a); // ❌ ReferenceError

** Re-assign Allowed-
let b = 20;
b = 30; // ✅ allowed

console.log(b); // 30

**Re-declare-
let c = 10;
let c = 20; // ❌ SyntaxError

**Hoisting (Temporal Dead Zone)-
console.log(d); // ❌ ReferenceError
let d = 40;

** Function Scope with let-

function test() {
  let x = 50;
  console.log(x); // ✅ 50
}

test();
console.log(x); // ❌ ReferenceError
```

**const case**

```
** Block Scope (const)-
if (true) {
  const a = 10;
  console.log(a); // ✅ 10
}
console.log(a); 

** Cannot Re-assign-
const y = 20;
y = 30; // ❌ TypeError


** Cannot Re-declare-
const z = 10;
const z = 20; // ❌ SyntaxError

```


```
@@@ scopes-
@ var- global & functional
var x=5;
function abc(){
    var a=10;
    if(1){
        var a=20;
         console.log(a)
    }
    console.log(x)
}
abc();

@let- global & block 
let x=5;
function abc(){
    let a=10;
    if(1){
        let a=20;
         console.log(a)
    }
    console.log(x)
}
abc();

@@@ hoisting-
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

@@@ re-declaration-
@var-
var a =10;
var a =20;
console.log(a)

@let-
let a =10;
let a =20;
console.log(a)

@@@ re-assignment-
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


