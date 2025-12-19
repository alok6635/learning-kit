<<<<<<< HEAD:react/demo/useEffect.md
```
import { useEffect, useState } from "react"

const App=()=>{
const[count,setCount]=useState(0);
const[data,setData]=useState(10);

useEffect(()=>{
    document.title=`changed the title ${count} times`;
     console.log('title is changed');
}) // calling again and again.

// useEffect(()=>{
//     document.title=`changed the title ${count} times`;
//      console.log('title is changed');
// },[]) // calling on screen load only or one times.

// useEffect(()=>{
//     document.title=`changed the title ${count} times`;
//      console.log('title is changed');
// },[count]) // depent on change in count variable

 return(
    <>
    <h3>count: {count}</h3>
    <h3>data: {data}</h3>
    <button onClick={()=>setCount(count+1)}>add</button>
    <button onClick={()=>setData(count+1)}>Add data</button>
    </>
 )
}
export default App;
```
=======

>>>>>>> 3b036455fc62c14cef64113b32262863d1d86e98:react/old-demo/useEffect/src/App.jsx
