
**# remove duplicate characters from string. & return duplicate character of string.**
```
* remove duplicate-
let res=str.split('').filter((item,index,arr)=>{
  return arr.indexOf(item) ==index;
})
console.log(res);

* return duplicate
let res= str.split('').filter((item,index,arr)=>{
         return arr.indexOf(item) !== index
})
console.log(res);
``` 

**# replace a word in string**

```
let res= str.replace('red','blue')
console.log(res);

* it is change only same word then using RexExp-
let str= 'pen is red and pencil is a Red'
let reg= new RegExp('red','gi')
let newStr= str.replace(reg,'blue')
console.log(newStr);

* for loop-
given a string and replaced red - blue

let str = 'pen is red';
let newStr = '';
let wordToReplace = 'red';
let replacementWord = 'blue';

let words = str.split(' ');
for (let i=0; i < words.length; i++) {
  if (words[i] === wordToReplace) {
    newStr += replacementWord;
  } else {
    newStr += words[i];
  }
  if (i < words.length - 1) {
    newStr += ' ';
  }
}
console.log(newStr);
```
  
**# Palindrome**
  
```
* I-
  let str = "alok"
  let str = "noon"
  let cleanStr= str.replace(/[^a-zA-Z0-9]/g,'').toLowerCase();
  let reversedStr= cleanStr.split('').reverse().join('');
  console.log(reversedStr);

* II-
function isPalindrome(str) {
    const cleanStr = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();
    const reversedStr = cleanStr.split('').reverse().join('');
    return cleanStr === reversedStr;
  }
  const inputString1 = "racecar";
  const inputString2 = "hello";
  console.log(isPalindrome(inputString1)); 
  console.log(isPalindrome(inputString2)); 
```

**# check anagrams string**

```
function verifyAnagrams(word1, word2) {
  return word1.split("").sort().join("") === word2.split("").sort().join("")
}
console.log(verifyAnagrams("eat", "ate"))
```

**# replace white space in string**
```
let str = ' my name is ashish '
let res =str.replace(/\s/g,'')
console.log(res)
```
**# count string character**
  
```
let  obj={};
for(let item of str){
   if(obj[item]){
    obj[item]=obj[item]+1;
   }
   else{
    obj[item]=1
   }
}
console.log(obj);
```

**# match above**


**# reverse string**
   
```
##
let str = 'alok kumar';
let result = str.split('').reverse().join('');
console.log(result);

## for loop-
let revStr = '';
for (let i = str.length - 1; i >= 0; i--) {
    revStr = revStr + str[i];
}
console.log(revStr);

## reverse each character in the string without blank comma-
let str = 'alok yadav';
let result = str.split('').reverse().filter((item)=>item !== ' ').join('');
let final= result.slice(0,5) + " " + result.slice(5, 9);
console.log(result);
console.log(final);

## spical character-
let cleanStr= str.replace(/[^a-zA-Z0-9]/g,'').toLowerCase();
let reversedStr= cleanStr.split('').reverse().join('');
console.log(reversedStr);

```

**# palindrome string**
  
```
* I-
function isPalindrome(str) {
    const cleanStr = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();
    const reversedStr = cleanStr.split('').reverse().join('');
    return cleanStr === reversedStr;
  }
  const inputString1 = "naman";
  const inputString2 = "hello";
  console.log(isPalindrome(inputString1)); 
  console.log(isPalindrome(inputString2)); 

* II-
function isPalindrome(str) {
    const len = str.length;
    for (let i = 0; i < len / 2; i++) {
      if (str[i] !== str[len - 1 - i]) {
        return false; 
      }
    }
    return true; 
  }
  
  const word = "naman";
  if (isPalindrome(word)) {
    console.log(`${word} is a palindrome`);
  } else {
    console.log(`${word} is not a palindrome`);
  }
```
  

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
**# a string starts with another string**

```
let str = "Good morning";
let res = str.startsWith('Good');
console.log(res);
let res1 = str.startsWith('morning');
console.log(res1);
```
**# check a string contains a substring**

```
@ includes-
let str = 'hello'
let subStr= 'hell'
let res= str.includes(subStr)
console.log(res);

@ indexOf-
let str = 'hello'
let subStr= 'man'
let res= str.indexOf(subStr) !==-1
console.log(res);

@ Using RegEx-
let str = 'hello'
regex= /hell/
let res= regex.test(str)
console.log(res);
```

