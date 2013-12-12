# AirPair-Notify

Use this tool to keep yourself up to date on airPair listings.
Truely its just a twitter stream tracker, and you could track anything.
But I am dedicating this to [AirPair][1]... so if you want to name it something else. Fork it.

## SETUP

```shell
gem install terminal-notifier
npm install airpair-notify -g
```

Obtain API credentials from [Twitter][2]

Create an `airpair-notify.json` anywhere you want.
The contents must contain variables like the following.
It must be properly formatted JSON its parsed using `JSON.parse()`.

```json
{
    "growl": {
        "title": "AirPair",
        "sticky": true
    },
    "twitter": {
        "stream": {
            "track": "@airpair #nodejs #mongodb"
        },
        "credentials": {
            "consumer_key": "YOUR_KEY",
            "consumer_secret": "YOUR_SEC",
            "access_token_key": "YOUR_ACCESS_TOKEN",
            "access_token_secret": "YOUR_ACCESS_TOKEN_SECRET"
        }
    }
}
```

`twitter.stream.track` is the phrase that will be used to filter results in the twitter stream.
Make this useful. If your only interested in AirPair listings that are for `nodejs` or `ruby`
be sure to make your track phrase reflect this. `@airpair #nodejs #aws`
An OSX notifcation will be fired off any time a new tweet comes in from AirPair.

## USE

```shell
airpair-notify --file /path/to/airpair-notify.json
```


### TODO

- [ ] Add more commandline options
- [ ] Actually use the AirPairIcon.png
- [ ] Allow deamonization of `airpair-notify` so it can be started and forgotten about.
- [ ] Add instructions for linux
- [ ] Add --help option

[1]: https://www.airpair.com
[2]: https://dev.twitter.com