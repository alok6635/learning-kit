```
let obj1={
    name:'alok',
    age:32,
    say:function(city,country){
        return `${this.name} ${this.age} ${city} ${country}`
    }
}
let obj2={
    name:'kittu',
    age:12,
}
* call-
console.log(obj1.say.call(obj2,'kanpur','nepal'));
* apply-
let arr=['kanpur','india']
console.log(obj1.say.apply(obj2,arr));
* bind-
let res= obj1.say.bind(obj2,'kanpur','nepal')
console.log(res);
```


