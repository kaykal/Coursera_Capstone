## Contents
1. [Background and Motivation](#motivation)
2. [Objectives and Key Results](#okr)<br>
  2.1. [Audience](#audience)<br>
3. [Drawbacks of Current Applications](#curr-drawbacks)<br>
  3.1. [What is available now?](#available)<br>
  3.2. [What is not available now?](#not-available)<br>
  3.3. [How to fill the gaps?](#fill-the-gap)<br>
4. [This work](#this-work)<br>
  4.1. [Data Sources](#data-sources)<br>
  4.2. [Part-1 Using Foursquare API to identify interesting locations based on custom criteria](#4sq-api)<br>
      4.2.a. [Technical Details](#part1-tech)<br>
  4.3. [Part-2 Using Machine Learning Techniques to estimate house prices in interesting locations](#house-pr-estimation)<br>
      4.3.a. [Technical Details](#part2-tech)<br>
  4.4. [Learnings](#learnings)<br>
5. [Conclusions and Possible Extensions](#conclusions)

### 1. Background and Motivation<a name="motivation"></a>

This is about a fictitious family of eight - a husband and wife, their three children, the man's parents and his sister. They sold their belongings in their current hometown - a small beautiful village rich in culture and heritage, and moving to California in search of a better life for themselves and their children. A "large" family by California standards and with limited amount of money in hand, he has to find a house large enough to house all of his family and one that also fits his budget. So, here are some of his informal requirements:
  * His mother has issues with her knee and is old. She can't walk up stairs often and hence he prefers to find a house that has enough room at the lower level.
  * His mother is a wonderful cook and in their village was cooking delicacies for families for little money that also went to support the family. 
  * His father was a car mechanic and would like to continue that work part of the week, in order to earn some income. He is old and not advised to drive by himself. They would like to have some car garages close to home so that he could find some part-time work.
  * His wife had worked in two small grocery stores in their village and would like to find a similar job in California. She does not drive. They would like to live in a place close to some grocery stores so that she could find work and could walk or bike to them. 
  * He worked as a primary school teacher during the day, cooked in restaurants during the evenings, waited in bars for part of the night, and was also involved in theatre during the weekends - all to support his awesome family. Since commute time is a lot in California, they would like to live in a neighbourhood that has some of these possibilities if not all, so that he could make enough time for his family while spending enough time to make ends meet.
  * Their youngest son is autistic and needs special care. His eldest daughter is a track and field athlete and has won several awards. They would like to encourage her and believe she has the potential to become an Olympian in future, if property nurtured. They would like to live close to some track stadium so that she could practice and get the necessary coaching.

Although he is moving to the epicentre of technology innovation, he is surprised that there is no website where he could look to purchase a property given the several requirements he has. 

### 2. Objectives and Key Results<a name="okr"></a>

An application to decide where to move your family and live based not only on the cost of housing, but also on
* opportunities for yourself
* opportunities for your immediate family (spouse, parents)
* fueling your childrens' ambitions and creating opportunities for them

#### 2.1. Audience<a name="audience"></a>

This would be an application that could be used by anyone who would like a more generic application that lets them analyze for more kinds of categories rather than just real estate price or touristic importance. It could be a people moving to a new place for work, for starting a new life, with specific interests and needs.

### 3. Drawbacks of Current Applications<a name="curr-drawbacks"></a>

Of course, there are many applications that provide housing prices (Redfin, Zillow, etc.) as well as several applications (Google Maps, Foursquare, Yelp, etc.) that provide information on interesting places around any city or location. But there is more to it than just restaurants, bars, pubs and housing prices. There are many other restrictions that one might need to take into account.

#### 3.1. What is available now?<a name="available"></a>

At the moment, when you want to move your family, say to a particular city or county in the Bay area, cost of living immediately comes to mind. One goes through websites like [Craigslist](https://sfbay.craigslist.org/d/apartments-housing-for-rent/search/apa) to find houses that fit their requirements (size) and budget (rent) or when one wants to permanently relocate to an area one would look at websites like [Redfin](https://www.redfin.com/) or [Zillow](https://www.zillow.com/) to find houses that fit their requirements (size, school district, etc.) and budget (home prices). Besides ratings of different schools in the area, they also provide detailed history of the property itself, detailing when it was built, renovated, what kind of heating it has, an estimate of monthly mortgage payments, etc. Further, one could filter the houses based on several of these parameters to narrow down one's search.

#### 3.2. What is not available now?<a name="not-available"></a>

But all of these websites, though they are geared towards catering to the needs of customers main interests (school quality for their kids, price, etc.) they hardly cater to the needs of the individuals. Of course, they might advertise the house being closer to "Silicon Valley tech companies" or "Apple's Spaceship" or walkable from "Marina Green", but if you are a family trying to work several jobs to make ends meet, it doesn't provide you how many restaurants or grocery stores are nearby where family members could work part-time during the evenings to provide for one's family. Neither does it provide information on the kinds of activities (like a swim school producing Olympians, etc.) that one would want in order to nurture their potential. This leads to the families trying to gather this information through word-of-mouth or by trying to assemble information gathered from several disparate sources of information which is both time-consuming and error prone.

#### 3.3. How to fill the gaps?<a name="fill-the-gap"></a>

There are disparate sources of information available through various websites. In order to stitch these together, I will use the knowledge learnt during the past few weeks and come up with an application that, even if not perfect, would cover much of the ground and would serve as a platform to build more things on. 

### 4. This Work<a name="this-work"></a>

In this work, we try to bridge some of the gaps mentioned above. We use two main sources of data which provide disparate pieces of information and use the data science skills acquired during the course to stitch the pieces into a single useful application. There are two main parts to this exercise:

1. Part-1: In this effort, we use Foursquare API to identify interesting locations around a given set of possible addresses. As mentioned above looking for interesting locations may mean different things to different people. While the currently available applications cater to the mostly widely sought after interests like restaurants and night life, it doesn't cater to the more important needs of finding a second part-time job in a grocery store or mexican restaurant or a special needs school or a swimming pool to train for Olympics, which may all be important for someone making a move to a new city.

2. Part-2: Having identified interesting locations from Part-1 above, one would want to estimate the housing prices in the different interesting locations. The COVID pandemic has caused a huge migration of people from cities to suburbs and less expensive cities causing a major shift in real estate prices. So, learning from historic prices is going to give us a wrong estimate. However, Redfin allows us to download current listings (houses listed for sale) as a csv file. This would provide the most recent prices and could be used to estimate the current amount one would have to spend.

#### 4.1. Data Sources<a name="data-sources"></a>

The problem we are trying to solve involves data gathering from a variety of sources. The main challenge and handicap of all of the current websites is that not all the information is present in one dashboard or platform for the family head of our fictitious family to filter and narrow his search. We will primarily use two main sources of data and mention a third one (which is not being used in this project, but was analyzed and the analysis would be presented in the final presentation). The main sources of data we would be using in this project includes:

  * Home prices (of "current" listings) from [Redfin](https://www.redfin.com/)
  * Venue data from [Foursquare API](https://developer.foursquare.com/docs/api-reference/venues/categories/)
  * California School data from [CA School Dashboard](https://www.cde.ca.gov/ta/ac/cm/#)
  
##### Why Redfin over Others?<a name="why-redfin"></a>

The main reason for choosing Redfin although there are various other similar websites is the ease of data collection. Websites like Craigslist are difficult to gather data from (even while using python scrapping libraries like BeautifulSoup). Further Craigslist is not as well trusted for expensive purchases. Websites like Zillow and MLS Listings, though very popular and trusted require us to scrap the webpage in order to collect and refine the data. On the other hand, Redfin allows you to search the data and download the data as a .csv file right away from the search page. I did not know about this feature until I started working on this project and it is very useful for anyone looking at such data (and until the feature exists). I am pointing to the feature in the screen-capture below: <br>

![Download Redfin data](./assets/redfin_data_csv_download.PNG)

<br>

##### Why Foursquare API?<a name="why-foursquare"></a>

Although I knew about Foursquare and the quality of their data, I had never used their API until the last few weeks when the course introduced us to using Foursquare API. The quality of the data is much more reliable (the location data, rather than reviews) and it is provided in a structure that is very ameanable to parse automatically. The [venue categories](https://developer.foursquare.com/docs/build-with-foursquare/categories/) provided by the API is very comprehensive (although there were certain categories that I could not find or did not have enough entries around my own locality) and it provides all the necessary ingredients for the solution to the problem we are trying to solve. We can also iterate over nearby locations (given an anchor location) which is very handy when you want to find all the restaurants (target venues) near to a given restaurant (anchor venue). I have used this extensively in the project.
