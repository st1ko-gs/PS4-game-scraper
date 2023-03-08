# PS4-game-scraper
Chrome extension that grabs your playstation purchase list and formats it as json data.  For use with importing into a games database like Playnite to search your games easily.

![](https://www.rtsoft.com/PSGameDataScraper/psgamedatascraper.jpg "Screenshot")

I wanted a list of all my Playstation games and couldn't find a way to do that so I wrote this crappy web scaper that pulls the info directly from my Sony account via a Chrome extension.

It puts the data into a text box as a json format string so you can cut and paste it as needed.

Example output:

```{
  "games": [
    {
      "title": "Grand theft auto 5",
      "Size": "90.75GB",
      "PurchaseDate": "7/3/2023",
      "Platforms": [
        "PS4"
      ],
      "productID": "UP0177-CUSA13186_00-JUDGMENTRYUGAENG"
    },
    {
      "title": "Fortnite",
      "Size": "28.64GB",
      "PurchaseDate": "7/3/2023",
      "Platforms": [
        "PS4"
      ],
      "productID": "UP1001-CUSA01401_00-BORDERLANDSHDCOL"
    }, ... and so on
```

# How to use it in

* clone the repo or use the Download zip option and unzip the directory ( PS4-game-scraper-main )  somewhere.
* Enter chrome://extensions into your chrome URL bar
* Enable Developer mode option in the top right
* Click "Load unpacked" in the top left, and choose the PS4-game-scraper-main directory.
* You should now see the extension installed.  Click on its little PS and follow the instructions it gives

Security warning: After using it, go back to chrome://extensions and remove it, and disable developer mode.  Normally you should never install an extension like this for security reasons, but I assume you would here because you know me or have looked at the source code!

# Todo

I probably won't work much on this anymore but here are some issues/problems with it for anybody who wanted to use it as a starting point:

* It asks for too many privileges, it should only need Sony's website.  I tried doing that, but it then no longer gives the "This is the wrong website" warning when you use it on the wrong webpage with how I currently do it
* Instead of using alert() to show progress it should have a nice status window while working
* It's very likely to break given the methods it uses to parse data, web scraping in general sucks, but I don't know another way to get this info
* Should also be gathering data from online trophies, this method could detect more games that you own.  Current method doesn't know about games you've played via real disc
