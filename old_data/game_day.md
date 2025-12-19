```
import React, { useState } from 'react';

const App = () => {
  const gamesArr = ["cricket", "football", "hockey"];
  const daysArr = ["weekday", "weekend"];
  const [game, setGame] = useState("");
  const [days,setdays] = useState("");

  return (
    <>
      <h4>Game type</h4>
       {
        gamesArr.map((item, index) => (
          <div key={index}>
            <input type="radio" value={item} onChange={(e) => setGame(e.target.value)} />
            <label>{item}</label>
          </div>))
        }
      <h4>Days</h4>
      {
        daysArr.map((item,index)=>(
          <div key={index}>
            <input type="radio" value={item} onChange={(e) => setdays(e.target.value)} />
            <label>{item}</label>
          </div>
          ))
      }
        <h2>You will play</h2>
        <h3>{days && game ? `${game} on ${days}` : "Please select a game and a day"}</h3>
    </>
  );
};
export default App;

```

