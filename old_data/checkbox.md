**# CheckBox**

```
import React, { useState } from "react";

const App = () => {
  const [selectedIds, setSelectedIds] = useState([]); 

  const arr = [
    { id: 1, vehicle: "alto"},
    { id: 2, vehicle: "breza" },
    { id: 3, vehicle: "safari"},
  ];
  const handleCheckbox = (id) => {
    setSelectedIds((prev) =>
      prev.includes(id) ? prev.filter((item) => item !== id) : [...prev, id]
    );
  };
  return (
    <>
      {
        arr.map((item) => (
        <div key={item.id}>
          <input type="checkbox"checked={selectedIds.includes(item.id)} onChange={() => handleCheckbox(item.id)}/>
          {item.vehicle} 
        </div>
      ))}
      <div>
        <div>Selected Vehicles: {selectedIds.length}</div>
        {selectedIds.map((id) => {
          const selectedItem = arr.find((item) => item.id === id);
          return (
            <div key={id}>
              {selectedItem.vehicle}
            </div>
          );
        })}
      </div>
    </>
  );
};
export default App;

```

**# select simple Type**

```
import React, { useState } from 'react';

const App = () => {
  const arr = ["Mobile", "Car", "Bike"];
  const [select, setSelect] = useState("");

  return (
    <>
      <select onChange={(e)=>setSelect(e.target.value)}>
        <option disabled>Select items</option>
        {arr.map((item, index) => (
          <option key={index} value={item}>{item}</option>
        ))}
      </select>
      <div>{select}</div>
    </>
  );
};
export default App;

```
