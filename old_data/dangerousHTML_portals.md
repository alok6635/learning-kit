**#dangerousHTML**

```
import React from 'react';

const App = () => {
  let data = `<p>Here is a new concept</p>`

  return (
    <>
      <div dangerouslySetInnerHTML={{__html:data}}></div>
    </>
  )
}
export default App;
```

**#portals**

```
import React from 'react'
import ReactDom from 'react-dom'

const App =()=>{
  return (
      ReactDom.createPortal(<p>this is a portal</p>,document.getElementById('portal'))
  );
};
export default App;
```
