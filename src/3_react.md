# WEEK 3

## Week goal 🏁

Learn about context api & redux

## Subtopics


* Context API and Fetching
* Redux Fundamentals
* Redux Toolkit

## Week challenges (Monday) 💻

1. **Build Search Filter In React**  *exercise*

React code to build a simple search filter functionality to display a filtered list based on the search query entered by the user.

**Example:**

![example](https://camo.githubusercontent.com/bf8f3cb56455725381970003b0d919cf6eda1b545e506001b3951ac24b60d492/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f4c4f4b44683630614376446b364642794c712f67697068792e676966)

***Solution***

```javascript
import React, {useState} from 'react'

function List() {

    const items = [
        'Aston Martin',
        'Lamborghini',
        'Toyota',
        'Bentley',
        'Chevrolet',
        'Alfa Romeo',
        'Porsche',
        'Lotus',
        'Ferrari',
        'Mercedes-benz',
        'Lexus',
        'Mazda',
        'Nissan',
        'Honda',
        'Land Rover',
        'Renault',
        'Tesla',
        'Subaru',
        'Fiat',
        'Ford',
        'Jeep',
        'Rolls Royce',
        'Suzuki',
        'BMW',
        'Mitsubishi',
        'Volkswagen',
        'Volvo',
        'Porsche',
        'Audi',
        'Seat',
        'Kia',
        'Maserati',
        'Cadillac',
        'Mclaren'
    ];

    const [list, setList] = useState(items);

    function filter(e){

        if (e.target.value === "") {
            setList(items);
            return;
          }
          const filtered = list.filter(
            (item) =>
              item.toLowerCase().indexOf(e.target.value.toLowerCase()) !== -1
          );
          setList(filtered);
    }

    return (
        <>
            <input type="text" onChange={filter}/>
            <div>{list.map((item) => <div>{item}</div>)}</div>
        </>
    )
}

export default List
```

## Week challenges (Tuesday) 💻

1. **Fetch Random User Data** *exercise*

## Week challenges (Wednesday) 💻

1. **React Router Blog** *exercise*

## Week challenges (Thursday) 💻

1. Redux lecture





















