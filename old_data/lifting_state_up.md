```
#App.js-
import React from 'react'
import Child from './Child'

const App = () => {
  function getData(data){
     console.log(data)
  }
  return (
  <Child getData={getData}/>
  )
}
export default App;

#Child.jsx-
import React, { useState } from 'react'

const Child = ({getData}) => {
const [name,setName] = useState();

const handleSubmit =()=>{
    getData(name)
}
    return (
        <>
            <input type="text"value={name} onChange={(e)=>setName(e.target.value)}/>
            <button onClick={handleSubmit} >add</button>
        </>

    )
}
export default Child;

### 2nd Synrio-
#App.js-
import { useState } from "react";
import Child from "./Child";

const App = () => {
  const arr = ['ram', 'shyam', 'sunil', 'mohan'];
  const [user, setUser] = useState(arr);

  const delItem = (itemToRemove) => {
    console.log(itemToRemove);
    const updatedUser = user.filter((val, index) => index !== itemToRemove);
    setUser(updatedUser);
  }
  return (
    <>
      {
        user.map((item, index) => {
          return <li key={index}>
            <Child id={index} item={item} delItem={delItem} />
          </li>
        }
        )
      }
    </>
  )
}
export default App;
#Child.js-
import React from 'react';

const Child = ({ item, delItem, id }) => {
    return (
        <>
            {item}
            <button onClick={() => delItem(id)}>Del</button>
        </>
    );
}
export default Child;

```
