

**# useNavigate hook**


```
@@@ App.jsx-
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Home from './Home';
import About from './About';

const App = () => {
  return (
    <Router>
      <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about' element={<About />} />
      </Routes>
    </Router>
  );
};
export default App;

@@@ Home.jsx-
import React from 'react';
import { useNavigate } from 'react-router-dom';

const Home = () => {
  const navigate = useNavigate();
  return (
    <>
      <h3>Home Page</h3>
      <button onClick={() => navigate("/about")}>Go to About</button>
    </>
  );
};
export default Home;

@@@ About.jsx-
import React from 'react';

const About = () => {
  return <h3>Hi, I am the About Page</h3>;
};
export default About;
```

**# passing data via useNavigate hook**

```
@@@ App.js-
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Home from './Home';
import About from './About';

const App = () => {
  return (
    <Router>
      <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about' element={<About />} />
      </Routes>
    </Router>
  );
};
export default App;

@@@ Home.jsx-
import React from 'react';
import { useNavigate } from 'react-router-dom';

const Home = () => {
  const navigate = useNavigate();
  const name = "alok";
  return (
    <>
      <h3>Home Page</h3>
      <button onClick={() => navigate("/about",{state: { passData: name } })}>
        Go to About
      </button>
    </>
  );
};
export default Home;

@@@ About.jsx-
import React from 'react';
import { useLocation } from 'react-router-dom';

const About = () => {
  const location = useLocation();
  const { passData } = location.state

  return (
    <>
      <h3>Hi, I am the About Page</h3>
      {passData}
    </>
  );
};
export default About;
```

**# useLocation** 
```
@@@ App.js-
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Home from './Home';
import About from './About';
import NavBar from './NavBar';

const App = () => {
  return (
    <Router>
      <NavBar/>
      <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about' element={<About />} />
      </Routes>
    </Router>
  );
};
export default App;

@@@ NavBar.jsx-
import React from 'react'
import { Link } from 'react-router-dom'

const NavBar = () => {
    return (
        <ul >
            <li><Link to="/">Home </Link> </li>
            <li><Link to="about">About </Link> </li>
        </ul>
    )
}
export default NavBar

@@@ Home.jsx-
import React from 'react';

const Home = () => {
    return (
        <h3>Home Page</h3>
    );
};
export default Home;

@@@ About.jsx-
import React from 'react';
import { useLocation } from 'react-router-dom';

const About = () => {
   const location =  useLocation();
   console.log(location);
  return (
    <>
      <h3>Hi, I am the About Page</h3>
      <h4>Current Location : {location.pathname}</h4>
    </>
  );
};
export default About;
```


**# useParams**

```
@@@ App.jsx-
import React from 'react';
import { BrowserRouter as Router, Route, Routes } from 'react-router-dom';
import Home from './Home';
import About from './About';
import NavBar from './NavBar';
import Contact from './Contact';

const App = () => {
  return (
    <Router>
      <NavBar />
      <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about/:id' element={<About />} />
       <Route path='/contact/:id/:name' element={<Contact />} />
      </Routes>
    </Router>
  );
};
export default App;

@@@ NavBar.jsx-
import React from 'react';
import { Link } from 'react-router-dom';

const NavBar = () => {
  return (
    <ul>
      <li><Link to="/">Home</Link></li>
      <li><Link to="/about/1">About</Link></li> 
      <li><Link to="/contact/10">Contact</Link></li>
    </ul>
  );
};

export default NavBar;

@@@ Home.jsx-
import React from 'react';

const Home = () => {
  return <h3>Home Page</h3>;
};
export default Home;

@@@ About.jsx-
import React from 'react';
import { useParams } from 'react-router-dom';

const About = () => {
  const { id } = useParams();

  return (
    <>
      <h3>About Page</h3>
      <p>ID: {id}</p>
    </>
  );
};

export default About;

@@@ Contact.jsx-
import React from 'react'
import { useParams } from 'react-router-dom';

const Contact = () => {
  const {id,name}= useParams()
  return (
    <>
    <h3>Contact Page</h3>
    <p> ID: {id} & {name}</p>
    </>
  )
}
export default Contact;
```

**# form error**

```
import { useState,useReducer } from "react";

const App = () => {
  const initialState = {
    name: '',
    pass: '',
    display: []
  }
  const [err,setErr] = useState({});

  const reducer = (state,action) => {
    switch (action.type) {
      case "NAME":
        return { ...state, name: action.payload };
      case "PASS":
        return { ...state, pass: action.payload }
      case "ADD":
        return { ...state, display: [...state.display, { name: state.name, pass: state.pass }] }
    }
  }
  const [state, dispatch] = useReducer(reducer, initialState);

  const handleAdd = (e) => {
    e.preventDefault();
    dispatch({ type: "ADD" })
    fetChEroor()
  }

const fetChEroor=()=>{
  const showError ={};
  if(!state.name){
    showError.name = "name is requie"
  }
  if(!state.pass){
    showError.pass = 'pass is require';
  }
  setErr(showError)
}

  return (
    <>
      <form onSubmit={handleAdd}>
        <input type="text" value={state.name} onChange={(e) => dispatch({ type: 'NAME', payload: e.target.value })} /> <br/>
        {err.name}
        <input type="number" value={state.pass} onChange={(e) => dispatch({ type: 'PASS', payload: e.target.value })} />
        {err.pass}
        <input type="submit" />
      </form>
      {
        state.display.map((item, index) => (
          <li key={index}>{item.name} & {item.pass}</li>
        ))
      }
    </>
  )
}
export default App;
```

**# colorPicker**

```
import React, { useState } from "react";

const APP = () => {
  const [color, setColor] = useState("#000");
  return (
    <>
      <input type="color" value={color} onChange={(e)=>setColor(e.target.value)}/>
      <div>Selected Color {color}</div>
    </>
  );
};
export default APP;

```


