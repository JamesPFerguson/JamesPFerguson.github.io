---
layout: post
title:      "Music Rater - React / Redux Final Project"
date:       2018-08-18 20:43:10 -0400
permalink:  music_rater_-_react_redux_final_project
---


It's surreal to be done with this project. Redux was surprisingly tough for me to grasp. While I could easily complete any lab involving Redux, I wasn't prepared for hooking it all up myself and knowing **exactly** how everything needed to interact. From all the googling , stack overflow, and blog posts I encountered while researching Redux for the project, I wasn't the only one. For this reason I plan to post another blog soon outlining redux in simple terms, and making sure how everything interacts is explained with the most clarity possible. That post will also include links to resources I found helpful in completely understanding redux.

I was very comfortable with React this project. React makes me love working with HTML, and I imagine other developers feel the same way. React is a great framework and makes Javascript feel so much more natural. I watched a talk given by someone from the React team a few years ago, and the speaker emphasized that React created a separation of concerns rather a separation of languages. It's exactly that, that makes working with React multitudes nicer than working with vanilla JS and HTML.

Let's get into a few quirks I ran into, so that anyone else working on their project won't spend as much time debugging as I did. First,when passing in props via containers, the values I needed were often one level deeper in the JSON than I expected. For example, I needed to write this.props.album_reviews.album_reviews sometimes to get the array I needed, rather than simply writing this.props.album_reviews. The second issue that gave me the most trouble was passing arguments into my actions. I found it necessary to use BindActionCreator from redux, and this allowed me to pass arguments into the action functions.

The app is a simple CR application currently (the UD part of CRUD isn't present, and won't be until I add some features regarding users) that allows users to write reviews for music albums.

I got the CSS to the point where I'm satisfied with it. I did a lot of poking around, read a decent amount of bootstrap documentation, and reviewed some CSS content on Learn.co. After this project I plan to spend time getting slightly more familiar with bootstrap so I get layouts I like more quickly in the future.

If you're struggling with Redux, check back here within a week or two, and hopefully I can help.
