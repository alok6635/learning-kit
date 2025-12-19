**# usestate hook**

```
const App=()=>{
  let count=0;
function handleAdd=()=>{
   count= count+1;
  console.log(count)
}
  return(
    <>
    <h2>{count}</h2>
    <button onClick={handleAdd}>Add</button>
    </>
  )
}
```

**# single state (using by input name & value)**

```
import React, { useState } from 'react';

const App = () => {
  const [cred, setCred] = useState({ username: '', password: '' });
  const [display, setDisplay] = useState([]);

  const handleChange = (e) => {
    const { name, value } = e.target; 
    setCred({ ...cred, [name]: value }); 
  };

  const handleSubmit = (e) => {
    e.preventDefault();
    setDisplay([...display, cred]);
    setCred({ username: '', password: ''}); 
  };

  return (
    <>
      <form onSubmit={handleSubmit}>
        <input type="text" name="username" value={cred.username} onChange={handleChange}/><br/>
        <input type="password" name="password" value={cred.password} onChange={handleChange}/><br/>
        <input type="submit" value="Login" />
      </form>

        {
        display.map((item, index) => ( <div key={index}>{item.username} & {item.password}</div>))
        }
    </>
  );
};

export default App;
```


**useRef**

```
import React, { useRef, useState } from 'react';

const App = () => {
  const nameRef = useRef();
  const passRef  = useRef();
  const [display,setDisplay] = useState([]);

const handleAdd=(e)=>{
  e.preventDefault();
  setDisplay([...display, {name:nameRef.current.value, pass:passRef.current.value}])
}

  return (
    <>
    <form onSubmit={handleAdd}>
      <input type='name' ref={nameRef}/><br/>
      <input type='pass' ref={passRef}/><br/>
      <input type='submit'/>
    </form>
  {
    display.map((item,index)=> <div key={index}>{`${item.name} ${item.pass}`}</div> )
  }
    </>
  )
}
export default App;
```


**# useRef 2nd**

```
import React, { useRef, useState } from 'react';

const App = () => {
  const [name, setName] = useState('alok');
  const inpRef = useRef();

  const handleColor = () => {
    if (inpRef.current) {
      inpRef.current.value="kittu"
      inpRef.current.style.color = "blue";
    }
  };
  const handleReset=()=>{
    setName("")
    inpRef.current.focus()
    }

  return (
    <>
      <input type="text" ref={inpRef} value={name} onChange={(e) => setName(e.target.value)}/>
      <button onClick={handleColor}>Change Color</button>
      <button onClick={handleReset}>Reset</button>
    </>
  );
};
export default App;
```

**# useRef 3rd**

```
import React, { useRef, useState } from 'react';

const App = () => {
  const refValue = useRef(null); 
  const [count, setCount] = useState(0); 

  const handleAdd = () => {
    const inputValue = refValue.current.value;
    const parsedValue = parseInt(inputValue); 
      setCount((prevCount) => prevCount + parsedValue);
  };
  return (
    <>
      <input type="text" ref={refValue} />
      <button onClick={handleAdd}>Add</button>
      <p>Count: {count}</p>
    </>
  );
};
export default App;
```


