---
layout: post
title:      "Stock Tracker"
date:       2018-01-30 19:03:29 -0500
permalink:  stock_tracker
---


Stock Tracker is a CLI application that allows the user to retrieve an up to date list of undervalued companies which have positive price momentum.

To determine if a company is undervalued, a basic value composite is used. This includes price/sales, price/FCF,  and price/earnings, but not price/book. I chose not to use this due to my skepticism about its worth as a value indicator.

Stocks which qualify as undervalued using the above value composite are then sorted by six month price appreciation and filtered for positive quarter and month performance.

The top 20 results are returned, and can be explored by inputting a number corresponding to each company. This provides detailed financial information on each company.

I was happy with how well Finviz's website worked for scraping. Searches have specific urls, and going through different tabs in the table the search returns also updates the URL. This allowed me to scrape the first page of results as well as pages containing other information I was interested in. 

Here is an example url of what I was scraping from : https://finviz.com/screener.ashx?v=111&f=fa_pe_low,fa_pfcf_low,fa_ps_u3,geo_usa,ta_perf_13wup,ta_perf2_4wup&ft=4&o=-perf26w

It was easier to scrape the dark and light rows seperately, so that's what I ended up doing. After getting the list of companies from my first search, I updated their respective objects when data from seperate scrapes was obtained.

The Stock class itself is fairly simple. It does have a long list of instance variables, though.

I'm happy with how well this project went. I expected to hit a few roadblocks, but there were labs I found  more frustrating than this project. It was nice having freedom in deciding how to make things work, and that made the project enjoyable and easier to get done.

