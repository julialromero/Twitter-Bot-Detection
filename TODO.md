1. Download botometer datasets: https://botometer.osome.iu.edu/bot-repository/datasets.html
- twibot-20 -- TwiBot-20 is a comprehensive sample of the Twittersphere and it is representative of the current generation of Twitter bots and genuine users. Per the creator's request, we only provide the sample here. To download the full dataset, please contact the creator directly.
    - Full dataset --> 229,573 users, 33,488,192 tweets, 8,723,736 user property items and 455,958 follow relationships
    - only subset is publicly available,bu can email and ask
    Metadata:
        'ID': the ID from Twitter identifying the user.
        'profile': the profile information obtained from Twitter API.
        'tweet': the recent 200 tweets of this user.
        'neighbor': the random 20 followers and followings of this user.
        'domain': the domain of this user and the domains include politics, business, entertainment and sports.
        'label': the label of this user and '1' means it is a bot while '0' means it is a human. (not included in sample)

- botwiki-2019 -- Self-identified bots from https://botwiki.org. Labels and user objects.

- cresci-rtbust-2019 -- Manually annotated bot and human accounts. Labels and user objects.

- vendor-purchased-2019 -- Fake follower accounts purchased from several companies. Labels and user objects.

- midterm-2018 -- Manually labeled human and bot accounts from 2018 US midterm elections. Labels and processed user objects.

- gilani-2017 -- Manually annotated human and bot accounts. Labels and user objects.

- varol-2017 -- This dataset contains annotation of 2573 Twitter accounts. Annotation and data crawl is completed in April 2016.