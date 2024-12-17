# Alt-Season-Index (introduction)
A small project that i made this summer to emulate the alt season index. <p>
More precisely i wanted to recreate the index that can be found here: https://www.blockchaincenter.net/en/altcoin-season-index/ so that i could have a version of that running locally on my machine, making my life easier if i wanted to use it as an indicator for an investment strategy.
<p>
Another benefit is that i can chose the period more freely (not just 90 days, a month or a year), and can chose how many crypto i want to have in my index (not capped at 50 anymore).
<p>
  
# Navigating the files

[Web_Scraping.ipynb](Web_Scraping.ipynb)
Here is were we use Selenium, beautifullsoup and other libraries to scrape data from the internet to make the Alt Season Index, the website we scrape data from are:

  ```python
  #We put at DATE the date we are scraping from (yyyymmdd)
  #We load the data for assetbacked token and stable coin so that i can remove them later
  #since they would otherwise interfere with the alt season index
  ```
  ```python 
  https://coinmarketcap.com/historical/DATE/ 
  ```
  ```python 
  https://coinmarketcap.com/view/stablecoin/ 
  ```
  ```python 
 https://www.coingecko.com/en/categories/asset-backed-tokens
  ```


<p>
  
[Alt_Season_Index](Alt_Season_Index.ipynb)
Here is were we acutally calculate the Alt Season Index, by default we use BTC as our crypto to compare against the others (just like it's in the website), but 
the code allows to also use other crypto as a metric (like ETH).

<p>
  
![Example Immage](output.png)

<p>
  
[Final_Code](Final_Code.ipynb)
Here is were we combine the 2 previous files plus a simple strategy that buys crypto when the Alt Season is under 25 and sells them when it's over 75.
You use this code in case you want to automatically update the data and simulate the buy/selling process.
At the start it has some configs:
```python
#Settings
start="20241202" #Start one day previous to the one you want to start from
end="20241211"
Crypto_Alt_Season="BTC" #Crypto that i want to use as an indicator for my ALT season (default BTC)
Crypto_to_invest="ETH" #Crypto that i want to buy and sell
Metric="Price" #Metric of my Alt Season (it can also be Volume)
N_Crypto=50 #Number of Crypto i take into consideration for my ALT season (max 200)
```
[Hystorical Data](Hystorical_Data_CoinMarketCap)
Here we have all the daily data of the top 200 cryptos from 2013/04/28 to 2024/12/11, Github only shows the first 1000 files (so the first 1000 days), you can get future data by running [Final_Code](Final_Code.ipynb) or [Web_Scraping](Web_Scraping.ipynb)

<p>

[Stable_Coin_and_Asset_Backed_Token](Stable_Coin_and_Asset_Backed_Token)
Here we have the list of Stable Coin and Asset Backed Token, so that they can be removed when calculating the Alt Season Index

<p>
  
[Alt_Season_With_50_Crypto](Alt_Season_With_50_Crypto)
This folder contains the 2 time series of the Alt season, one with BTC as a metric, the other with ETH as a metric. It also contains files that are used as a storage of past data, needed when calculating the Alt Season for new days





