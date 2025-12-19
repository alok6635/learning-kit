

```
import React, { useState } from 'react';
import { StyleSheet, Text, TouchableOpacity, View } from 'react-native';
import ChildA from './componet/ChildA';
const App = () => {
  const [count, setCount] = useState(0);
  return (
    <>
      <View>
        <Text>Count : {count}</Text>
      </View>
      <TouchableOpacity onPress={() => setCount(count + 1)} style={styles.btn}>
        <Text style={styles.btnText}>Add</Text>
      </TouchableOpacity>
      <ChildA />
    </>
  )
}
export default App;
const styles = StyleSheet.create({
  btn:{
    width:50,
    borderWidth:1,
    borderColor:"#000",
    borderRadius:5,
    backgroundColor:'red'
  },
  btnText:{
     textAlign:'center',
     color:'#fff'
  }
})

#child-
import { Text, View } from 'react-native'
import React, { memo } from 'react'
const Child = () => {
  console.log('child component')
  return (
    <View>
      <Text>Child comp</Text>
    </View>
  )
}
export default memo(Child);
```

```
#useMemo
```
import { useMemo, useState } from "react";
const App = () => {
  const [inc,setInc] = useState(10);
  const [dec,setDec] = useState(15);

// const add=(a,b)=>{
//   console.log('add function call');
//   return a+b;
// }

const add = useMemo(()=>{
  console.log('add function call');
     return (a,b)=>a+b;
},[inc]);

return (
    <>
      <div>{add(2,5)}</div>
      <button onClick={()=>setInc(inc+1)}>Inc</button>
      <span>{inc}</span><br/>
      <button onClick={()=>setDec(dec-1)}>Dec</button>
      <span>{dec}</span>
    </>
  )
}
export default App;
```

**advance**

```
import { useMemo } from 'react';
import { useState } from 'react'

function App() {
  const [count, setCount] = useState(0);
  const [input,setInput] = useState(0);

  function expensiveTask(num) {
    console.log("Inside Expensive Task");
    for (let i = 0; i <= 1000000000; i++) { }
    return num * 2;
  }
  let doubleValue = useMemo(() => expensiveTask(input),[input]);

  return (
    <>
      <button onClick={() => setCount(count + 1)}> Incr </button>
      <input onChange={(e) => setInput(e.target.value)} />
      <div>Count: {count}</div>
      <div>Double: {doubleValue}</div>
    </>

  )
}
export default App

```


## usecallback-
```
@@@ App.js-
import { useCallback, useState } from "react";
import Child from "./Child";

const App = () => {
  const [count, setCount] = useState(0);
  const [add, setAdd] = useState(0);

  // const Learning =()=>{
  //       console.log("callback function")
  // }

  const Learning = useCallback(() => {
    console.log("callback function")
  }, [add])

  return (
    <>
      <Child Learning={Learning} add={add} />
      <div>Count : {count}</div>
      <button onClick={() => setCount(count+1)}>Inc</button>
      <div>Add : {add}</div>
      <button onClick={() => setAdd(add+1)}>Add</button>
    </>
  )
}
export default App;

@@@ Child.jsx-
import React, { memo } from 'react'

const Child = ({Learning,add}) => {
    console.log('child component');
    return (
        <>
        </>
    )
}
export default memo( Child);
```

