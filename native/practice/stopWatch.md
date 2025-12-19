```

import { StyleSheet, Text, TouchableOpacity, View } from 'react-native'
import React, { useState } from 'react';

const StopWatch = () => {
  const [count, setCount] = useState(0);
  const [interval, setIntertval] = useState(null);

  const handleStart = () => {
    const id = setInterval(() => {
      setCount((prev) => prev + 1)
    }, 1000);
    setIntertval(id)
  }
  const handleStop = () => {
    if (interval) {
      clearInterval(interval);
      setIntertval(null);
    }
  }
  const handleReset = () => {
    clearInterval(interval);
    setCount(0);
    setIntertval(null);
  }
  return (
    <View style={styles.cover}>
      <Text>Count: {count}</Text>
      <View style={styles.container}>
        <TouchableOpacity onPress={handleStart}><Text style={styles.btn}>Start</Text></TouchableOpacity>
        <TouchableOpacity onPress={handleStop}><Text style={styles.btn}>Stop</Text></TouchableOpacity>
        <TouchableOpacity onPress={handleReset}><Text style={styles.btn}>Reset</Text></TouchableOpacity>
      </View>
    </View>
  )
}
export default StopWatch

const styles = StyleSheet.create({
  cover: {
    paddingTop: 35,
    paddingLeft: 20
  },
  container: {
    flexDirection: 'row',
  },
  btn: {
    borderWidth: 1,
    borderColor: '#000',
    borderRadius: 5,
    padding: 10,
    backgroundColor: 'black',
    color: '#fff',
    margin: 10
  }
})
```

#TOGGLE#

```
import { StyleSheet, Text, TouchableOpacity, View } from 'react-native'
import React, { useState } from 'react'

const Temp = () => {
   const [toggle,setToggle] = useState();
const handleToggle=()=>{
setToggle(!toggle)
}
  return (
    <>
    <View>
      <Text style={[styles.heading,{color: toggle ? "black" :"red"}]}>{toggle ? "ON" : "OFF"}</Text>
     <TouchableOpacity style={styles.btn} onPress={handleToggle}>
     <Text style={styles.buttonText}>{toggle ? "ON" : "OFF"}</Text>
     </TouchableOpacity>
    </View>
    </>
  )
}
export default Temp;
const styles = StyleSheet.create({
btn:{
  backgroundColor:'blue',
  borderWidth:1,
  borderColor:"#000",
  padding:5,
  width:100,
  margin:'auto',
  borderRadius:5,
  marginTop:20
},
btnText:{
  color:'#fff',
  textAlign:'center'
},
heading:{
  textAlign:'center',
  fontWeight:'800'
}
});
```



