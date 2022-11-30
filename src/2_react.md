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

A palindrome is a word, phrase, number, or other sequence of characters which reads the same backward or forward. This includes capital letters, punctuation, and word dividers.

Implement a function that checks if something is a palindrome. If the input is a number, convert it to string first.

**Examples(Input ==> Output)**

      "anna"   ==> true
      "walter" ==> false
      12321    ==> true
      123456   ==> false

***Solution***

```javascript
function isPalindrome(line) {
  let str = String(line);
  let arr = str.split('');
  let reversed = arr.reverse()
  let final = reversed.join('')
  if (final === str){
    return true
  } else {
    return false
  }
}
```


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

## Week challenges (Thursday) 💻

1. **React Santa Wish List** *exercise*

Santa wants to simplify his life and offer children the possiblity to enter their wishlist via an online form.

The form should be a React component and should contain:

* an input field for the child's name (with id 'name')
* * a text area to describe the wish (id: 'wish')
* a drop-down indicating the priority of the wish, from 1 to 5 - default is 1 (id: 'priority')
* the keys in the state to store the corresponding values should be named the same as the element's id
* an onSubmit action calling the function handleSubmit
* a function called handleSubmit, which
   * calls send (a function that is already provided as part of the injected properties props)
   * passes the current state as a parameter to send
   * calls event.preventDefault
* it should be a controlled component (i.e. using onChange to bind input to the component's state)


***Solution***

```javascript
const React = require("react");

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);
    this.handleSubmit = this.handleSubmit.bind(this);
    
    this.state = {name: '', wish: '', priority: 1}
    
  }
  
  handleSubmit(event){
    event.preventDefault();
    this.props.send(this.state);
  }
  
  render() {
    const {name, wish, priority} = this.state;
    return (
      <form onSubmit={this.handleSubmit}>
        <input id='name' value={name} onChange={e => this.setState({name: e.target.value})} />
        <textarea id="wish" value={wish} onChange={e => this.setState({wish: e.target.value})} />
        <select id='priority' value={priority} onChange={e => this.setState({priority: +e.target.value})}>
          <option value='1' />
          <option value='2' />
          <option value='3' />
          <option value='4' />
          <option value='5' />
        </select>
        <button/>
      </form>
    );
  }
};
```
