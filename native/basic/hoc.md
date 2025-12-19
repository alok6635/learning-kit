```
import React from 'react';
import { SafeAreaView } from 'react-native';
import Click from './Click';
import Hover from './Hover';

const App = () => {
  return (
    <SafeAreaView>
      <Click/>
      <Hover/>
    </SafeAreaView>
  )
}
export default App;

#HOC.jsx-
import { useState } from "react";
const Hoc = (OldComponent) => {
    return function EnhancedComponent() {
        const [count, setCount] = useState(0);
        return (
            <OldComponent 
                count={count} 
                handleAdd={() => setCount(count + 1)} 
            />
        )
    }
}
export default Hoc;

#Hover.jsx-
import React from 'react';
import { View, Text, TouchableOpacity, StyleSheet } from 'react-native';
import Hoc from './Hoc';

const Hover = (props) => {
    const { count, handleAdd } = props;
    return (
        <View style={styles.container}>
            <Text style={styles.count}>{count}</Text>
            <TouchableOpacity style={styles.button} onPressIn={handleAdd}>
                <Text style={styles.buttonText}>Hover me</Text>
            </TouchableOpacity>
        </View>
    )
}
const styles = StyleSheet.create({
    container: { alignItems: 'center', margin: 10 },
    button: { backgroundColor: '#28a745', padding: 10, borderRadius: 5 },
    buttonText: { color: '#fff', fontSize: 16 },
    count: { marginBottom: 10, fontSize: 18 }
});
export default Hoc(Hover);

#click.jsx-
import React from 'react';
import { View, Text, TouchableOpacity, StyleSheet } from 'react-native';
import Hoc from './Hoc';

const Click = (props) => {
    const { count, handleAdd } = props;
    return (
        <View style={styles.container}>
            <TouchableOpacity style={styles.button} onPress={handleAdd}>
                <Text style={styles.buttonText}>Click Me</Text>
            </TouchableOpacity>
            <Text style={styles.count}>{count}</Text>
        </View>
    )
}

const styles = StyleSheet.create({
    container: { alignItems: 'center', margin: 10 },
    button: { backgroundColor: '#007bff', padding: 10, borderRadius: 5 },
    buttonText: { color: '#fff', fontSize: 16 },
    count: { marginTop: 10, fontSize: 18 }
});

export default Hoc(Click);

```
