<summary>synario asynchronous</summary>
	
* case-I  asynchronous v/s synchronous task.
* below code is asynchronous code.
```
function one (){
    console.log('alok1');
}
function two(){
    fetch('https://fakestoreapi.com/products')
    .then((respon)=>respon.json())
    .then((res)=>{
        console.log(res);
    })
}
function three(){
console.log('alok3');
}
one()
two()
three()
```
* requirement is when function two gives the result then function three is called.so we want to this code work as a 
  synchronouslly.we have two method callback,async & await.
```
@@@ using callback-
function one (){
    console.log('alok1');
}
function two(cb){
    fetch('https://fakestoreapi.com/products')
    .then((respon)=>respon.json())
    .then((res)=>{
        console.log(res[0].title);
        cb()
    })
}
function three(){
console.log('alok3');
}
one()
two(three)

@@@ using async & await-
function one(){
    console.log('kittu1');
}
async function two(){
      let data= await fetch('https://fakestoreapi.com/products')
      let res= await data.json();
      console.log(res[0].title);
     console.log('kittu2');
      three()
}
function three(){
    console.log('kittu3');
}
one()
two()
```

* case-II- effect b/w callback v/s without callback.
```
* without callback problem-
function hello(data){
    setTimeout(()=>{
        console.log(data)
      },Math.random()*10)
  }
function say(){
    hello("alok1")
    hello("alok2")
    hello("alok3")
  }
say()

* using callback resolve problem-
function hello(data,cb){
    setTimeout(()=>{
        console.log(data)
        cb()
      },Math.random()*10)
  }
function say(){
    hello('alok1',()=>{
        hello('alok2',()=>{
            hello('alok3',()=>{
            })
        })
    })
  }
say()
```