**# remove duplicate characters from a string.& return duplicate character of string**
```
* remove duplicate-
let str =  'priya riya supriya'
let res=str.split('').filter((item,index,arr)=>{
  return arr.indexOf(item) ==index;
})
console.log(res);

@ for loop-
let str =  'priya riya supriya'
let res = [];
for (let i = 0; i < str.length; i++) {
    if (res.indexOf(str[i]) === -1) { 
        res.push(str[i]);
    }
}
console.log(res);


* return duplicate
let str =  'priya riya supriya'
let res= str.split('').filter((item,index,arr)=>{
         return arr.indexOf(item) !== index
})
console.log(res);

@@@ for loop-
let str =  'priya riya supriya'
let res = [];
let seen = [];

for (let i = 0; i < str.length; i++) {
    if (seen.indexOf(str[i]) === -1) {
        seen.push(str[i]);
    } else {
        if (res.indexOf(str[i]) === -1) {
            res.push(str[i]);
        }
    }
}
console.log(res);

``` 

**# replace a word in string**

```
let str = 'pen is red and pencil is a Red'
let res= str.replace('red','blue')
console.log(res);

* it is change only same word then using RexExp-
let str= 'pen is red and pencil is a Red'
let reg= new RegExp('red','gi')
let newStr= str.replace(reg,'blue')
console.log(newStr);

* for loop-
given a string and replaced red - blue

let str = 'pen is red';
let newStr = '';
let wordToReplace = 'red';
let replacementWord = 'blue';

let words = str.split(' ');
for (let i=0; i < words.length; i++) {
  if (words[i] === wordToReplace) {
    newStr += replacementWord;
  } else {
    newStr += words[i];
  }
  if (i < words.length - 1) {
    newStr += ' ';
  }
}
console.log(newStr);
```
  


**# check anagrams string**

```
function verifyAnagrams(word1, word2) {
  return word1.split("").sort().join("") === word2.split("").sort().join("")
}
console.log(verifyAnagrams("eat", "ate"))
```

**# create specific number of copies of a string**
```
"Hello".repeat(4)
```

**# replace white space in string**
```
let str = ' my name is ashish '
let res =str.replace(/\s/g,'')
console.log(res)
```
**# count string character**
  
```
let  obj={};
for(let item of str){
   if(obj[item]){
    obj[item]=obj[item]+1;
   }
   else{
    obj[item]=1
   }
}
console.log(obj);
```

**# find vowel & consonent in a string**

```
let str = "Good morning";
let vowels = [];
let consonants = [];
for (let i = 0; i < str.length; i++) {
    let char = str[i].toLowerCase(); 
        if ('aeiou'.includes(char)) {
            vowels.push(char);
        } else {
            consonants.push(char);
        }
}
console.log('Vowels:', vowels);
console.log('Consonants:', consonants);
```


**# What are the string methods available in Regular expression**
  * Regular Expressions has two string methods: search() and replace().
  
```
@@@ search-
var str = "Hello John";
var n = str.search(/John/i); 
console.log(res)

@@@ replace-
var str = "Hello John";
var res = str.replace(/John/i, "alok")
console.log(res)
```











**# reverse string**
   
```
##
let str = 'alok kumar';
let result = str.split('').reverse().join('');
console.log(result);

## for loop-
let revStr = '';
for (let i = str.length - 1; i >= 0; i--) {
    revStr = revStr + str[i];
}
console.log(revStr);

## reverse each character in the string without blank comma-
let str = 'alok yadav';
let result = str.split('').reverse().filter((item)=>item !== ' ').join('');
let final= result.slice(0,5) + " " + result.slice(5, 9);
console.log(result);
console.log(final);

## spical character-
let cleanStr= str.replace(/[^a-zA-Z0-9]/g,'').toLowerCase();
let reversedStr= cleanStr.split('').reverse().join('');
console.log(reversedStr);

```

**# palindrome string**
  
