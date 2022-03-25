# cardano-tip-bot
Use [@CardanoTipBot](https://twitter.com/CardanoTipBot) to tip ADA &amp; tokens with Twitter!
Use [Cardano Tip Bot#7235] to tip ADA &amp; tokens with Discord!

## Disclamer / Terms of uses

By using the Cardano Tip Bot you are accepting the following terms :

1. We are not responsible for lost funds or incorrect balances. Use at your own risks!
2. This software is provided to promote engagement in the Twitter [#cardano](https://twitter.com/search?q=%23Cardano) community or any Cardano Discord server in a fun way. 

### Examples of recommended uses of the Cardano Tip Bot
1. Tip a Cardano community member for a positive contribution to the ecosystem.
2. Tip a Cardano community member for answering another community member's question with a helpful answer.
3. Tip a Cardano community member for making a tweet that raises a good debate.

### Examples of what cannot be done when using the Cardano Tip Bot
1. The Cardano Tip Bot should not be used for online crowdfunding or to fund any political party.
2. The Cardano Tip Bot can be used with non-Cardano related tweets, but must not spam these non-Cardano related tweets.
3. The Cardano Tip Bot should not be used in a disrespectful manner to insult or discriminate against another Twitter or Discord user
4. The Cardano Tip Bot should not be used in any criminal/illegal activities.
5. Store and/or transfer large amount of ADA or tokens.

If any of the above situations are detected or reported, the account will be blocked from the bot temporarily or permanently.

## Limitations / Processing delays
Twitter version :
This bot uses the Twitter API which has some limits:

1. Direct messages can only be queried once per 60 seconds so it can take a little while before receiving an answer.
2. Tweets have a rate limit of 300 per 3h so the bot might not reply to a tweet after it successfully sent a tip.
3. If the bot can't reply to a tweet, it will try to like the tweet instead. Again, this has a rate limit of 1000 likes per 24h so the bot might not be able to like a tweet after successfully sending a tip.

You can always send `!balance` as direct message to the bot to validate that your tip went through.

Twitter and Discord version :
1. When handling deposits/withdrawals, the bot transfers to/from the master wallet and waits for a certain amount of blocks before updating your balance. This is to make sure your deposit/withdrawal isn't rollbacked by a chain fork.

## Supported assets
1. ada (6 decimals: `0.000000`) 1 ada = 1000000 lovelace
2. lovelace (0 decimal) 1 lovelace = 0.000001 ada
3. HOSKY (`2aa9c1557fcf8e7caa049fa0911a8724a1cdaf8037fe0b431c6ac664.50494759546f6b656e`) (0 decimal)

Any decimals beyond what's declared above will be discarded. For example `1.23456789 ada` is automatically converted to `1.234567 ada` (ie `1234567 lovelace`).

`k`, `M` and `B` suffixes are supported everywhere you can specify an amount:
- `k` = * 1 000 (`1k HOSKY` = `1000 HOSKY`)
- `M` = * 1 000 000 (`1M HOSKY` = `1000000 HOSKY`)
- `B` = * 1 000 000 000 (`1B HOSKY` = `1000000000 HOSKY`)

## Fees
1. Deposit fee: 0.1 developer ada + network transaction fee (about 0.18-0.20 ada)
2. Withdrawal fee: 0.1 developer ada + network transaction fee (about 0.18-0.20 ada)
3. Tip: Free!

## How it works

Each Twitter user or Discord user gets assigned its own, unique deposit address. The user sends $ada & supported assets to its deposit address to funds its balance. CardanoTipBot will move these funds to a central wallet and update the user's balance in the internal database. The user can now tip other users. The user can also withdraw its $ada & assets at any time.

![HowItWorks.drawio.svg](HowItWorks.drawio.svg)

It is not possible to link your Twitter and Discord account at the moment, but it may be possible in the future. 

## How to use
### Direct/Private messages
On Twitter, you can send a direct message to [@CardanoTipBot](https://twitter.com/CardanoTipBot) to create and view information about your wallet:

On Discord, you can send a private message to <b>Cardano Tip Bot#7235</b> to create and view information about your wallet:

<b>WARNING FOR DISCORD USERS : Make sure the Discord username is <b>Cardano Tip Bot#7235</b>. If the identifier after Cardano Tip Bot is not #7235, it might be a SCAM.</b>

1. `!info` will return the following message:

    ``` 
    USE AT YOUR OWN RISKS!
    WE ARE NOT RESPONSIBLE OF LOST FUNDS!
   
   BY SENDING A COMMAND TO THE BOT, YOU AGREE TO THE TERMS OF USE MENTIONED IN THE BOT GUIDE.
    
    Please refer to the user guide in my profile's description for how to use me.

    Your balance is:
    7.952868 ADA
    2000000 HOSKY

    Minimum withdrawal amount: 2.0 ADA
    Withdrawal fee*: 0.1 ADA

    Available commands:
    
    !balance
    Show your balance
    
    !info
    Show this message
    
    !deposit
    Show your deposit address & activate the monitoring of your deposit address for the next 3 hours
    
    !withdraw <address or $handle> <amount> <asset>
    Withdraw ADA & assets

    * Plus an extra network fee of about 0.2 ADA to move to/from master wallet
    ``` 
    
2. `!balance` will return the following message:
  
    ``` 
    Your balance is:
    7.952868 ADA
    2000000 HOSKY
    ``` 
    
3. `!deposit` will return the following message:

    ``` 
    USE AT YOUR OWN RISKS!
    WE ARE NOT RESPONSIBLE OF LOST FUNDS!
   
   BY SENDING A COMMAND TO THE BOT, YOU AGREE TO THE TERMS OF USE MENTIONED IN THE BOT GUIDE.
    
    Please refer to the user guide in my profile's description for how to use me.
    
    Your deposit address is: addr1qxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
    
    Your deposit address will be monitored for the next 3 hours. You will need to message me again to restart the monitoring.
    
    You will receive a message when a deposit is processed.

    Assets supported for deposits*:
    - HOSKY (2aa9c1557fcf8e7caa049fa0911a8724a1cdaf8037fe0b431c6ac664.50494759546f6b656e)

    Recommended deposit amount: 2.0 ADA
    Deposit fee**: 0.1 ADA
    
    * Any deposit containing an unsupported asset will be returned MANUALLY, minus deposit fee**

    ** Plus an extra network fee of about 0.2 ADA to move to/from master wallet
    ```

4. `!withdraw <address or $handle> <amount> <asset>` will allow you to send the `<amount> <asset>` to an `<address>` where:

    - `address or $handle` is a shelley address you own or your ADA $handle **that is not an exchange**
    - `amount` is the amount you want to withdraw
    - `asset` is the asset you want to withdraw

    Multiple amount and assets can be specified in the following format `amount asset[, amount asset[,...]]`. Valid examples:
    
    - `3 ada`
    - `1000 lovelace`
    - `3 ada, 1000000 hosky`
    - `1000000 hosky`
    
    The complete command could look like `!withdraw addr1qxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx 3 ada, 1000000 hosky` or `!withdraw $your_ada_handle 4 ada`

### How to tip on Twitter?
You can tip someone by replying to one of their tweet: `@CardanoTipBot !tip <amount> <asset> [message]` where:

- `amount` is the amount you want to tip
- `asset` is the asset you want to tip
- `message` is an optional text

### How to tip on Discord?
Before tipping someone make sure the bot is on the Discord Server by checking for user <b>Cardano Tip Bot#7235</b>.

You can tip someone by sending the following message in a public Discord channel : `!tip @DiscordUser <amount> <asset> [message]` where:
- `@DiscordUser` is the tag of the person you want to tip
- `amount` is the amount you want to tip
- `asset` is the asset you want to tip
- `message` is an optional text
- 
The complete command could look like `@CardanoTipBot !tip 3 ada, 1000000 hosky wow great work, thank you!` on Twitter or `!tip @DiscordUser 3 ada, 1000000 hosky wow great work, thank you!` on Discord.

### Twitter specific commands
1. `.@CardanoTipBot !giveaway <duration> <assets>` allows you to distribute `<assets>` equally among everyone who replies to the tweet in the next `<duration>` timeframe. It can only be used when posting a new tweet (not a reply and not a retweet). For examples:
    - `.@CardanoTipBot !giveaway 15m 1000000 HOSKY` will distribute a total of 1 000 000 HOSKY split equally among everyone who replies to the tweet in the next 15 minutes
    - `.@CardanoTipBot !giveaway 1h30m 10 ADA, 1000000000 HOKSY` will distribute a total of 10 ADA and 1 000 000 000 HOSKY split equally among everyone who replies to the tweet in the next 1 hour and 30 minutes
    
    **NOTE: The dot (`.`) before `@CardanoTipBot` is important!**

### Discord specific commands
1. `!rain <duration> <assets>` allows you to distribute `<assets>` equally among everyone who sent at least one message in the last `<duration>` timeframe in the channel. For examples: 
    - `!rain 15m 1000000 HOSKY` will distribute a total of 1 000 000 HOSKY split equally among everyone who sent a message in the channel in the last 15 minutes
    - `!rain 1h30m 10 ADA, 1000000000 HOKSY` will distribute a total of 10 ADA and 1 000 000 000 HOSKY split equally among everyone who sent a message in the channel in the last 1 hour and 30 minutes
    
## Roadmap
### Phase 1 ✅ 2022-01-29
- Twitter integration ✅ 2022-01-29
    - Deposit assets ✅ 2022-01-29
    - Tip other users ✅ 2022-01-29
    - Withdraw assets ✅ 2022-01-29

### Phase 2
- [$handle](https://adahandle.com/) ✅ 2022-02-11
- Discord integration ✅ 2022-01-30
    - Deposit assets ✅ 2022-01-30
    - Tip other users ✅ 2022-01-30
    - Withdraw assets ✅ 2022-01-30

### Phase 3
- More Discord integration (surprises 😉)

### TBD
- Hydra integration
    - Remove central database
    - Tipping is done on-chain
    - Allow user to retrieve their private keys (seed)

## FAQ
<details>
  <summary>I made a deposit, but my account was never credited.</summary>
    
  1. Make sure the bot still scans your deposit address. To reduce load on the servers, addresses without activity are not scanned after 3 hours. You can DM `!deposit` to [@CardanoTipBot](https://twitter.com/CardanoTipBot) to enable the scanning of your deposit address again.
  2. Make sure you deposited enough $ada to pay the fees to transfer to the master wallet. Each UTxO needs at least 1.0 $ada attached so if you deposited exactly 1.0 $ada the bot can't transfer to the master wallet. You can check your deposit address balance on [cardanoscan.io](https://cardanoscan.io). You can also send more $ada to cover the fees. A safe amount to deposit is 1.5 $ada. 
  3. Contact [@QCPOLstakepool](https://twitter.com/QCPOLstakepool) for assistance. 
</details>
  
<details>
    <summary>Can I send/withdraw multiple assets in the same command?</summary>

Yes, multiple amount and assets can be specified in the following format `amount asset[, amount asset[,...]]`. Valid examples:

- `3 ada`
- `1000 lovelace`
- `3 ada, 1000000 hosky`
- `1000000 hosky`
</details>

## Like the bot? Support us!
If you like bot and would like to support us, you can:
1) Tip the bot on Twitter (reply `@CardanoTipBot !tip 1 ada` to a tweet by @CardanoTipBot)
2) Stake some ADA with [QCPOL](https://pool.pm/c2b8bff5160dd75149f2cae0955698550e8cf0d390025b26a9508a3e)
