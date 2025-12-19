import React, { useEffect, useState } from "react";
import "./index.css";

const LIGHT_DURATION = { red: 1000, yellow: 1000, green: 1000 };
const LIGHT_COLORS = ["red", "yellow", "green"];

const App = () => {
  const [activeLight, setActiveLight] = useState("red");
  const [nextLight, setNextLight] = useState("yellow");

  useEffect(() => {
    const timer = setTimeout(() => {
      switch (activeLight) {
        case "green":
          setActiveLight("yellow");
          setNextLight("red");
          break;
        case "yellow":
          setActiveLight(nextLight);
          break;
        case "red":
          setActiveLight("yellow");
          setNextLight("green");
          break;
        default:
          break;
      }
    }, LIGHT_DURATION[activeLight]);
    return () => clearTimeout(timer);
  }, [activeLight, nextLight]);

  return (
    <div className="traffic_light">
     {
         LIGHT_COLORS.map((item) => (
          <div className={`light ${item} ${activeLight === item ? "active" : ""}`} />
        ))
     }
    </div>
  );
};
export default App;
