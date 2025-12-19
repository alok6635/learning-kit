
**# counter using context api**

```
import React, { createContext, useState } from 'react';
export const CounterContext = createContext();

const Store = ({ children }) => {
  const [count, setCount] = useState(0);

  const handleAdd = () => {
    setCount(prev => prev + 1);
  };
  return (
    <CounterContext.Provider value={{ count, handleAdd }}>
      {children}
    </CounterContext.Provider>
  );
};
export default Store;

#App.jsx-
import React from 'react';
import CounterSlice from './componet/CounterSlice';
import Store from './componet/store';

const App = () => {
  return (
    <Store>
      <CounterSlice/>
    </Store>
  );
};
export default App;

#CounterSlice.jsx-
import { StyleSheet, Text, TouchableOpacity, View } from 'react-native'
import React, { useContext } from 'react'
import { CounterContext } from './store';

const CounterSlice = () => {
  const { count, handleAdd } = useContext(CounterContext);
  return (
    <View style={styles.container}>
        <Text style={styles.countText}>{count}</Text>
        <TouchableOpacity style={styles.button} onPress={handleAdd}>
          <Text style={styles.buttonText}>Add</Text>
        </TouchableOpacity>
      </View>
  )
}
export default CounterSlice
const styles = StyleSheet.create({
  container: { flex: 1, justifyContent: 'center', alignItems: 'center' },
  countText: { fontSize: 24, marginBottom: 20 },
  button: { backgroundColor: 'blue', padding: 10, borderRadius: 5 },
  buttonText: { color: '#fff', fontSize: 18 },
});
```

**# simple**

```
import { createContext } from "react";
import Child from "./componet/Child";
export const objContext = createContext();
const App = () => {
  const obj = { name: 'alok'}
  return (
    <>
      <objContext.Provider value={{obj}}>
        <Child />
      </objContext.Provider>
    </>
  )
}
export default App;

#child.js-
import React, { useContext } from 'react';
import { objContext } from '../App';
import { Text, View } from 'react-native';

const Child = () => {
  const { obj } = useContext(objContext); 
  return (
    <View>
        <Text>{obj.name}</Text>
    </View>
  );
};
export default Child;
```

