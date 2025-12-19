```
import React, { useState } from 'react';
const App = () => {
  const tabData = [
    { title: 'Tab1', content: 'Html Content'},
    { title: 'Tab2', content: 'Php Content'},
    { title: 'Tab3', content: 'React Content'},
    { title: 'Tab4', content: 'Node Content'}
  ];
  const [tab, setTab] = useState(0); 
  return (
    <>
      <ul className='tab_cover'>
        {
          tabData.map((item, index) => (
          <li key={index}  className={`tab ${tab === index ? 'active' : ''}`} onClick={()=>setTab(index)}>{item.title}</li>))
     }
      </ul>
      <div>
        {tabData[tab].content}
      </div>
    </>
  );
};
export default App;

#css-
.tab_cover{
    display: flex;
}
.tab{
    background: gray;
    padding: 10px;
    text-align: center;
    cursor: pointer;
    color: #fff;
}
.active{
    background: blue;
    border: none;
}

### second-
#App.js-
import React, { useState } from "react";
import tabData from "./data"; 
import Mobile from "./Mobile";
import Laptop from "./Laptop";

const App = () => {
  const [tab, setTab] = useState(tabData.key1);

  const handleTab = (key) => {
    setTab(key);
  };
  return (
    <>
      <div className="tab_cover">
        <div
          className={`${tab === tabData.key1 ? "tab active" : "tab"}`}
          onClick={() => handleTab(tabData.key1)}
        >
          {tabData.mobileTabs}
        </div>
        <div
          className={`${tab === tabData.key2 ? "tab active" : "tab"}`}
          onClick={() => handleTab(tabData.key2)}
        >
          {tabData.laptopTabs}
        </div>
      </div>
      {tab === tabData.key1 && <Mobile />}
      {tab === tabData.key2 && <Laptop />}
    </>
  );
};
export default App;

# data.js-
const tabData = {
    mobileTabs: "Mobile Details",
    laptopTabs: "Laptop Details",
    key1: 'mobile',
    key2: 'laptop'
  };
  export default tabData;

 # css-
.tab_cover{
    display: flex;
}
.tab{
    background: gray;
    padding: 10px;
    text-align: center;
    cursor: pointer;
    color: #fff;
}
.active{
    background: blue;
    border: none;
}


```


%%%%%%%%%%%%%  select type value

```
import React, { useState } from 'react';

const App = () => {
  const [selected, setSelected] = useState('');
  const vehicles = ['Car', 'Bike', 'Cycle', 'Bus'];

  const handleSelect = (e) => {
    setSelected(e.target.value);
  };
  return (
    <div>
      <select onChange={handleSelect} value={selected}>
        {vehicles.map((item, index) => {
          return <option key={index} value={item}>{item}</option>
        })}
      </select>
      <p>Selected Vehicle: {selected}</p> 
    </div>
  );
};
export default App;

@@@@@@@ STOP WATCH-
import React, { useState, useEffect } from "react";

const App = () => {
  const [time, setTime] = useState(0);
  const [isRunning, setIsRunning] = useState(false);

  useEffect(() => {
    let timer;
    if (isRunning) {
      timer = setInterval(() => setTime((prev) => prev + 1), 1000);
    } else {
      clearInterval(timer);
    }
    return () => clearInterval(timer);
  }, [isRunning]);

  const handleStartStop = () => setIsRunning(!isRunning);

  const handleReset = () => {
    setIsRunning(false);
    setTime(0);
  };

  return (
    <div>
      <h2>{time} s</h2>
      <button onClick={handleStartStop}>{isRunning ? "stop" : "Start"}</button>
      <button onClick={handleReset}> Reset </button>
    </div>
  );
};
export default App;
```

**# form validation**


```
import React from 'react'
import { useState } from 'react';

const App = () => {
  const [cred, setCred] = useState({ name: '', password: '', email: '' });
  const [error, setError] = useState({});

  const formValidate = () => {
    let Errors = {};
    if (!cred.name) {
      Errors.name = "name is required"
    }
    if (!cred.password) {
      Errors.password = "password is required"
    }
    else if(!cred.password < 10){
       Errors.password = "Password should more then 10 char"
    }
    if (!cred.email) {
      Errors.email = "email is required"
    }
    setError(Errors)
  }

  const handleSub = (e) => {
    e.preventDefault(); 
    if(formValidate()){
      console.log("Form submitted successfully")
    }
    else{
      console.log("Validation errors", error);
    }
  }

  return (
    <form onSubmit={handleSub}>
      <input type='text' placeholder='name' value={cred.name} onChange={(e) => setCred({...cred, name: e.target.value})}/><br/>
      <div>{error.name}</div>
      <input type='password' placeholder='password' value={cred.password} onChange={(e) => setCred({...cred, password: e.target.value})}/><br/>
      <div>{error.password}</div>
      <input type='email' placeholder='email' value={cred.email} onChange={(e) => setCred({...cred, email: e.target.value})}/><br/>
      <div>{error.email}</div>
      <input type='submit' />
    </form>
  )
}
export default App;

@@@@ using formik-
import React from "react";
import { useForm } from "react-hook-form";
const App = () => {
  const { register, handleSubmit,  watch, formState: { errors } } = useForm();

  const onSubmit = (data) => {
    console.log("Form Submitted Successfully:", data);
    alert("Form submitted!");
  };
  const passwordValue = watch("password");

  return (
    <div>
      <form onSubmit={handleSubmit(onSubmit)}>
        <div>
          <label>Name:</label>
          <input
            type="text"
            {...register ("name", { required: "Name is required" })}
          />
          {errors.name && <p style={{ color: "red" }}>{errors.name.message}</p>}
        </div>

        <div>
          <label>Email:</label>
          <input type="email" {...register("email", {
              required: "Email is required",
              pattern: {
                value: /^[^\s@]+@[^\s@]+\.[^\s@]+$/,
                message: "Invalid email format",
              },
            })}
          />
          {errors.email && (
            <p style={{ color: "red" }}>{errors.email.message}</p>
          )}
        </div>

        <div>
          <label>Password:</label>
          <input
            type="password"
            {...register("password", {
              required: "Password is required",
              minLength: {
                value: 8,
                message: "Password must be at least 8 characters long",
              },
              pattern: {
                value: /^(?=.*[A-Za-z])(?=.*\d)(?=.*[@$!%*#?&])[A-Za-z\d@$!%*#?&]{8,}$/,
                message:
                  "Password must include letters, numbers, and a special character",
              },
            })}
          />
          {errors.password && (
            <p style={{ color: "red" }}>{errors.password.message}</p>
          )}
        </div>

        <div>
          <label>Confirm Password:</label>
          <input
            type="password"
            {...register("confirmPassword", {
              required: "Please confirm your password",
              validate: (value) =>
                value === passwordValue || "Passwords do not match",
            })}
          />
          {errors.confirmPassword && (
            <p style={{ color: "red" }}>{errors.confirmPassword.message}</p>
          )}
        </div>

        <div>
          <button type="submit">Submit</button>
        </div>
      </form>
    </div>
  );
};
export default App;

```
