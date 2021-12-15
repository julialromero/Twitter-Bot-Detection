# Twitter-Bot-Detection

This repo contains scripts to query the Twitter API and construct edgelists for networks representing follow, likes, and @mentions interactions. 
These scripts are: 
  - code/download-mentions-script.ipynb
  - code/download-likes.ipynb
  - code/download-follows-script.ipynb

The data analysis and machine learning code is at code/data-analysis.
These files are named:
  - code/data-analysis/compute-network-metrics.ipynb/
  - code/data-analysis/visualizations.ipynb
  - code/data-analysis/classification.ipynb

Other code files for data cleaning, scratchwork exploring, and fusing follows with likes/mentions are:
  - code/aggregate_weighted_edges.ipynb
  - code/read_edgelists.ipynb

Figures from exploration and network visualization are at code/data-analysis/figures.


Finally, edgelists are in the directories: follows/, likes/, mentions/. The botometer dataset for labelled human and bot accounts is at botometer-labelled-dataset/ginali-2017/.

