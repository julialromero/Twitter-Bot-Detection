1. Download botometer datasets: https://botometer.osome.iu.edu/bot-repository/datasets.html
    
    This paper has an overview of datasets hosted by Botometer: https://arxiv.org/pdf/1911.09179.pdf
    
    - botwiki-2019 -- Self-identified bots from https://botwiki.org. Labels and user objects.
        - 698 bots, 0 humans

    - cresci-rtbust-2019 -- Manually annotated bot and human accounts. Labels and user objects.
        - 353 bots, 340 humans  (tweets in Italian)

    - vendor-purchased-2019 -- Fake follower accounts purchased from several companies. Labels and user objects.
        1087 bots, 0 humans

    - midterm-2018 -- Manually labeled human and bot accounts from 2018 US midterm elections. Labels and processed user objects.
        - 42446 bots, 8092 humans

    - gilani-2017 -- Manually annotated human and bot accounts. Labels and user objects.
        - 1090 bots, 1413 humans (manually annotated)
        - http://www-public.imtbs-tsp.eu/~farahbak/publications/Asonam_17.pdf

    - varol-2017 -- This dataset contains annotation of 2573 Twitter accounts. Annotation and data crawl is completed in April 2016.
        - 733 bots, 1495 humans



2. Create network data structures with networkx
    
    - Each node is a data point. For each node we need to define some network around it. This network could be  6, 20, or X degrees of separation from the given node. We will create networks based off the following inter-account interactions obtained from the Twitter API. 

    - Limitations of this approach:
        - nodes at the Xth degree of separation would be skewed. Only a subset of their neighbors are included.
        - network properties could vary greatly based on value of X. Choosing X would require careful iterative exploration.
- KYLE EDIT: given that this is a real-world social media network, "six degrees of separation" likely holds and would probably give us literally almost all of Twitter -- we probably only need a few degrees of separation at most

    - Networks:
        - Directed: followers / following
        - Directed: likes -- need time series way to quantify
        - Directed: replies -- need time series way to quantify
    - KYLE EDIT: do we necessarily need to worry about time series? quantity of replies and to whom might suffice, regardless of time. Although I guess you don't capture spammy behavior without time series. But perhaps our project should be exploratory, asking "how well can we predict bots SOLELY relying on network attributes, i.e. how much does network science tell us?"
    - JULIA RESPONSE: we could start simple without considering time-series, and instead use frequency to weight the edges (that's what they do in the botometer paper).

3. Compute network properties:
    1) Features to calculate:
        - in and out degree centralities
        - clustering coefficient
        - Q / modularity  -- is there assortative mixing / homophily within the network? 
        - can bot accounts be identified thru disassortative mixing behavior? Using attributes such as # followers, # following, # posts/day, response time
        - assortative mixing by node degree
        - I think we should omit metrics that capture number of edges shared with bot accounts since we don't have comprehensive list of labeled bot accounts.
        - KYLE EDIT: also refer to the list of 1150 features used in the Botometer paper


    2) Exploratory Analyis: 
        - compare properties between bot-centered, human-centered, and random generated networks
    - KYLE EDIT: not sure what you mean by human/bot-centered -- are you referring to the highest-degree node being a human/bot?
        
    
    3) Classifier (subject to change): Chose these for simplicity and because we won't have huge dataset.
        - Logistic Regression
        - Random Forest
        - Naive Bayes
        

    4) Explore -- how does classifier performance differ *using only networks metrics listed above* compared to *using networks metrics in addition to extra non-networks features*. Non-networks features including: 
        - daily tweet counts
        - response rates
        - time of day of activities recorded
        - more


    5) Can we create new networks features to capture bot account properties? After EDA and understanding their behavior? Can we create time-series features that capture this?
         
        
        
    
- Random things:
    - bots have less reciprocated behavior compared to human accounts (botometer paper)