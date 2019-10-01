# Snowdon Summit [Push] Weather App

This project brings together several elements of learning and practical pieces to put together a basic application that will notify you when the forecast on Snowdon looks favourable.

As a long standing user of the website I decided to use MetOffice DataPoint, a way of accessing freely available Met Office data feeds in a format that is suitable for application developers. It is aimed at professionals, the scientific community and student or amateur developers, in fact anyone looking to re-use Met Office data within their own innovative applications.

Access to data includes:

* forecast and observation map layers such as radar and cloud cover for the UK
* forecast and observed site specific data such as temperature, wind speed and direction
* regularly updated text forecasts for mountain weather, national parks and UK regions

Data is available in **XML** or **JSON** formats.

[Link to MetOffice Datapoint](https://www.metoffice.gov.uk/services/data/datapoint/about)

##### Base URL #####
All DataPoint resources have a base URL of http://datapoint.metoffice.gov.uk/public/data/ and must be requested with your API key as a query in the format:

* http://datapoint.metoffice.gov.uk/public/data/{resource}?key={APIkey}

##### UK 3 Hourly Site #####
Specific Broadcast (Over 5000 Sites Across the UK):
(A quality-controlled forecast datafeed out to 5 days):

https://www.metoffice.gov.uk/services/data/datapoint/uk-3-hourly-site-specific-forecast

##### Weather Code Definitions #####

https://www.metoffice.gov.uk/services/data/datapoint/code-definitions

##### API Reference #####
https://www.metoffice.gov.uk/services/data/datapoint/api-reference

##### Get Site List (using my API key) #####

http://datapoint.metoffice.gov.uk/public/data/val/wxfcs/all/datatype/sitelist?key={NotPuttingMyAPIkeyHere}

Snowdon Site is **3308** so the full URI [**JSON**] would be:

http://datapoint.metoffice.gov.uk/public/data/val/wxfcs/all/json/3308?res=3hourly&key={NotPuttingMyAPIkeyHere}

This will be wrapped in an Azure Custom Connector, called from a Logic App using the Built-In Schedule Connector and trigger a push (Twilio?).