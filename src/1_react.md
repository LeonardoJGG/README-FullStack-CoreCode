# WEEK 1

## Week goal 🏁

Learn about React fundamentals, hooks & input

## Subtopics

* JSX Fundamentals
    * CRA
    * Components
    * props
    * useState
    
* useEffect
* High Order Components
* Handle inputs and forms (Formik)

## Week Challenges (Tuesday)💻

1. **Ensure Question** *exercise* 

Given a string, write a function that returns the string with a question mark ("?") appends to the end, unless the original string ends with a question mark, in which case, returns the original string.

**For example** (***Input --> Output***)

    "Yes" --> "Yes?"
    "No?" --> "No?"
    
***Solution***

```javascript
  function ensureQuestion(s) {

    let validation = s.endsWith('?')

    if (validation == true) {
      return s
    } else {
      return s + '?'
    }
  }
```

2. **Reverse Sentence** *exercise*

Complete the solution so that it reverses all of the words within the string passed in.

**Example** (***Input --> Output***)

    "The greatest victory is that which requires no battle" --> "battle no requires which that is victory greatest The"

***Solution***

```javascript
  function reverseWords(str){
  
    let reverse = str.split(' ').reverse().join(' ')
    return reverse;
  }
```

## Week Challenges (Wednesday)💻

1. **Smallest Integer In Array** *exercise*

Given an array of integers your solution should find the smallest integer.

**For example:**

    Given [34, 15, 88, 2] your solution will return 2
    Given [34, -345, -1, 100] your solution will return -345

You can assume, for the purpose of this kata, that the supplied array will not be empty.

***Solution***

```javascript
  class SmallestIntegerFinder {
    findSmallestInt(args) {
      return Math.min(...args)
    }
  }
```

## Week Challenges (Thursday)💻

1. **Odd Or Even** *exercise*

Given a list of integers, determine whether the sum of its elements is odd or even.

Give your answer as a string matching "odd" or "even".

If the input array is empty consider it as: [0] (array with a zero).

***Examples:***

    Input: [0]
    Output: "even"

    Input: [0, 1, 4]
    Output: "odd"

    Input: [0, -1, -5]
    Output: "even"

Have fun!

***Solution***

```javascript
  function oddOrEven(array) {
    let sum = array.reduce((acc, curr) => acc + curr, 0);
    let mod = sum % 2;

    if(mod == 0){
      return 'even'
    } else {
      return 'odd'
    }

  }
```
