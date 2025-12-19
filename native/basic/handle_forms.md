**# Handle multiple inputs using only single state**

```
import { StyleSheet, TextInput, TouchableOpacity, View, Text, FlatList } from 'react-native';
import React, { useState } from 'react';

const App = () => {
  const [cred, setCred] = useState({ name: '', pass: '' });
  const [display, setDisplay] = useState([]);

  const handleSubmit = () => {
    setDisplay([...display, cred])
  }
  return (
    <>
      <View style={styles.container}>
        <View>
          <TextInput style={styles.input} placeholder='enter name' value={cred.name} onChangeText={(value)=>setCred({ ...cred,name:value})}/>
          <TextInput style={styles.input} placeholder='enter pass' value={cred.pass} onChangeText={(value)=>setCred({ ...cred, pass: value})}/>
          <TouchableOpacity style={styles.add} onPress={handleSubmit}>
            <Text style={styles.text}>Add</Text>
          </TouchableOpacity>
        </View>
      </View>
      {
        <View style={styles.displayContainer}>
          <FlatList data={display}
            keyExtractor={(item) => item.toString()}
            renderItem={({item}) => <View style={styles.displayText}>
              <Text>{`${item.name} & ${item.pass}`}</Text>
            </View>}/>
        </View>
      }
    </>
  )}
export default App;

const styles = StyleSheet.create({
  container: {
    marginTop: 30,
    padding: 20,
    backgroundColor: '#f8f9fa',
  },
  input: {
    paddingLeft: 5,
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    marginBottom: 10
  },
  add: {
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    backgroundColor: 'blue',
    padding: 10,
  },
  text: {
    color: 'white',
    textAlign: 'center',
    fontSize: 20
  },
  displayContainer: {
    flex: 1,
    padding: 10,
    marginLeft: 20,
    marginRight: 20,
    borderRadius: 5,
  },
  displayText: {
    border: 1,
    borderWidth:1,
    borderRadius:5,
    marginBottom:10,
    padding:5,
    borderColor: 'black',
  }
})
```

**# Handle multiple inputs using only single state**

* using only one function in InputText-
```
import { StyleSheet, TextInput, TouchableOpacity, View, Text, SafeAreaView, FlatList } from 'react-native';
import React, { useState } from 'react';

const App = () => {
    const [cred, setCred] = useState({ name: '', pass: '' });
    const [display, setDisplay] = useState([]);

  const handleChange =(field, value)=>{
    setCred({ ...cred, [field]: value });
  }

    const handleSubmit = () => {
        setDisplay([...display, cred])
    }
    return (
        <>
            <View style={styles.container}>
                <View>
                    <TextInput style={styles.input} placeholder='enter name' name='name' value={cred.name}  onChangeText={(value) => handleChange('name', value)}  />
                    <TextInput style={styles.input} placeholder='enter pass' name='pass' value={cred.pass} onChangeText={(value) => handleChange('pass', value)} />
                    <TouchableOpacity style={styles.add} onPress={handleSubmit}>
                    <Text style={styles.text}>Add</Text>
                    </TouchableOpacity>
                </View>
            </View>
            {
                <View style={styles.displayContainer}>
                    <FlatList data={display}
                        keyExtractor={(item) => item.toString()}
                        renderItem={({ item }) => <View style={styles.displayText}>
                            <Text>{`${item.name} & ${item.pass}`}</Text>
                        </View>
                        }
                    />
                </View>
            }
        </>
    )
}
export default App;

const styles = StyleSheet.create({

    container: {
        marginTop: 30,
        padding: 20,
        backgroundColor: '#f8f9fa',
    },
    input: {
        paddingLeft: 5,
        borderWidth: 1,
        borderColor: '#ccc',
        borderRadius: 5,
        marginBottom: 10
    },
    add: {
        borderWidth: 1,
        borderColor: '#ccc',
        borderRadius: 5,
        backgroundColor: 'blue',
        padding: 10,
    },
    text: {
        color: 'white',
        textAlign: 'center',
        fontSize: 20
    },
    displayContainer: {
        flex: 1,
        padding: 10,
        marginLeft: 20,
        marginRight: 20,
        borderRadius: 5,
    },
    displayText: {
        border: 1,
        borderWidth: 1,
        borderRadius: 5,
        marginBottom: 10,
        padding: 5,
        borderColor: 'black',
    }
})

``` 
**# useReducer**

