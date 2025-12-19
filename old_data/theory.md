---------
**# Hooks**
  


**# useReducer**
* managing more complex state management.useReducer Hook is similar to the useState Hook.
   * Syntax- const[state,dispatch]=useReducer(reducer,initalState)
   * useReducer hook accept two value as a parameter(reducer,initalState) & returns two values-A.current state. B. dispatch function.
   * reducer- reducer is a pure function(A- a function always returns a same output if the same arrguments passed. B- does not produce 
     any sideEffect).
* use of reducer function-
    * syntax reducer- const reducer(state,action)=>{return single value/new state}
    * reducer function accept two paremeter(state,action)


**# useEffects**
* it is call when components created ,if state or props update then call but we call control all case ,it is all life cylcle method 
  combination as availavle on class life cycle.

**# Rules of useEffect hook**
```
* component mounting-
* when component initial mount then it call. and when any props & state is change then it call
useEffect(()=>{
  console.log('ss');
})

* componentDidMount-
*  when any  state update then it is not called.
useEffect(()=>{
  console.log('ss');
},[])

* componentDidUpdate-
* when any specific state update then it is called.
useEffect(()=>{
  console.log('ss');
},[count])

* componentUnmount-
 useEffect(()=>{
    return ()=>{console.warn('sdsd')}
  })

```

**# memo & useMemo**
* memo-
   * it is a hoc. it prevent to unnecessary renders. if components renders the same result given the same props. we can wrap your component in a call to 
     React.Memo.
* useMemo-
   * useMemo will only recompute the memorized value when one of the dependencies has changed. accepts the function & array of dependencies  

**# useMemo hook (pure components)**
* useMemo hook returns a memoized value.
* useMemo hook only runs when one of its dependencies update & second parameter to declare dependencies.
* a pure component is considered pure if it renders the same output for the same state and props.
* it extend a class with pure components, there is no need for shouldComponentupdate.
* reactjs pure component class compare current state and props with new props and state to decide whether the react component should re- 
   render itself or not.

**# useCallback hooks**
* useMemo and useCallback hooks are similar.main difference is useMemo returns a memoized value and useCallback returns a memoized 
  function.
* when passed the props and child is wrap the memo but child is re-rendering.then fallow the terms referencial equality(jb page re-render hota hai to function re-create hote hai. means function nya create hua hai ya koe changes hue hai )  
  

**# useRef hook(controlled components)**
* useRef allows access to Dom elements and retains mutable values withouts re-renders.
* access a dom element directly.
* not limited to DOM references can hold any value.
  
**# controlled component & uncontrolled comopnent**

* controlled- components managed by the state in react that called controled componets.
* uncontrolled- omponents not managed by the state in react that called uncontroled componets.it's manage by useRef(function based) 
 class based-createRef.


**# react-router-dom hooks**
* useHistory
* useParams
* useLocation

 **# difference in useEffect & useLayoutEffect**
* useLayoutEffect work in the before painting.It is more synchronous than to useEffect.execution oder define it.no 
  method of Error handling.


---------




