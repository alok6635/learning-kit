
```
@@@ I-addEventListener or onclick-
<a href="abc.html" id="demo" onclick="handleAdd(event)">click me</a>
document.querySelector('#demo').addEventListener('click',handleAdd);
function handleAdd(event){
   event.preventDefault();
   event.target.style.fontSize = '32px';
}
* onclick-
<a href="abc.html" id="demo" onclick="handleAdd(event)">click me</a>
function handleAdd(event){
   event.preventDefault();
   event.target.style.fontSize = '32px';
}
@@@ II-javascript void(0)-
<a href="javascript:void(0)" id="demo" onclick="handleAdd()">click me</a>
function handleAdd(){
    console.log('aaaaaaaaa');
}
@@@ III-return false-
  <a href="abc.html" id="demo" onclick="return false;">click me</a><br>
  ```


