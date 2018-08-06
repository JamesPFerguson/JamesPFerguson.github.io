---
layout: post
title:      "Portfolio Tracker - now with AJAX"
date:       2018-08-06 16:56:43 -0400
permalink:  portfolio_tracker_-_now_with_ajax
---


For [this project(]https://github.com/JamesPFerguson/portfolio_tracker_v2) I changed some featues to allow user interaction and DOM changes without a page refresh, Stocks can now be added and reviewed without a page refresh. An Index of all stocks entered into Portfolio tracker can now be pulled on the stocks index page with the click of a button.

I was thankful to experience few major issues coding these changes. Most problems I ran into were solveable with 10-20 minutes of using byebug in ruby or debugger in JS. Most issues arose from incorrect syntax or accidentally adding an unecessary ) or }.

The biggest Issue I ran into when starting the project was that the CSS selectors which were working when I completed the original project were no longer returning anything. Stock information is widely sought out, so I was able to use an API to get my data instead of scraping. This ended up making that part of the code cleaner and much more readable, and much more reliable. I used the [IEX API](https://iextrading.com/developer/docs/). It had all the information I needed and didn't require an account, I recommend it to anyone else that needs to pull stock related info for a project.

I still want to add some styling and additional features to this project, but for now I'm ready to move on and finish up the React section.
