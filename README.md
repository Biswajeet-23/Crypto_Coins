# Crypto Coins

Easy to use app which just shows list of **cryptocurrencies**, their present market values along with their **Candle Chart**. I have used [CoinMarketCap API](https://coinmarketcap.com/api/) as datasource for this application. You can bookmark some currencies to watchlist which appear on the  **Watchlist screen**. 


## App Compatibility

Android device running with Android OS 6.0 ([API Level 23](https://developer.android.com/about/versions/marshmallow/android-6.0)) or above. Designed for Phones and NOT for Tablets.


## Rubric followed for the Project

* App queries the `coinmarketcap.com` API to fetch cryptocurrencies and properly parses the JSON Response.
* Each List item displayed by the App for the crypto currencies should contain relevant text and information about the currency. 
* This includes -
	* Current Market value.
	* Candle chart for different time periods.
	* Increase/Decrease in rate percentage.
* Networking operations are handled by Retrofit library.
* Clicking on cryptocurrency redirects to details page.
* On device rotation -
	* The layout remains scrollable.
	* The app saves state and restores the list back to the previously scrolled position.
	* The UI properly adjusts so that all contents of each list item is still visible and not truncated/overlapped.
* When new cryptocurrency data is fetched, the main screen properly updates the new data.
* Check whether connected to internet or not. Also, validate for any occurrence of bad server response or lack of response.


### Things explored/developed in addition to the above defined Rubric

* This app fetches data once from API using `Retrofit` and caches it using `Room`. The watchlist is stored in `SharedPreferences` as list of IDs. It uses **Paging Libaray** for loading data from database in discrete manner and UI is bound with data using `DataBinding`. 
* Used `RecyclerView` in place of `ListView` (to display the cryptocurrencies) for its advantages in performance and easy placeholders for custom item decoration.
* `CardView` for displaying the cryptocurrency content for each cryptocurrency item.
* Components used:
	- Lifecycle - Used by `LiveData`.
	- LiveData - For observing upon data in `ViewModel`.
	- ViewModel - For managing UI data.
	- Room - For persisting data. 
    - Paging- For loading long list or infinite data in `RecyclerView`
	- Navigation - For simplifying navigation using `Fragment`.
	- WorkManager - For running repeated background `Work`. 
	- DataBinding - For binding data with views in layout.
* List of libraries used:
	- [Retrofit](https://square.github.io/retrofit/) : For handling HTTP request and responses.
	- [Glide](https://github.com/bumptech/glide) : Image Loader library.
	- [Room](https://developer.android.com/training/data-storage/room) :  For more robust database access.
	- [Navigation Component](https://developer.android.com/guide/navigation/navigation-getting-started) : Navigating between destinations. 
	- [Picasso](https://github.com/square/picasso) - For loading images into `ImageView`. 
	- [Gson](https://github.com/google/gson) - For converting JSON to POJO and vice versa. 

## Design
Home Page | Details Page | Market Page | Watchlist
--- | --- | --- | --- |
![](https://github.com/Biswajeet-23/Crypto_Coins/blob/https_/github.com/Biswajeet-23/Crypto_Coins/ScreenShots/Home.png) | ![](https://github.com/Biswajeet-23/Crypto_Coins/blob/https_/github.com/Biswajeet-23/Crypto_Coins/ScreenShots/Details.png) | ![](https://github.com/Biswajeet-23/Crypto_Coins/blob/https_/github.com/Biswajeet-23/Crypto_Coins/ScreenShots/Market.png) | ![](https://github.com/Biswajeet-23/Crypto_Coins/blob/https_/github.com/Biswajeet-23/Crypto_Coins/ScreenShots/Watchlist.png)

## Install

* [Download the app](https://github.com/Biswajeet-23/Crypto_Coins/raw/https_/github.com/Biswajeet-23/Crypto_Coins/ScreenShots/app-debug.apk)
* Make sure to turn on the Data network before using the app. 
