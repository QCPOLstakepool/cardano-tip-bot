# cardano-tip-bot
Use @CardanoTipBot to tip ADA &amp; tokens with Twitter!

## Supported assets
1. ada / lovelace
2. HOSKY (`2aa9c1557fcf8e7caa049fa0911a8724a1cdaf8037fe0b431c6ac664.50494759546f6b656e`) 

## Fees
1. Deposit fee: 0.1 ada + network transaction fee (about 0.18-0.20 ada)
2. Withdrawal fee: 0.1 ada + network transaction fee (about 0.18-0.20 ada)
3. Tip: Free!

## How to use
### Direct messages
You can send a direct message to @CardanoTipBot to view information about your wallet:

1. `!info` will return the following message:

    ``` 
    USE AT YOUR OWN RISKS!
    WE ARE NOT RESPONSIBLE OF LOST FUNDS!

    Documentation: https://github.com/QCPOLstakepool/cardano-tip-bot

    Your balance is:
    7.952868 ADA
    2000000 HOSKY

    Your deposit address is: addr1qxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx

    Only deposit supported assets*:
    - HOSKY (2aa9c1557fcf8e7caa049fa0911a8724a1cdaf8037fe0b431c6ac664.50494759546f6b656e)

    Minimum withdrawal amount: 2.0 ADA
    Deposit fee**: 0.1 ADA
    Withdrawal fee**: 0.1 ADA

    Available commands:
    !info
    !withdraw <address> <assets>

    * Any deposit containing an unsupported asset will be returned MANUALLY, minus deposit fee**

    ** Plus an extra TX fee of about 0.2 ADA to move to/from master wallet
    ``` 
    
2. `!withdraw <address> <assets>` will allow you to send the `<assets>` to an `<address>` where:

    - `address` is a shelley address you own **that is not an exchange**
    - `assets` is a single or multiple assets in the following format `amount asset[, amount asset[,...]]`. Valid examples:
        - `3 ada`
        - `1000 lovelace`
        - `3 ada, 1000000 hosky`
        - `1000000 hosky`
    
    The complete command could look like `!withdraw addr1qxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx 3 ada, 1000000 hosky`

### Tweets
You can tip someone by replying to one of their tweet: `@CardanoTipBot !tip <assets>` where `assets`:

- `assets` is a single or multiple assets in the following format `amount asset[, amount asset[,...]]`. Valid examples:
    - `3 ada`
    - `1000 lovelace`
    - `3 ada, 1000000 hosky`
    - `1000000 hosky`
    
The complete command could look like `@CardanoTipBot !tip 3 ada, 1000000 hosky`
