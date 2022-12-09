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

React code to fetch from [this](https://jsonplaceholder.typicode.com/users) API random users. You should display the Name, website, email and phone of a random user. Also there should be a Reset button to fetch a new user (For this you need to generate a random number from 1 to 10).

**Example**

![Example](https://camo.githubusercontent.com/64539ff356879af3dbc52c57918a298a91e2383504c64ecb53c9a73ca702b516/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f4259366445473945426643476278424c496c2f67697068792e676966)

***Solution***

```javascript
import React, { useState, useEffect } from 'react'

function Users() {
    const [users, setusers] = useState({})

    const getusers = async () => {
        const number = Math.floor(Math.random() * 10) + 1;
        const url = `https://jsonplaceholder.typicode.com/users/${number}`;
        const res = await fetch(url);
        const usersJson = await res.json();
        setusers(usersJson);
    };

    useEffect(() => {
        getusers();
      }, {});
    
      const reset = async () => {
        await getusers();
      };
    
      return (
        <>
            <div>Users</div>
            <p>Name: {users.name} </p>
            <p>Website: {users.website} </p>
            <p>Email: {users.email} </p>
            <p>Phone: {users.phone} </p>

            <button onClick={() => reset()}>Reset</button>
        </>
      );
}

export default Users
```

## Week challenges (Wednesday) 💻

1. **React Router Blog** *exercise*

## Week challenges (Thursday) 💻

1. Redux lecture





















