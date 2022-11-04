[![MIT License](https://img.shields.io/apm/l/atomic-design-ui.svg?)](https://github.com/tterb/atomic-design-ui/blob/master/LICENSEs)
![contributors](https://img.shields.io/github/contributors/sravankr96/hcd_proj_part1_common_analysis.svg)
![codesize](https://img.shields.io/github/languages/code-size/sravankr96/hcd_proj_part1_common_analysis.svg) 

# hcd_proj_part1_common_analysis

This repository contains analysis of COVID confirmed cases and masking policies intended for the project part 1 for DATA 512 Human Centered Data Science course at the University of Washington - Masters in Data Science program

# Goal of this Project: Professionalism & Reproducibility

Over the past few years, the global pandemic has had an severe impact on all of us. This had a horrible, disruptive effect on many countries, and it greatly harmed the lives of countless people and their families.  One aspect of the pandemic's datafication that has been challenging to ignore during the past three years. In other words, a lot of data about the personal cost of the pandemic has been acquired, collated, and presented. With the aid of this information, we have the chance to look into the epidemic from a number of different perspectives in order to understand how it has impacted both individuals and society. 

We will be focusing on the analysis of one specific US county in this project - New Haven, CT, US.

## Datasource Information

1. RAW_us_confirmed_cases.csv: The RAW_us_confirmed_cases.csv file from the Kaggle repository of John Hopkins University COVID-19 data. This data is updated daily. You can use any revision of this dataset posted after October 1, 2022.
2. cdc_masking_mandates_county.csv: The CDC dataset of masking mandates by county. Note that the CDC stopped collecting this policy information in September 2021.
3. mask-use-by-county.csv: The New York Times mask compliance survey data.

## Repository Structure:
Here are the main folders in our github data-512-homework_1 repository:
```bash
hcd_proj_common_analysis
├── README.md
├── Reflection_Statement.pdf
├── Visualization_Explanation.pdf
├── data
│   ├── CT_NewHaven_mask_mandate.csv
│   ├── RAW_us_confirmed_cases.csv
│   └── mask-use-by-county.csv
├── notebooks
│   └── hdc-512-part1-COVID_common_analysis.ipynb
├── part1_analysis_viz.png
└── requirements.txt
```

We will follow a sequence of steps in this project

## 1. Dependencies and Setup

Python 3.10 is used to develop this project. Python package requirements are automatically installed when you execute the cells in the jupyter notebook.
Before proceeding with the execution of project in jupyter notebook, please replace the below line
```bash
  BASE_PATH = '/Users/sravan/PycharmProjects/DATA-512-HCD/data-512-homework_1'
```

## 2. Data Aquisition

We will be using the above mentioned wikimedia API to fetch the pageview data related to the articles listed in the above mentioned excel file. We will then dump this data in the ``` JSON_data``` folder. We will store all our data in three files one each for mobile access, desktop access, cumulative views of the articles.

We will aslo store the intermediate data in the folder ```intermediate_files```. These files contain data related to the list of articles we are processing here and the csv formatted response data to enable us manually navigate the data in a tabular format and confirm our findings. 

JSON_data/dino_monthly_desktop_201507-202209.json - JSON file containing all articles pages view data for desktop access type
JSON_data/dino_monthly_mobile_201507-202209.json - JSON file containing all articles pages view data for mobile access type
JSON_data/dino_monthly_cumulative_201507-202209.json - JSON file containing the cumulative page views of all articles for both desktop and mobile access type

## 3. Analysis and intermediate files

We will be using the Pandas python library to perform different transformation in our data, starting from datetime conversions to gouping the data by article to find max/min/mean views that we will be further showcasing in the visualizations. Below are the intermediate files that we save to manually explore the data in a tabular format and validate our finding through the scripts.

intermediate_files/articles_list.csv - CSV file containing the list of article titles we process in this project
intermediate_files/dino_monthly_desktop_201507-202209.csv - CSV file containing all articles pages view data for desktop access type
intermediate_files/dino_monthly_mobile_201507-202209.csv - CSV file containing all articles pages view data for mobile access type
intermediate_files/dino_monthly_cumulative_201507-202209.csv - CSV file containing the cumulative page views of all articles for both desktop and mobile 

## 4. Visualizations

We will be using the famous Matplotlib python visualization library here

- Figure showing Maximum Average and Minimum Average articles

The first visualization is a time series for the articles that have the highest average page requests and the lowest average page requests for desktop access and mobile access. The graph has four lines (max desktop, min desktop, max mobile, min mobile).

[Maximum and Minimum average view articles](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/min_max_viewed_articles.png)
![Alt text](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/min_max_viewed_articles.png "Articles with fewest Months of Data")

- Figure showing Top 10 Peak Page Views

The second visualization is a time series for the top 10 article pages by largest (peak) page views over the entire time by access type. The graph has the top 10 for desktop and top 10 for mobile access (20 lines).

[Top 10 articles by views](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/top_10_most_viewed_articles.png)
![Alt text](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/top_10_most_viewed_articles.png "ML Pipeline Hyperparameter Diagram")

- Figure showing articles with fewest months of Data

The third visualization is a time series of the articles that have the fewest months of available data. The plot will have relatively short time series, some may only have one month of data. The graph has the 10 articles with the fewest months of data for desktop access and the 10 articles with the fewest months of data for mobile access.

[Top 10 least view data articles](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/least_view_month_articles.png)
![Alt text](https://github.com/sravankr96/data-512-homework_1/blob/main/figures/least_view_month_articles.png "Articles with fewest Months of Data")

## Missing data and Exception handling

It is possible that few of the articles view data is missing in cases where an article is not available for the date we are looking against. In such cases we have used a generic exception handling to let us know what is the reason of exception and the response from the request to wikimedia API.

## Authors
- [Sravan Hande](https://github.com/sravankr96)

![GitHub Contributors Image](https://contrib.rocks/image?repo=sravankr96/data-512-homework_1)

## License
This work is licensed under MIT license. Read through the attached LICENSE file for more details about the use and distribution of this work.
