# Alt-Season-Index (introduction)
Small project that i made this summer to emulate the alt season index. <p>
More precisely i wanted to recreate the index that can be found here: https://www.blockchaincenter.net/en/altcoin-season-index/ so that i could have a version of that running locally on my machine, making my life easier if i wanted to use it as an indicator for an investment strategy.
<p>
Another benefit is that i can chose the period more freely (not just 90 days, a month or a year), and can chose how many crypto i want to have in my index (not capped at 50 anymore).
<p>
  
# Navigating the files

[Web_Scraping.ipynb](Web_Scraping.ipynb)
Here is were we use Selenium, beautifullsoup and other libraries to scrape data from the internet to make the Alt Season Index
The website we scrape data from are::

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
  
[Alt_Season_Index.ipynb](Alt_Season_Index.ipynb)
Here is were we acutally calculate the Alt Season Index, by default we use BTC as our crypto to compare against the others (just like it's in the website), but 
the code allows to also use other crypto as a metric (like ETH).

<p>
  
![Example Immage](output.png)

<p>
  
[Final_Code.ipynb](Final_Code.ipynb)
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




