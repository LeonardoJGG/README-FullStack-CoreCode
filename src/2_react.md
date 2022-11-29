# WEEK 2

## Week goal 🏁

Learn about dynamic rendering, routes & styling

## Subtopics

* Rendering lists
* Dynamic components
* Routes
    * React Router Dom
* Styles
    * CSS
    * Styled Components
    * Frameworks

## Week challenges (Monday) 💻

1. **Is Palindrome?** *exercise*


## Week challenges (Tuesday) 💻

1. **Well Of Ideas** *exercise*

For every good kata idea there seem to be quite a few bad ones!

In this kata you need to check the provided array (x) for good ideas 'good' and bad ideas 'bad'. If there are one or two good ideas, return 'Publish!', if there are more than 2 return 'I smell a series!'. If there are no good ideas, as is often the case, return 'Fail!'.

***Solution***

```javascript
function well(x){
  const filter_good = x.filter(word => word == 'good');
  if(filter_good.length < 1){
    return 'Fail!';
  } else if (filter_good.length < 3){
    return 'Publish!'
  } else {
    return 'I smell a series!'
  }
}
```

## Week challenges (Wednesday) 💻

1. **React Manage Events** *exercise*

**Write a react component that will display the current value of our counter.**

* The counter should start at 0.
* There should be a button to add 1.
* There should also be a button to subtract 1.

We want to be able to see the value of the counter - so it should be rendered! And for your buttons to work they will need an onClick prop.

In your render you should return:

* The counter display element with an id of 'counter', containing the counter value.
* An increment button with an id of 'increment'
* A decrement button with an id of 'decrement'

***Solution***

```javascript
import React, {useState} from 'react';

export class Counter extends React.Component {
  constructor(props) {
    super(props)
    this.state = {counter:0}
    // Your state
    this.sum = this.sum.bind(this);
    this.subs = this.subs.bind(this);
  }
  
  sum (){
    this.state.counter += 1
  }
  
  subs (){
    this.state.counter -= 1
  }
  
  // Your event handlers 
  render() {
    return (
      <div>
        <h1 id='counter'>{this.state.counter}</h1>
          <button id='decrement' type="button" onClick={this.subs}>
            Decrement
          </button>
          <button id='increment' type="button" onClick={this.sum}>
            Increment
          </button>
      </div>
    )
  }
```
