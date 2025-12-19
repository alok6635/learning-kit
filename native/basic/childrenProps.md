### props_not_changeable

```
## App.jsx-
import { Text, View } from 'react-native'
import React from 'react'
import Child from './Child'

const App = () => {
  let name ="alok";
  return (
    <>
      <Child name={name}/>
    </>
  )
}
export default App;

## Child.jsx-
import React from 'react';
import { Text, View } from 'react-native';
const Child = (props) => {
    console.log(props.name);
    props.name="kittu"
  return (
    <View>
      <Text>{props.name}</Text>
    </View>
  );
};
export default Child;

```
### children_props

```
## App.jsx-
import { StyleSheet, Text, View } from 'react-native'
import React from 'react'
import Child from './Child'

const App = () => {
  return (
    <>
      <View>
        <Text>this is the children props</Text>
      </View>
      <Child />
    </>
  )
}
export default App;

## child.jsx-
import { StyleSheet, Text, View } from 'react-native';

const Child = (props) => {
  return (
    <View>
        <Text>{props.children }</Text>
    </View>
  )
}
export default Child;
const styles = StyleSheet.create({})
```

### prop_types
```
## App.jsx-
import { StyleSheet, Text, View } from 'react-native'
import React from 'react'
import Child from './Child'
const App = () => {
  let name ="alok";
  let age =11;
  let value;
  return (
    <>
      <Child name={name} age ={age} value={value} />
    </>
  )
}
export default App;

## Child.jsx-
import React from 'react';
import { Text, View } from 'react-native';
import PropTypes from 'prop-types';

const Child = ({ name, age, value }) => {
  return (
    <View>
      <Text>Name: {name}</Text>
      <Text>Age: {age}</Text>
      <Text>Value: {value}</Text>
    </View>
  );
};
Child.propTypes = {
  name: PropTypes.string.isRequired,
  age: PropTypes.number.isRequired,
    value: PropTypes.number,
};
export default Child;
```




