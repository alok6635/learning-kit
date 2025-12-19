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



