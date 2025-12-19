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


