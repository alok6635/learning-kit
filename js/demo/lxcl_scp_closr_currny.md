```
* lexical scope-

function outer() {
  let a = 10;
  function inner() {
     console.log(a + b);
  }
  let b = 20;
  inner()
}
outer()

* closure-

function outer(a){
   console.log(a)
  return  function inner(b){
   console.log(b);
     return a+b;
  }
}
let result=outer(10)
console.log(result(20));


* curring-

@@@ non-curried-
function sum(a,b,c){
    return a+b+c;
}
let res=sum(10,20,30)
console.log(res);

@@@ curring-

function curring(a){
    return (b)=>{
      return(c)=>{
     return a+b+c;
      }
    }
   }
   console.log(curring(1)(2)(3));
other-
   const sum1=curring(1)
   const sum2=sum1(2)
   const result=sum2(3)
   console.log(result);

```



```
@ curring in arrow function-
let add = a=> b=> c=> a+b+c;
console.log(add(1)(2)(3))
```


**# closer**

```
## problem-
function abc(){
    var count=0;
    count++;
    console.log(count);
}
abc();
abc();

## 
var count=0;
function abc(){
    count++;
    console.log(count);
}
abc()
abc()
```

## closer real life use case-
```
@ counter based-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@picocss/pico@2/css/pico.min.css">
    <script src="1.js"></script>
</head>


<body class="container">
    <div class="grid">
        <div>
            <button id="btn1" onclick="counter1()">BtnA</button>
        </div>
        <div>
            <button id="btn2" onclick="counter2()">BtnB</button>
        </div>
    </div>
   
<script>
    function initCounter(id) {
    let count = 0;
    return function () {
      count++;
      document.getElementById(id).innerText = count;
    };
  }
  let counter1 = initCounter('btn1');
  let counter2 = initCounter('btn2');
  
</script>
      
</body>
</html>

@ string based-
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@picocss/pico@2/css/pico.min.css">
    <script src="1.js"></script>
</head>

<body class="container">
    <input type="text" id="text1">
<button onclick="strAdder1()">Add String</button>
<p id="text-output1"></p>

<input type="text" id="text2">
<button onclick="strAdder2()">Add String</button>
<p id="text-output2"></p>

<script>
    function initAddString(inputId, outputId) {
    let str = '';
    return function () {
      str += ' ' + document.getElementById(inputId).value;
      document.getElementById(inputId).value = '';
      document.getElementById(outputId).innerText = str;
    };
  }
  
  let strAdder1 = initAddString('text1', 'text-output1');
  let strAdder2 = initAddString('text2', 'text-output2');
</script>
</body>
</html>
```

```
