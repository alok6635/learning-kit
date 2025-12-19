* string is imutable. typeOf string is object.
  
```
let str = "Hello";
str[0] = "J";  
console.log(str); 

@ can do this type-
let str = "Hello";
let newStr = 'j' + str.slice(1)
console.log(newStr)
```
* strings method-

```
slice- it takes two parameter startIndex & endIndex.it can give a negative value.
split- it returns a array.
substring- cut a piece of string like a slice.take two parameter indexStart indexEnd.
trim- remove space before & after in string.
concat- add two strings latest use `${}` string interpolation
replace- replaced a character/word
include- return boolean value
uppercase & lowerCase

## Note-
     * reverse,join,splice method is array not string.
     * split is only use to string.
     * common method-concat,indexOf,length,Include,slice.
     * forEach works only in array not string.
```

* IndexOf-
     * returns the index of first occurence of the string.count start is 0.
```
let str = "alok kumar";
let res= str.indexOf('l')
let res= str.indexOf('k')
let res= str.indexOf('z')
console.log(res);
```

* last IndexOf- return last index.
```
let str = 'alok kumar'
let res= str.lastIndexOf('k')
console.log(res);
```
  
* charAt-
    * returns the character.count start is 0.
```
let str = 'alok yadav'
let res= str.charAt(3)
let res= str.charAt(30)
const res = str.charAt();//Without passing parameter in charAt()
console.log(res);
```
* charCodeAt-
   * returns an integer between 0 and 65535 representing the UTF-16 code unit at the given index.

```
const greeting = "Good morning";
let res= greeting.charCodeAt(9)
let res= greeting.charCodeAt(19)
let res= greeting.charCodeAt(-9)
console.log(res);
```
* slice
```
const str = "Hello, World";
const res = str.slice(1,9);
console.log(res);

* negative value-
let str = "Hello";
let res=str.slice(-4,3)
console.log(res);

```
* split
```
let str = 'alok yadav is a react developer';
let res = str.split(' ');
let res = str.split(' ',3);
console.log(res);
```
* trim
```
let str = "   alok kumar     "
let res= str.trim()
console.log(res);
```
* substring
```
const str= "alok kumar";
const res= str.substring(3,7)
console.log(res);
```
* uppercase
```
let str = "alok kumar"
console.log(str.toUpperCase());
```
* concat
```
let st1 = "Hello";
let st2 = "World";
let result = st1.concat(" ", st2);
let result = `${st1} ${st2}` //template literal
console.log(result);

* normally add-
const str1 = "alok";
const str2 = "kumar";
const newStr = str1+ " "+str2;
console.log(newStr);
```

* Include
```
const str = "Hello, World!";
console.log(str.includes("World"));
console.log(str.includes("foot"));
```

* replace
```
const str = "Hello World";
const newStr = str.replace("r", "p");
console.log(newStr);
```
**# regular expression**
* replace white space in string.
* use the regular expression /\s/g as the first argument.regular expression \s matches any whitespace character, and the g flag makes the replacement global, replacing all occurrences.
```
let str = ' my name is ashish '
let res =str.replace(/\s/g,'')
console.log(res)
```

**# some imp points**

* find the index-
```
let str = "kittu kumar"
console.log(str[0]);
console.log(str[5]);
let arr = [10,20,30,40,  ,60]
console.log(arr[0]);
console.log(arr[4]);
```

* backscape- remove / automtically.
```
let badString = 'you\'ve are a wrong';
console.log(badString);
 ```
* parseInt() Method
parseInt() parses a string and returns the first integer
```
let data= parseInt("34 45 66");
console.log(data)
let data2=parseInt("40 years");
console.log(data2)
let data3=parseInt("He was 40");
console.log(data3)
```
