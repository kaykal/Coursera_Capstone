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