```
import { StyleSheet, TextInput, TouchableOpacity, View, Text, FlatList } from 'react-native';
import React, { useReducer } from 'react';

const App = () => {
  const initialState = { name: '',  pass: '',  display: []};

  const reducer = (state, action) => {
    switch (action.type) {
      case 'NAME':
        return { ...state, name: action.payload };
      case 'PASS':
        return { ...state, pass: action.payload };
      case "ADD":
        return { ...state, display: [...state.display, { name: state.name, pass: state.pass }] };
      default:
        return state;
    }
  };
  const [state, dispatch] = useReducer(reducer, initialState);

  const handleSubmit = () => {
    dispatch({ type: "ADD" });
  };

  return (
    <>
      <View style={styles.container}>
        <View>
          <TextInput style={styles.input} placeholder='enter name' value={state.name} onChangeText={(value) => dispatch({ type: 'NAME', payload:value})}/>
          <TextInput style={styles.input}  placeholder='enter pass'  value={state.pass} onChangeText={(value) => dispatch({ type: 'PASS', payload:value})}/>
          <TouchableOpacity style={styles.add} onPress={handleSubmit}>
            <Text style={styles.text}>Add</Text>
          </TouchableOpacity>
        </View>
      </View>
      <View style={styles.displayContainer}>
        <FlatList
          data={state.display}
          keyExtractor={(_, index) => index.toString()}
          renderItem={({ item }) => (
            <View style={styles.displayText}>
              <Text>{`${item.name} & ${item.pass}`}</Text>
            </View>
          )}
        />
      </View>
    </>
  );
};
export default App;

const styles = StyleSheet.create({
  container: {
    marginTop: 30,
    padding: 20,
    backgroundColor: '#f8f9fa',
  },
  input: {
    paddingLeft: 5,
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    marginBottom: 10
  },
  add: {
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    backgroundColor: 'blue',
    padding: 10,
  },
  text: {
    color: 'white',
    textAlign: 'center',
    fontSize: 20
  },
  displayContainer: {
    flex: 1,
    padding: 10,
    marginLeft: 20,
    marginRight: 20,
    borderRadius: 5,
  },
  displayText: {
    borderWidth: 1,
    borderRadius: 5,
    marginBottom: 10,
    padding: 5,
    borderColor: 'black',
  }
});

```

**# useRef**

```
import { useRef, useState } from 'react';
import { StyleSheet, TextInput, TouchableOpacity, View, Text, FlatList } from 'react-native';

const App = () => {
  const nameRef = useRef();
  const passRef = useRef();
  const [display, setDisplay] = useState([]);

  const handleSubmit = () => {
    setDisplay([...display, { name: nameRef.current.value, pass: passRef.current.value }]);
  };

  return (
    <>
      <View style={styles.container}>
        <View>
          <TextInput style={styles.input} placeholder="enter name" ref={nameRef}  onChangeText={(text) => (nameRef.current.value = text)}/>
          <TextInput style={styles.input} placeholder="enter pass" ref={passRef} onChangeText={(text) => (passRef.current.value = text)}/>
          <TouchableOpacity style={styles.add} onPress={handleSubmit}>
            <Text style={styles.text}>Add</Text>
          </TouchableOpacity>
        </View>
      </View>

      <View style={styles.displayContainer}>
        <FlatList
          data={display}
          keyExtractor={(_, index) => index.toString()}
          renderItem={({ item }) => (
            <View style={styles.displayText}>
              <Text>{`${item.name} - ${item.pass}`}</Text>
            </View>
          )}
        />
      </View>
    </>
  );
};
export default App;

const styles = StyleSheet.create({
  container: {
    marginTop: 30,
    padding: 20,
    backgroundColor: '#f8f9fa',
  },
  input: {
    paddingLeft: 5,
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    marginBottom: 10,
  },
  add: {
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    backgroundColor: 'blue',
    padding: 10,
  },
  text: {
    color: 'white',
    textAlign: 'center',
    fontSize: 20,
  },
  displayContainer: {
    flex: 1,
    padding: 10,
    marginLeft: 20,
    marginRight: 20,
    borderRadius: 5,
  },
  displayText: {
    borderWidth: 1,
    borderRadius: 5,
    marginBottom: 10,
    padding: 5,
    borderColor: 'black',
  },
});

```


