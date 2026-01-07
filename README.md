NYC Subway and Store Closures After COVID

Why did I make this project???

After seeing some NYC neighborhoods still struggling while others bounced back, I was wondering if subway stations help nearby stores survive equally everywhere. Or are some areas just getting hit harder, even with good access to transit?

What I Actually Found (this was surprising)

The Bronx lost way more stores near subways than Manhattan. The Bronx was at 38.9%. Manhattan was at 34.0% That 5% gap is bigger than I expected. Crazy.
One station in Queens which is Beach 44 St had 66.7% of nearby stores close. If you do the math that's 2 out of every 3 stores gone. 
Brooklyn which was at 37.6% was closer to the Bronx than to Manhattan, which I didn't expect.
Stations with only a few stores nearby had really jumpy numbers and that makes sense but good to see in the data.

How did I Figure This Out??

So first I Got the data from NYC OpenData because it has the store locations and the subway stations.
I Cleaned it up in Python. This means that I removed missing addresses and kept the important columns
the first try was too slow because my code did 22 million distance calculations and took forever
I did some research and found BallTree. This helped me learn about spatial indexing. because I did this it now it runs in seconds
Counted "closed" stores as ones with Expired, Surrendered, or Revoked licenses because adding the extra keywords will stop skews in my final data

i made some charts to actually see the patterns

Stuff I'm Still Thinking About

 The data isn't perfect. An "Expired" license might mean the store actually closed... or it might mean they just didn't renew their paperwork. I'm counting it as closed, but that could overcount a bit.

another thing to consider is that 0.25 miles seemed like a good "walking distance" cutoff but maybe some people walk farther? i Could maybe try like 0.5 miles or something next time to compare.

my biggest surprise was that I thought having a subway station nearby would be the main thing helping stores. But if that were true, all boroughs would have similar numbers. The neighborhood itself seems to matter more than I guessed.

What Does This Project Show????

i Worked with real city data that was all over the place and it was not clean like  textbook examples
I found a performance problem which was the slow code and found a better way, which is balltree
i made charts that actually help tell the story and represent my results
i am Thinking about what the data can't tell me, not just what it can. like how some stores may have the expired license but not be closed. 

If You Want to Run This

Open analysis.ipynb in Google Colab
It'll ask for two CSV files which is the subway stations and NYC business licenses. The files can be found using these two links. subway 

stations: https://data.ny.gov/Transportation/MTA-Subway-Stations/39hk-dx4f/about_data

business licenses: https://data.cityofnewyork.us/Business/Issued-Licenses/w7w3-xahh/about_data
Go to the links and export the files as csv files. The first cell will prompt you to add these files.

Run the cells top to bottom. I added notes explaining what each chunk does
The results CSV gets saved with all the station-by-station numbers

This was my first real spatial analysis project. I built it in Google Colab over a couple weeks. 

This project was fully done in Google Colab and exported here for sharing.
