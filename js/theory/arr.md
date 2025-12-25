


**Method of array**
  
* at-
  *  returns value of index. 
```
let arr=[6,11,18,10,12,16]
let res= arr.at(0)
console.log(res)
let res1= arr.at(-1)
console.log(res1)
```

* Indexof-
  * counting start always 0.if element is not present in the array it returns -1
  * if present the dublicate element in the array it gives first occurence.
    
```
let arr = [1,2,3,66,4,5,19]
console.log(arr.indexOf(66));
console.log(arr.indexOf(100));
```

* Array delete-
```
const fruits = ["Banana", "Orange", "Apple", "Mango"];
delete fruits[0];
```

* array Insert (push-last,ushift-first)-
```
push-
let city = ['kanpur','lucknow','agra']
let result = city.push('delhi',);
console.log(result);
console.log(city);

@ Imp-
let myHero = ['thor','shatiman', 'ratan']
let dcHero = ['raja','powerman', 'lal']
myHero.push(dcHero)
console.log(myHero)

unshift-
let city = ['kanpur','lucknow','agra']
let result = city.unshift('delhi','merad');
console.log(result);
console.log(city);
```

* array Remove (pop-last,shift-first)-
  
```
pop-
let city = ['kanpur','lucknow','agra','jhasi']
let result = city.pop('jhasi');
console.log(result);
console.log(city);

shift-
let city = ['kanpur','lucknow','agra']
let result = city.shift();
console.log(result);
console.log(city);
```
* map-
```
let arr= [1,2,3]
let res = arr.map((item)=>item*2)
console.log(res)
```
* filter-
```
let arr= [1,2,3]
let res = arr.filter((item)=>item >1)
console.log(res)
```
* find-
   * first value which condition return true.
```
let arr= [1,2,3].find((item)=>item ===1)
console.log(arr)
```
* findIndex-
   * first index for which condition return true. 
```
let arr= [1,2,3].findIndex((item)=>item ===2)
console.log(arr)
```
* every-
  * even if 1 element don't satisfied the condition we get false.
    
```  
let arr= [1,2,3]
let res = arr.every((item)=>item >0)
console.log(res)
```
* some-
  * even if 1 element satisfied the condition we get true.
```
let arr= [1,2,3]
let res = arr.some((item)=>item >4)
console.log(res)
```
* includes-
```
let arr= [1,2,3]
let res = arr.includes(3)
console.log(res)
```

* reduce-
```
let arr= [1,2,3]
let res= arr.reduce((acc,num)=> acc+num,0)
console.log(res)
```
* flat- remove nested array
    * flat()- takes by default value =1;
    * multiple array inside array- flat(Infinity)

```
@ I-
let arr= [1,2,3,[5,6],[8,1]]
console.log(arr.flat());
@ II-  
let arr1= [1,2,3,[5,6,[9,4]]]
console.log(arr1.flat(2));
let arr1= [1,2,3,[5,6,[9,4]]]
@ III-   
let arr= [1,2,3,[5,6,[9,[9,0,[1,2]],4]]]
console.log(arr.flat(Infinity));
```
* flatMap-
 * using next array iterable thing.

```
let data = 'my name is alok';
let data2 = data.split(' ')
let result = data2.flatMap((item)=>  item.split('')
)
console.log(result);
```
**# map v/s flatMap**

```
let cart=[
    { name:'mobile phone', qty:2,price:500 },
    { name:'tablet', qty:5,price:2500 },
]
@ map-
let arr=[10,20,30,[40,50],60,70]
let res = arr.map((item=>item))
console.log(res)

@ flatMap-
let arr=[10,20,30,[40,50],60,70]
let res = arr.flatMap((item=>item))
console.log(res)
```
* Array.isArray
  * check it is array or not. 
```
let res= Array.isArray([1,2,3])
console.log(res)
```
* Array.from-
* convert string to array.
  
```
let data = "alok"
console.log(Array.from(data))
@ logic-
console.log(Array.from({name:"alok"}))
```

* Array.of()-
     * Array.of method creates a new Array instance.
```
console.log(Array.of());
console.log(Array.of('foo', 112, 'bar', true));
```
* fill-
 *  fill an array with a specified value.It modifies the original array and returns the modified array.

```
let arr= [1,2,3].fill(0)
console.log(arr)
let arr= [1,2,3].fill(0,1)
console.log(arr)

```

* split-
```
```
* concat-
```
let arr= [1,2,3].concat([4,5])
console.log(arr)
```
* reverse-
```
let arr= [1,2,3].reverse()
console.log(arr)
```
* sort-
  
```
@ string-
var num = ['banglaure','africa','kanpur','canada']
var result = num.sort();
console.log(result);

@ Number-
var num = [10,40,30,20]
var result = num.sort();
console.log(result);

@ problem-
var num = [10,40,30,-4,200]
var result = num.sort();
console.log(result); 

@ solve-
var num = [10, 40, 30,-4, 200];
var result = num.sort((a,b) => (a - b)-(b-a));
console.log(result);


* join-
  * convert array to string.
```
let arr= [1,2,3].join()
let arr1= [1,2,3].join('-')
console.log(arr)
console.log(arr1)
```
* tostring-
```
let arr= [1,2,3].toString()
console.log(arr)
console.log(typeof(arr))
```
* toLocaleString-
```
let arr= [1,2,3].toLocaleString()
console.log(arr)
console.log(typeof(arr))
```

* Cloning/coping array-
  * spread
```
const arr = [1,2,3];
const newArr = [...arr, 9,8];
console.log(newArr);
```
  * slice
```
let arr=['alok','kittu']
let res=arr.slice(0)
console.log(res);
```
  * concat-
```
const arr = [1,2,3]
const arr1 = [5,7,8]
const ConcateArr = [...arr, ...arr1];
console.log(ConcateArr)
```

  * Array.from()-
```
let arr= [10,20,30]
let res=Array.from(arr)
console.log(arr);
```


* mutable methods- push(),pop(),shift(),unshift(),splice(),sort(),reverse(),fill(),copyWithin(). 
* immutable methods- concat(),slice(),map(),filter(),reduce(),join(),find(),findIndex(),includes().

