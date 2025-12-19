```
@@@ Array-
let arr = [1, 2, 3, 4, 5];
const [a, b, ...rest] = arr;
console.log(b); 
console.log(a,b,rest);

@ using missing comma-

let arr = [1, 2, 3, 4, 5];
const [a, , , ...rest] = arr;
console.log(rest);

@ not possible-
let arr = [1, 2, 3, 4, 5];
const [a, ...rest,b] = arr;
console.log(arr);   

@ using alias-
let arr = [1, 2, 3, 4, 5];
const [a,name=b, ...rest] = arr;
console.log(a);  
console.log(name);   
console.log(...rest);

@@@ Object-
let person = {
    firstName: "John",
    lastName: "Doe",
    age: 30,
    country: "USA",
  };
  let {firstName,lastName, ...rest}=person;
  console.log(firstName);  
  console.log(lastName);   
  console.log(rest);

```
