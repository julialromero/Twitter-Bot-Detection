1. Download botometer datasets: https://botometer.osome.iu.edu/bot-repository/datasets.html
    
    This paper has an overview of datasets hosted by Botometer: https://arxiv.org/pdf/1911.09179.pdf
    
    - botwiki-2019 -- Self-identified bots from https://botwiki.org. Labels and user objects.
        - 698 bots, 0 huumans

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

3. Compute network properties:
    ...