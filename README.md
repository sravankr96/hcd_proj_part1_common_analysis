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


## Missing data and Exception handling

It is possible that few of the dates does not have any mask mandating information in such cases we are assuming the mask mandating as 'No', meaning there is no masking policy in force at that point of time.

## Authors
- [Sravan Hande](https://github.com/sravankr96)

![GitHub Contributors Image](https://contrib.rocks/image?repo=sravankr96/hcd_proj_part1_common_analysis)

## License
This work is licensed under MIT license. Read through the attached LICENSE file for more details about the use and distribution of this work.
