
	
```
<div id="parent">
<div id="child">
<div id="subChild"></div>
</div>
</div>
Css-
#parent {
    width: 200px;
    height: 200px;
    background: red;
    margin: 10px;
    padding: 5px;
  }
#child {
    background: blue;
    height: 150px;
    margin: 10px;
    padding: 10px;
  }
#subChild {
    background: palegreen;
    height: 100px;
    margin: 10px;
    padding: 10px;
  }

@@@ bubbling-
document.querySelector('#parent').addEventListener('click',function(){console.log('parent')})
document.querySelector('#child').addEventListener('click',function(){console.log('child')})
document.querySelector('#subChild').addEventListener('click',function(){console.log('subChild')})

@@@ capturning-
document.querySelector('#parent').addEventListener('click',()=>console.log('parent'),true)
document.querySelector('#child').addEventListener('click',()=>console.log('child'),true)
document.querySelector('#subChild').addEventListener('click',()=>console.log('subChild'),true)
@@@ stop-propogation (bubbling case)-

document.querySelector('#parent').addEventListener('click',function(e){
  console.log('parent');
})
document.querySelector('#child').addEventListener('click',function(e){
    e.stopPropagation()
    console.log('child');
  })
document.querySelector('#subChild').addEventListener('click',function(e){
    console.log('subChild');
  })
@@@ stop-propogation- (capturning-case)
document.querySelector('#parent').addEventListener('click',function(e){
     console.log('parent')},true)
document.querySelector('#child').addEventListener('click',function(e){
e.stopPropagation()
      console.log('child')},true)
document.querySelector('#subChild').addEventListener('click',function(e){
      console.log('subChild')},true)
```
