---
layout: post
title:      "Portfolio Tracker"
date:       2018-05-20 16:43:30 +0000
permalink:  portfolio_tracker
---


Portfolio Tracker is a Rails app that allows the user to track the contents of their financial portfolio. Users enter a stock ticker and the quantity owned into a form, and the ticker is then scraped on financial websites to collect data about the stock. This stock specific data is accessible on a show page, while the quantity owned, the ticker, and links to see info about the stock or edit the quantity owned are all displayed on the portfolio page.

This project took me much longer than both of other ones. There were multiple join tables involved, and figuring out how I wanted to structure the project took multiple revisions. I was able to get my scraper working properly very quickly though, in part thanks to the experience I had building a scraper from [Stock Tracker](https://github.com/JamesPFerguson/stock_tracker).

Diving deeper into the join tables, the following tables were necessary: Stocks, Portofolios, PortfolioStocks, Categories, StockCategories, and Users. Portfolio objects don't actually contain stock objects, they contain PortfolioStock objects, which contain the ID of the portfolio they belong to as well as the ID of the stock referenced.

Thanks to the way this is structured, only one instance of a stock will ever be created for each stock that exists. So if two accounts both try to add NFLX to their portfolio, two instances of it will not be created in the SQL table. instead, the portfolio stock row created  will simply contain the ID of NFLX the stock.




