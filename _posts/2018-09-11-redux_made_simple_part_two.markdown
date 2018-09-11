---
layout: post
title:      "Redux Made Simple (Part Two)"
date:       2018-09-11 04:38:42 +0000
permalink:  redux_made_simple_part_two
---


Let's take a look at the reducers we were passing to the root reducer in our last blog post. 

```
export default function reviewsReducer(state = {
    reviews: []
    }, action) {
    switch (action.type) {
        case 'ADD_REVIEW':
            return { reviews: state.reviews.concat(action.review) }
        case 'FETCH_REVIEWS':
            return {  reviews: action.reviews}
        default:
            return state;
    }
}
```

Our reducer has a default argument for the state, which in this case is an object with a review key. The second param is for an object called action. The action object is where we will tell the reducer what type of action we want to perform, as well as what data we will be passing into the reducer. Your reducer will return the actual state only when an action type not covered by the reducer is passed in. When modifying the state, you will instead return a copy of your state with the completed changes. Lets take a look at our actions, where we pass data to our reducers.


```
export function fetchReviews() {

    return (dispatch) => {
        return fetch('http://localhost:3000/reviews')
            .then(res => res.json())
            .then(response => {dispatch({type: 'FETCH_REVIEWS', reviews: response})}
        )
    }
}

export function addReview(reviewData) {
    return (dispatch) => {
        return fetch('http://localhost:3000/reviews', {
            method: "POST",
            headers: {
                "Content-Type": "application/json; charset=utf-8",
            },
            body: JSON.stringify(reviewData)
        })
            .then(res => res.json())
            .then(response => {
                dispatch({type: 'ADD_REVIEW', review: response})
            })
    }
}
```

You will notice repetition of the word dispatch in this file. This is the function that must be called to dispatch actions to the store (which holds our reducers). We pass dispatch an object, with keys named type, and in this case review and reviews. Review and reviews are used to pass the necessary data to the reducer. In part Three (the final part) we'll take a look at where these functions are being called, and some of the necessary set up for that to happen.
