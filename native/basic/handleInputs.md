**# single inputs v/s multiple inputs**

```
import { StyleSheet, Text, TouchableOpacity, View, TextInput,FlatList } from 'react-native';
import React, { useState } from 'react';


const HandleInputs = () => {
    const [cred, setCred] = useState({ name: '', pass: '' });
    const [display,setDisplay] = useState([]);

    const handleAdd=()=>{
        setDisplay([...display,cred])
    }
    return (
        <>
        <View style={styles.container}>
            <TextInput style={styles.input} placeholder='Enter name' value={cred.name} onChangeText={(value) => setCred({ ...cred, name: value })} />
            <TextInput style={styles.input} placeholder='Enter pass' value={cred.pass} onChangeText={(value) => setCred({ ...cred, pass: value })} />
            <TouchableOpacity style={styles.btn} onPress={handleAdd}><Text style={styles.text}>Add </Text></TouchableOpacity>
        </View>
        {
            <FlatList data={display}
             renderItem={({item})=> <View style={styles.displayContainer}>
                   <Text>{`${item.name} & ${item.pass}`}</Text>
             </View>}
            />
        }
        </>
    )
}
export default HandleInputs;


const styles = StyleSheet.create({
    container: {
        marginTop: 50,
        alignItems:'center'
    },
    input: {
        width:'80%',
        borderWidth: 1,
        borderColor: '#000',
        borderRadius: 5,
        padding: 5,
        marginBottom:5,
    },
    btn: {
        width:'80%',
        backgroundColor: '#000',
        color: '#fff',
        padding: 10,
        borderRadius:5,
    },
    text: {
        color: '#fff',
        textAlign:'center'
    },
    displayContainer:{
        margin:38,
        width:'70%',
        borderWidth: 1,
        borderColor: '#000',
        borderRadius: 5,
        padding: 5,
        marginBottom:5,
    }
})
```

**# dynamic key(name & value)**


```
import { StyleSheet, Text, TouchableOpacity, View, TextInput,FlatList } from 'react-native';
import React, { useState } from 'react';

const HandleInputs = () => {
    const [cred, setCred] = useState({ name: '', pass: '' });
    const [display,setDisplay] = useState([]);

    const handleAdd=()=>{
        setDisplay([...display,cred])
    }

    const handleChange=(key,value)=>{
           setCred({...cred,[key]:value})
    }

    return (
        <>
        <View style={styles.container}>
            <TextInput style={styles.input} placeholder='Enter name' name="name" value={cred.name} onChangeText={(value)=>handleChange('name',value)} />
            <TextInput style={styles.input} placeholder='Enter pass' name="pass" value={cred.pass} onChangeText={(value)=>handleChange('pass',value)} />
            <TouchableOpacity style={styles.btn} onPress={handleAdd}><Text style={styles.text}> Add </Text></TouchableOpacity>
        </View>
        {
            <FlatList data={display}
             renderItem={({item})=> <View style={styles.displayContainer}>
                   <Text>{`${item.name} & ${item.pass}`}</Text>
             </View>}
            />
        }
        </>
    )
}
export default HandleInputs;

const styles = StyleSheet.create({
    container: {
        marginTop: 50,
        alignItems:'center'
    },
    input: {
        width:'80%',
        borderWidth: 1,
        borderColor: '#000',
        borderRadius: 5,
        padding: 5,
        marginBottom:5,
    },
    btn: {
        width:'80%',
        backgroundColor: '#000',
        color: '#fff',
        padding: 10,
        borderRadius:5,
    },
    text: {
        color: '#fff',
        textAlign:'center'
    },
    displayContainer:{
        margin:38,
        width:'70%',
        borderWidth: 1,
        borderColor: '#000',
        borderRadius: 5,
        padding: 5,
        marginBottom:5,
    }
})

```

**# useRucer**-

```
import { StyleSheet, TextInput, TouchableOpacity, View, Text, FlatList } from 'react-native';
import React, { useReducer } from 'react';

const InputReducer = () => {
  const initialState = {
    name: '',
    pass: '',
    display: []
  };

  const reducer = (state, action) => {
    switch (action.type) {
      case 'NAME':
        return { ...state, name: action.payload };
      case 'PASS':
        return { ...state, pass: action.payload };
      case 'ADD':
        return { ...state, display: [...state.display, { name: state.name, pass: state.pass }] };
      default:
        return state;
    }
  };

  const [state, dispatch] = useReducer(reducer, initialState);

  const handleSubmit = () => {
    if (state.name && state.pass) {
      dispatch({ type: 'ADD' });
    }
  };

  return (
    <>
      <View style={styles.container}>
        <View>
          <TextInput
            style={styles.input}
            placeholder="Enter name"
            value={state.name}
            onChangeText={(text) => dispatch({ type: 'NAME', payload: text })}
          />
          <TextInput
            style={styles.input}
            placeholder="Enter pass"
            value={state.pass}
            onChangeText={(text) => dispatch({ type: 'PASS', payload: text })}
          />
          <TouchableOpacity style={styles.add} onPress={handleSubmit}>
            <Text style={styles.text}>Add</Text>
          </TouchableOpacity>
        </View>
      </View>
      <View style={styles.displayContainer}>
        <FlatList
          data={state.display}
          keyExtractor={(item, index) => index.toString()}
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

export default InputReducer;

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