```
* I-
function isPalindrome(str) {
    const cleanStr = str.replace(/[^a-zA-Z0-9]/g, '').toLowerCase();
    const reversedStr = cleanStr.split('').reverse().join('');
    return cleanStr === reversedStr;
  }
  const inputString1 = "naman";
  const inputString2 = "hello";
  console.log(isPalindrome(inputString1)); 
  console.log(isPalindrome(inputString2)); 

* II-
function isPalindrome(str) {
    const len = str.length;
    for (let i = 0; i < len / 2; i++) {
      if (str[i] !== str[len - 1 - i]) {
        return false; 
      }
    }
    return true; 
  }
  
  const word = "naman";
  if (isPalindrome(word)) {
    console.log(`${word} is a palindrome`);
  } else {
    console.log(`${word} is not a palindrome`);
  }
```
  

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
**# a string starts with another string**

```
let str = "Good morning";
let res = str.startsWith('Good');
console.log(res);
let res1 = str.startsWith('morning');
console.log(res1);
```
**# check a string contains a substring**

```
@ includes-
let str = 'hello'
let subStr= 'hell'
let res= str.includes(subStr)
console.log(res);

@ indexOf-
let str = 'hello'
let subStr= 'man'
let res= str.indexOf(subStr) !==-1
console.log(res);

@ Using RegEx-
let str = 'hello'
regex= /hell/
let res= regex.test(str)
console.log(res);
```

**# remove duplicate characters from a string.& return duplicate character of string**
```
* remove duplicate-
let str =  'priya riya supriya'
let res=str.split('').filter((item,index,arr)=>{
  return arr.indexOf(item) ==index;
})
console.log(res);

@ for loop-
let str =  'priya riya supriya'
let res = [];
for (let i = 0; i < str.length; i++) {
    if (res.indexOf(str[i]) === -1) { 
        res.push(str[i]);
    }
}
console.log(res);


* return duplicate
let str =  'priya riya supriya'
let res= str.split('').filter((item,index,arr)=>{
         return arr.indexOf(item) !== index
})
console.log(res);

@@@ for loop-
let str =  'priya riya supriya'
let res = [];
let seen = [];

for (let i = 0; i < str.length; i++) {
    if (seen.indexOf(str[i]) === -1) {
        seen.push(str[i]);
    } else {
        if (res.indexOf(str[i]) === -1) {
            res.push(str[i]);
        }
    }
}
console.log(res);

``` 

**# replace a word in string**

```
let str = 'pen is red and pencil is a Red'
let res= str.replace('red','blue')
console.log(res);

* it is change only same word then using RexExp-
let str= 'pen is red and pencil is a Red'
let reg= new RegExp('red','gi')
let newStr= str.replace(reg,'blue')
console.log(newStr);

* for loop-
given a string and replaced red - blue

let str = 'pen is red';
let newStr = '';
let wordToReplace = 'red';
let replacementWord = 'blue';

let words = str.split(' ');
for (let i=0; i < words.length; i++) {
  if (words[i] === wordToReplace) {
    newStr += replacementWord;
  } else {
    newStr += words[i];
  }
  if (i < words.length - 1) {
    newStr += ' ';
  }
}
console.log(newStr);
```
  


**# check anagrams string**

```
function verifyAnagrams(word1, word2) {
  return word1.split("").sort().join("") === word2.split("").sort().join("")
}
console.log(verifyAnagrams("eat", "ate"))
```

**# create specific number of copies of a string**
```
"Hello".repeat(4)
```

**# replace white space in string**
```
let str = ' my name is ashish '
let res =str.replace(/\s/g,'')
console.log(res)
```
**# count string character**
  
```
let  obj={};
for(let item of str){
   if(obj[item]){
    obj[item]=obj[item]+1;
   }
   else{
    obj[item]=1
   }
}
console.log(obj);
```

**# find vowel & consonent in a string**

```
let str = "Good morning";
let vowels = [];
let consonants = [];
for (let i = 0; i < str.length; i++) {
    let char = str[i].toLowerCase(); 
        if ('aeiou'.includes(char)) {
            vowels.push(char);
        } else {
            consonants.push(char);
        }
}
console.log('Vowels:', vowels);
console.log('Consonants:', consonants);
```


**# What are the string methods available in Regular expression**
  * Regular Expressions has two string methods: search() and replace().
  
```
@@@ search-
var str = "Hello John";
var n = str.search(/John/i); 
console.log(res)

@@@ replace-
var str = "Hello John";
var res = str.replace(/John/i, "alok")
console.log(res)
```






