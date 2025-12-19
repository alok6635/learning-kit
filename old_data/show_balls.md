**# show ball in the display**

@App.js-
import React, { useState } from "react";
import "./index.css"; 

const App = () => {
  const [balls, setBalls] = useState([]);

  const handleClick = (e) => {
    const rect = e.target.getBoundingClientRect();
    const x = e.clientX - rect.left;
    const y = e.clientY - rect.top;
    setBalls([...balls, { x, y }]);
  };
  return (
    <div className="container" onClick={handleClick}>
      {balls.map((ball, index) => (
        <div key={index} className="ball"
          style={{
            left: `${ball.x}px`,
            top: `${ball.y}px`,
          }}
        ></div>
      ))}
    </div>
  );
};
export default App;

@index.css-
.container {
    position: relative;
    height: 100vh;
  }
  .ball {
    position: absolute;
    width: 20px;
    height: 20px;
    background-color: red;
    border-radius: 50%;
  }
  


