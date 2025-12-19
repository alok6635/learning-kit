# drap drop-
```
# app.js-
import React, { useState } from 'react';
import DrapDrops from './DrapDrops';

const App = () => {
     const initialData = {
      Todo:[
        "create design",
        "mock text",
        "write unit test",
        "intergate payment"
      ],
      "In Progress":[
           "development flow",
           "implement row",
           "final developement"
      ],
      completed:[
        "set up CI/CD pipeline",
        "Conduct code reviews",
        "Deploy initial version"
      ]
     }
  return (
    <>
    <DrapDrops initialData={initialData}/>
    </>
  );
};
export default App;

# Drapdrop.jsx-
import React, { useRef, useState } from 'react'

const DrapDrops = ({ initialData }) => {
  const [data, setData] = useState(initialData);
  const dragItem = useRef();
  const dragContainer = useRef();

  const handleDragStart = (e, item, container) => {
    dragItem.current = item;
    dragContainer.current = container;
  };

  const handleDragOver=(e)=>{
    e.preventDefault();
  }

  const handleDragEnd = (e) => {
    e.target.style.opacity = "1";
  };

  const handleDrop = (e, targetContainer) => {
    const item = dragItem.current;
    const sourceContainer = dragContainer.current;
    setData((prev) => {
      const newData = { ...prev };
      newData[sourceContainer] = newData[sourceContainer].filter((i) => i !== item);
      newData[targetContainer] = [...newData[targetContainer], item];
      return newData;
    })
  }

  return (
    <>
      <div className='flex'>
        {Object.keys(data).map((container, index) => {
          return (
            <div key={index} className='container' onDrop={(e) => handleDrop(e,container)}
              onDragOver={handleDragOver}>
              <h2>{container}</h2>
              {data[container].map((item, id) => {
                return (
                  <div key={id} className='each_item' draggable onDragStart={(e)=>handleDragStart(e,item,container)}
                  onDragEnd={handleDragEnd}>{item}</div>
                )
              })}
            </div>
          )
        })}
      </div>
    </>
  )
}
export default DrapDrops;

css-
body {
    background: gainsboro;
}

.flex {
    display: flex;
    justify-content: space-around;
    gap: 10px;

    .container {
        padding: 10px;

        .each_item {
            margin-bottom: 10px;
            background: #ffff;
            border-radius: 5px;
            padding: 20px;

        }
    }
}
```
