---
layout: post
title:      "Redux Made Simple (Part 1)"
date:       2018-08-31 15:13:10 -0400
permalink:  redux_made_simple
---


Putting together Redux for the first time is somewhat overwhelming. When I didn't 100% understand what the code I was typing was doing, it frustrated me even more. This post aims to help people in similar situations.

We'll start at the top. With Redux, and Index.js file for your application should look something like this

![](https://imgur.com/nuYrpOehttp://)

Your App will be wrapped in the Store, which is where Redux keeps all the state in your React application. Provider is an import from the react redux library which takes a store prop. This makes your store available to everything inside App.


Here is the code for creating a Redux store.

![](https://imgur.com/Q3Q9PVzhttp://)

```
import { combineReducers } from 'redux';
import reviewsReducer from './ReviewsReducer';
import albumReviewsReducer from './AlbumReviewsReducer';
import artistsReducer from './ArtistAlbumsReducer';
import homeReducer from './HomeReducer';

const rootReducer = combineReducers({
    reviews: reviewsReducer, album_reviews: albumReviewsReducer, artist_albums: artistsReducer, clicked: homeReducer
  })

 export default rootReducer
```


Thunk is necessary for returning functions in your actions, so that you can do things asynchronously (AJAX). The window arguments being passed into createStore are only necessary if you want to use Redux DevTools. The RootReducer returns the product of calling combineReducers in your reducers index file. Let's take a look at mine.

```
import { applyMiddleware, createStore } from 'redux';
import thunk from 'redux-thunk';
import rootReducer from './reducers/index';

const store = createStore(
  rootReducer,
  window.__REDUX_DEVTOOLS_EXTENSION__ &&
  window.__REDUX_DEVTOOLS_EXTENSION__(),
  applyMiddleware(thunk)
);

export default store;
```


![](https://imgur.com/ciJtF2lhttp://)
 
 In this file, I'm importing multiple reducers that I wrote for different state keys. These reducers are seperate because they handle different parts of the state, and the models return to them in the actions are also different. We'll get to the actions soon. For combineReducers, I named my keys the same as the keys that the reducers handled, and then passed the reducers themselves in as the value. Finally, this is exported so that when actions are dispatched to our store, it's aware of every reducer.


