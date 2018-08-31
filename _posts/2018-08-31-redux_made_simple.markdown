---
layout: post
title:      "Redux Made Simple"
date:       2018-08-31 19:13:09 +0000
permalink:  redux_made_simple
---


Putting together Redux for the first time is somewhat overwhelming. When I didn't 100% understand what the code I was typing was doing, it frustrated me even more. This post aims to help people in similar situations.

We'll start at the top. With Redux, and Index.js file for your application should look something like this

```JavaScript
import { Provider } from 'react-redux';
import store from './store.js';

ReactDOM.render(
    <Provider store={store}>
        <App />
    </Provider>,
    document.getElementById('root')
);```
