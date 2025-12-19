%%%%% RTK

```
%%% store.js-
import { configureStore } from "@reduxjs/toolkit";
import todoReducer from './TodoSlice';

const store = configureStore({
    name: "TODO",
    reducer: {
        todoReducer
    }
})
export default store;

%%%% index.js-
import React from "react";
import ReactDOM from "react-dom";
import App from "./App";
import { Provider } from "react-redux";
import store from "./store/Store";

ReactDOM.render(
  <Provider store={store}>
    <App />
  </Provider>,
  document.getElementById("root")
);

%%%% TodoSlice.js-
import { createSlice } from "@reduxjs/toolkit";

const todoSlice = createSlice({
  name: "todo",
  initialState: {
    input: "",
    display: [],
    edit: null,
  },
  reducers: {
    setInput: (state, action) => {
      state.input = action.payload;
    },
    addOrUpdateItem: (state) => {
      if (state.edit !== null) {
        state.display = state.display.map((item) =>
          item === state.edit ? state.input : item
        );
        state.edit = null;
      } else {
        state.display.push(state.input);
      }
      state.input = "";
    },
    deleteItem: (state, action) => {
      state.display = state.display.filter((_, index) => index !== action.payload);
    },
    editItem: (state, action) => {
      state.input = action.payload;
      state.edit = action.payload;
    },
  },
});
export const { setInput, addOrUpdateItem, deleteItem, editItem } = todoSlice.actions;
export default todoSlice.reducer;

%%%% App.jsx-
import React from "react";
import { useSelector, useDispatch } from "react-redux";
import {
  setInput,
  addOrUpdateItem,
  deleteItem,
  editItem,
} from "./store/TodoSlice";

const App = () => {
  const dispatch = useDispatch();
  const { input, display } = useSelector((state) => state.todoReducer);


  const handleAdd = () => {
    dispatch(addOrUpdateItem());
  };

  const handleDelete = (index) => {
    dispatch(deleteItem(index));
  };

  const handleEdit = (item) => {
    dispatch(editItem(item));
  };

  return (
    <>
      <input
        type="text"
        onChange={(e) => dispatch(setInput(e.target.value))}
        value={input}
      />
      <button onClick={handleAdd}>Add</button>
      {display.map((item, index) => (
        <div key={index}>
          {item}
          <button onClick={() => handleEdit(item)}>Edit</button>
          <button onClick={() => handleDelete(index)}>Delete</button>
        </div>
      ))}
    </>
  );
};

export default App;
```


