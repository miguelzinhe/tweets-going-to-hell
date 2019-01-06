# Tweets Going to Hell

Fork from [koenrh/delete-tweets](https://github.com/koenrh/delete-tweets) with a small modification in env variables. Contribute in koenrh's repository!

Delete tweets (or just replies or retweets) from your timeline, including tweets
beyond the [3,200 tweet limit](https://web.archive.org/web/20131019125213/https://dev.twitter.com/discussions/276).

## Prerequisites

### Configure API access

1. Open Twitter's [Application Management](https://apps.twitter.com/), and create
  a new Twitter app.
1. Set the permissions of your app to *Read and Write*.
1. Set the required environment variables:

```bash
api = twitter.Api(consumer_key="YOUR_CONSUMER_KEY_HERE",
                  consumer_secret="YOUR_CONSUMER_SECRET_KEY_HERE",
                  access_token_key="YOUR_ACCESS_TOKEN_KEY",
                  access_token_secret="YOUR_ACCESS_SECRET_TOKEN_HERE")
```

### Get your tweet archive

1. Open your [Twitter account page](https://twitter.com/settings/account).
1. Scroll to the bottom of the page, click 'Request your archive' (not 'Your Twitter
  data' in the left sidebar!), and wait for the email to arrive.
1. Follow the link in the email to download your Tweet archive.
1. Unpack the archive, and move `tweets.csv` to the same directory as this script.

## Installation

Install the required dependencies.

```
pip install -r requirements.txt
```

## Usage

For example, delete any tweet from before *January 1, 2014*:

```bash
python3 deletetweets.py -d 2014-01-01
```

Or delete all retweets:

```bash
python3 deletetweets.py -r retweet
```
