# Data Sources and Data Description

## Contents
1. [Data Sources](#data-sources)
  1.1. [Why Redfin over Others?](#why-redfin)
  1.2. [Why Foursquare API?](#why-foursquare)
  2.3. [Why CA School Dashboard?](#why-ca-school-dashboard)

2. [Data Description](#data-description)
3. [Data Acquisition Challenges](#data-acq-challenges)

### Data Sources<a name="data-sources"></a>

The problem we are trying to solve involves data gathering from a variety of sources. The main challenge and handicap of all of the current websites is that not all the information is present in one dashboard or platform for the family head of our fictitious family to filter and narrow his search. We will primarily use two main sources of data and mention a third one (which is not being used in this project, but was analyzed and the analysis would be presented in the final presentation). The main sources of data we would be using in this project includes:

  * Home prices (of "current" listings) from [Redfin](https://www.redfin.com/)
  * Venue data from [Foursquare API](https://developer.foursquare.com/docs/api-reference/venues/categories/)
  * California School data from [CA School Dashboard](https://www.cde.ca.gov/ta/ac/cm/#)
  
#### Why Redfin over Others?<a name="why-redfin"></a>

The main reason for choosing Redfin although there are various other similar websites is the ease of data collection. Websites like Craigslist are difficult to gather data from (even while using python scrapping libraries like BeautifulSoup). Further Craigslist is not as well trusted for expensive purchases. Websites like Zillow and MLS Listings, though very popular and trusted require us to scrap the webpage in order to collect and refine the data. On the other hand, Redfin allows you to search the data and download the data as a .csv file right away from the search page. I did not know about this feature until I started working on this project and it is very useful for anyone looking at such data (and until the feature exists). I am pointing to the feature in the screen-capture below:
![Download Redfin data](./assets/redfin_data_csv_download.PNG)

#### Why Foursquare API?<a name="why-foursquare"></a>

Although I knew about Foursquare and the quality of their data, I had never used their API until the last few weeks when the course introduced us to using Foursquare API. The quality of the data is much more reliable (the location data, rather than reviews) and it is provided in a structure that is very ameanable to parse automatically. The [venue categories](https://developer.foursquare.com/docs/build-with-foursquare/categories/) provided is very comprehensive (although there were certain categories that I could not find or did not have enough entries around my own locality) and it provides all the necessary ingredients for the solution to the problem we are trying to solve. We can also iterate over nearby locations (given an anchor location) which is very handy when you want to find all the restaurants (target venues) near to a given restaurant (anchor venue). I have used this extensively in the project.

#### Why CA School Dashboard?<a name=#why-ca-school-dashboard></a>

CA provides a school dashboard that has a lot of information that could be used to infer demography, quality of schools, qualities in specific subjects (like Math), etc. Further this system apparently put in places recently to replace an archaic system of test scores. I am not sure which system was better, but I used the latest available data. Although the data-set was analyzed I did not want to include the inference in the project as it was a very difficult year to make sense of school data. 

### Data Description<a name="data-description"></a>

### Data Acquisition Challenges<a name="data-acq-challenges"></a>

### Situational Challenges<a name="sit-challenges"></a>

The pandemic caused lots of schools to go virtual and being a passionate teacher myself, I can attest that the quality of virtual education may or may not fit the needs of all of the students and hence any reports on students that come out in 2020 might not propertly reflect the actual capabilties of the students. Further due to the movement of population from expensive neighborhoods like San Francisco (city) to the suburbs and from Silicon Valley to other states (due to remote-work becoming the norm in many tech workplaces), there is a huge demographic shift in schools (one of the goals of analyzing school data was also to infer the demography in the region). 

