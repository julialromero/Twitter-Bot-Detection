1. Download botometer datasets: https://botometer.osome.iu.edu/bot-repository/datasets.html
    
    This paper has an overview of datasets hosted by Botometer: https://arxiv.org/pdf/1911.09179.pdf
    
    - botwiki-2019 -- Self-identified bots from https://botwiki.org. Labels and user objects.
        - 698 bots, 0 humans

    - cresci-rtbust-2019 -- Manually annotated bot and human accounts. Labels and user objects.
        - 353 bots, 340 humans

    - vendor-purchased-2019 -- Fake follower accounts purchased from several companies. Labels and user objects.
        1087 bots, 0 humans

    - midterm-2018 -- Manually labeled human and bot accounts from 2018 US midterm elections. Labels and processed user objects.
        - 42446 bots, 8092 humans

    - gilani-2017 -- Manually annotated human and bot accounts. Labels and user objects.
        - 1090 bots, 1413 humans

    - varol-2017 -- This dataset contains annotation of 2573 Twitter accounts. Annotation and data crawl is completed in April 2016.
        - 733 bots, 1495 humans



2. Create network data structures with networkx
    Each node is a data point. For each node we need to define some network around it. This network could be  6, 20, or X degrees of separation from the given node. We will create networks based off the following inter-account interactions obtained from the Twitter API. 

    Limitations of this approach:
    - nodes at the Xth degree of separation would be skewed. Only a subset of their neighbors are included.
    - network properties could vary greatly based on value of X. Choosing X would require careful iterative exploration. 

    Networks:
        - Directed: followers / following
        - Directed: likes -- need time series way to quantify
        - Directed: replies -- need time series way to quantify

3. Compute network properties:
    1) Features to calculate:
        - in and out degree centralities
        - clustering coefficient
        - Q / modularity  -- is there assortative mixing / homophily within the network? 
        - can bot accounts be identified thru disassortative mixing behavior? Using attributes such as # followers, # following, # posts/day, response time
        - assortative mixing by node degree
        - I think we should omit metrics that capture number of edges shared with bot accounts since we don't have comprehensive list of labeled bot accounts.


    2) Exploratory Analyis: 
        - compare properties between bot-centered, human-centered, and random generated networks
        
    
    3) Classifier (subject to change): Chose these for simplicity and because we won't have huge dataset.
        - Logistic Regression
        - Random Forest
        - Naive Bayes
        

    4) Explore -- how does classifier performance differ *using only networks metrics listed above* compared to *using networks metrics in addition to extra non-networks features*. Non-networks features including: 
        -daily tweet counts
        -response rates
        -time of day of activities recorded
        -more


    5) Can we create new networks features to capture bot account properties? After EDA and understanding their behavior? Can we create time-series features that capture this?
         
        
        
    