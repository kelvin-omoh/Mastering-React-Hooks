# <u> Mastering React.js Hooks: A Comprehensive Guide 1</u> #

## Introduction

React hooks are functions provided by React, a popular JavaScript library for building user interfaces, that enable you to add state and other React features to functional components. In this article, we would be discussing about `useState`.

### Prerequisite
Before attempting to proceed, have a good knowledge of the following:
 1. JSX & ES6 Js.
 1. spread operation. 
 1. call-backs
 1. conditional statements & ternary operation 

## 1. useState Hook
 `useState` hook is a  React Hook that  allows you to store and manage stateful data within a functional component .
 
 ***The basic structure of a useState hook*** 
- The `Initial value` and
- The `Function to change` (update Function).

**<u>Example:</u>**
In this example we would be making a light bulb to light on and light off .

```js
import React, { useState } from 'react';

const Switch = () => {

    /* 
    const [initalValue ,updateFunction ]= useState(data)
    */
  const [isOn, setIsOn] = useState(false);

  /* 
  The switch's default state is off,
 represented by the initial value of false.
  */

  const handleSwitch = () => {
    /*
    This function is to turn on
    and turn off the switch.
    it's like a toggle function.
    */

    setIsOn((prevIsOn) => !prevIsOn);
    //updateFunction
  };

  return (
    <div 
     className="bedroom"
     style={{ background:
     isOn ? 'yellow' : 'black' }} >

      <h1 className="description" >
      This is a switch
      </h1>

      <button
       className="switch"
       onClick={handleSwitch} >

       Switch on/off
       
       </button>
    </div>
  );
};

export default Switch;

```


> ***Description:*** This example above demonstrates a React functional component for a light switch using the `useState hook` to toggle the switch on and off, changing the background color accordingly.<br>

- The ==update function== <span style="color:blue">"setIsOn( )"</span>   is used to store and mutate every value of the inital state "isOn". 
- The initial state was represented as <span style="color:blue">"prevIsOn" </span> in the callback function, which is still referred to as the ==Inital value== only in the call back function .



***Uses of useState Hook :*** 
1. To keep track of Strings, Like Numbers, Booleans, Arrays, Objects, and other combinations of these.

1. To update state The first element is the initial state, and the second one is a function used to update the state.

<u><b>Note:</b></u> `useState()` cannot work on class component

## When to Use the useState Hook 

You can use the `useState()` hook whenever you need to manage and update state within a functional component


1. Initializing a simple state variable: You can use the `useState()` hook to declare a state variable and initialize it with an initial value. For example: 
```jsx
 const [count, setCount] = useState(0);
  ``` 

2. Updating state based on user interactions: You can use the `useState` hook to update state based on user interactions, such as button clicks or form inputs. For example: 

```jsx
const [name, setName] = useState('');
 const handleInputChange = (event) => {
   setName(event.target.value)
   }
  ``` 

 3. Conditionally rendering components: You can use the `useState` hook to toggle the visibility or presence of certain components based on certain conditions. For example:
  ```jsx
   const [isVisible, setIsVisible] = useState(true);
    const toggleVisibility = () => {
       setIsVisible(!isVisible);
        } 
   ```
4. Implement simple UI components that require internal state management.
```jsx
import React, { useState } from 'react';

const Counter = () => {
  const [count, setCount] = useState(0);
    /* 
       function to increment  the 
       count by every click of
        the button  
    */
  const handleClick=()=>{
    setCount(count + 1)
  }

  return (
    <div>
      <p>Count: {count}</p>

      <button 
          onClick={handleClick}>Increment</button>
    </div>
  );
};

export default Counter;

```

5. Create controlled components that rely on state to maintain the value of form elements.
```jsx
import React, { useState } from 'react';

const ControlledInput = () => {
  const [inputValue, setInputValue] = useState('');

  const handleInputChange = (event) => {
    setInputValue(event.target.value);
  };

  return (
    <input
      type="text"
      value={inputValue}
      onChange={handleInputChange}
    />
  );
};

export default ControlledInput;
```


In general, `useState` is used when you need to manage state in a functional component.


## Conclusion. 
The hook discussed  is  integral to modern React development, enabling you to create concise, reusable, and maintainable code while harnessing the full potential of functional components. In [future  guides](), we will explore additional hooks ( use-Effect,use-Context,use-Ref, ....) to further enhance your React knowledge.



 <!-- Use-Effect hook useEffect is a React hook that enables you to perform side effects in functional components, such as data fetching, DOM manipulation, or subscriptions.

 Understanding the various hooks in React js -->