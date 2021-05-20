# moon-doge PHP BOT

moon-doge is a PHP bot that will buy DogeCoin on Binance when Elon Musk mention DogeCoin on twitter.

*Be aware that this is for educational purposes only*

Every second it will check the occurence of DogeCoin inside Elon's last tweet. 
When found, it will automatically buy DogeCoin on Binance.
It will convert all the available USDT in the futures wallet of your Binance account (unless you have set AMOUNT) into Doge with the leverage you will have previously set for DOGEUSDT Perpetual. It will also automatically sell when the price hit the target (defined by "TARGET").

It is best to have a dedicated Binance account only for this script.
You will need to create an API key on Binance with Futures enabled. Also a twitter API Key and secret.

## Dependencies

The script is using Composer and needs those two dependencies : 
- CCXT : https://github.com/ccxt
- twitter-api-php from https://github.com/J7mbo/twitter-api-php

All dependencies have to be installed by running `composer install` on the command line.

## Configuration

Set the variables :

BINANCE_API_KEY // your binance API Key (enable futures)

BINANCE_SECRET // your binance API Key secret

TWITTER_API_KEY // twitter API Key

TWITTER_SECRET // twitter API Key secret

TARGET // target price in percent 

AMOUNT // set the amount USDT (if empty it will take the available funds)

## Testing

Before to run the scipt in production, make sure that your Binance configuration will work. To do so, uncomment the line

    //check_binance(); exit;
    
then run the script in terminal.

This will check :

  - your Binance keys

  - The Binance API connection

  - Your USDT balance


## Usage

Run in terminal : 

    php doge.php



![Capture du 2021-04-01 13-13-49](https://user-images.githubusercontent.com/72351273/113289538-a308c780-92f0-11eb-8d56-d551bfde6069.png)

![Capture du 2021-04-01 13-12-10](https://user-images.githubusercontent.com/72351273/113289479-8ff5f780-92f0-11eb-8872-a2a001591f2b.png)

![Capture du 2021-04-01 14-21-08](https://user-images.githubusercontent.com/72351273/113293015-8753f000-92f5-11eb-836b-b01451628288.png)

## Codestyle

The codestyle is enforced by [PHP_CodeSniffer](https://github.com/squizlabs/PHP_CodeSniffer).  
To check the code [Composer](https://getcomposer.org/) has to be installed. Afterwards all dependencies have to be installed by running `composer install` on the command line. Now the codestyle can be checked by running `composer cs`.


## Updates

### 16 April 2021 : 
 
   - you can now define AMOUNT
   
   - check if the tweet is recent (< 1 minute) in case we start the script and Elon last tweet have mentioned dogecoin but it is too late
   
   - added check_binance(); function
        
        