**# counter (useReducer max 10 & min 0)**

```
import { FlatList, StyleSheet, Text, TouchableOpacity, View } from 'react-native'
import React, { useReducer } from 'react'

const App = () => {

  const initialState = {
    count: 0
  }
  const reducer = (state, action) => {
    switch (action.type) {
      case "ADD":
        return {...state, count: state.count + action.payload <= 10 ? state.count + action.payload : 10 };
      case "SUB":
        return {...state, count: state.count + action.payload >= 0  ? state.count - action.payload : 0 };
      default:
        return state
    }
  }
  const [state, dispatch] = useReducer(reducer, initialState);

  const handleAdd = () => { dispatch({ type: 'INC', payload: 2 })}
  const handleSub = () => {dispatch({ type: 'DEC', payload: 1 })}
  return (
    <View style={styles.container}>
      <Text style={styles.count}>Count: {state.value}</Text>
      <TouchableOpacity style={styles.button} onPress={handleAdd}>
        <Text style={styles.btnText}>+</Text>
      </TouchableOpacity>
      <TouchableOpacity onPress={handleSub} style={styles.button}>
        <Text style={styles.btnText}>-</Text>
      </TouchableOpacity>
    </View>
  )
}
export default App

const styles = StyleSheet.create({
  container: {
    flex: 1,
    justifyContent: "center",
    alignItems: "center",
    backgroundColor: "#f5f5f5"
  },
  title: {
    fontSize: 28,
    fontWeight: "bold",
    marginBottom: 20,
    color: "#333"
  },
  count: {
    fontSize: 24,
    marginBottom: 30,
    color: "#555"
  },

  button: {
    backgroundColor: "#4CAF50",
    paddingVertical: 12,
    paddingHorizontal: 20,
    borderRadius: 8,
    marginHorizontal: 10
  },
  btnText: {
    fontSize: 22,
    fontWeight: "bold",
    color: "#fff"
  }
})
```




**# useRef**

```
import React, { useRef, useState } from 'react';
import { View, Text, TextInput, Button, StyleSheet, ScrollView } from 'react-native';

const InputRef = () => {
  const nameRef = useRef();
  const passRef = useRef();
  const [display, setDisplay] = useState([]);

  const handleAdd = () => {
    setDisplay([
      ...display,
      { name: nameRef.current, pass: passRef.current }
    ]);
    nameRef.current = '';
    passRef.current = '';
  };

  return (
    <ScrollView contentContainerStyle={styles.container}>
      <View style={styles.inputContainer}>
        <TextInput
          placeholder="Name"
          style={styles.input}
          onChangeText={(text) => (nameRef.current = text)}
        />
        <TextInput
          placeholder="Password"
          style={styles.input}
          secureTextEntry
          onChangeText={(text) => (passRef.current = text)}
        />
        <Button title="Add" onPress={handleAdd} />
      </View>
      <View style={styles.displayContainer}>
        {display.map((item, index) => (
          <Text key={index} style={styles.displayText}>
            {`${item.name} ${item.pass}`}
          </Text>
        ))}
      </View>
    </ScrollView>
  );
};

const styles = StyleSheet.create({
  container: {
    flexGrow: 1,
    padding: 20,
    backgroundColor: '#fff',
  },
  inputContainer: {
    marginBottom: 20,
  },
  input: {
    borderWidth: 1,
    borderColor: '#ccc',
    borderRadius: 5,
    marginBottom: 10,
    paddingHorizontal: 10,
    height: 40,
  },
  displayContainer: {
    marginTop: 20,
  },
  displayText: {
    fontSize: 16,
    marginBottom: 5,
  },
});

export default InputRef;
```



