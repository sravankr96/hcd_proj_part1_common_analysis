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
├── LICENSE
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
## 2. Analysis and Visualization

On a high level, we are performing the below transformations, 
1. Merge the mask data and the confirmed cases data, filling missing mask data with 'No'
2. Create derived field - infection rate, which is a gradient of confirmed cases
3. Identify change points using rupture module
4. Identify the dates where mask mandating is changed

Below is the final visual plotted using the above transformed data,

[Image1](https://github.com/sravankr96/hcd_proj_part1_common_analysis/blob/main/part1_analysis_viz.png)
![Alt text](https://github.com/sravankr96/hcd_proj_part1_common_analysis/blob/main/part1_analysis_viz.png)

The plot shows us few interesting findings, we see the first change point around 2020-04, which was the first peak of the pandemic, which pushed the mask mandating and eventually reducing the transmission rate by second change point. The third change point shows an increase in the cases despite the use of masks, this is the peak stage of infection. At the 5th change point, we see an increase, despite that the mask mandating was removed, which might be due to the vaccination spread. At the 6th change pint, it is quite interesting to see why the masks are not mandated despite the peak infection rate at this time, will this be because people are already aware about the pandemic and have been voluntarily following the masking policy without mandating. In summary, we see a major drift in the infection rate during the initial months of the infection, however as we progressed there are many other variables like vaccination, public awareness, remote work etc. that effected the infection change which does not show much correlation with the masking policy.


## Missing data and Exception handling

It is possible that few of the dates does not have any mask mandating information in such cases we are assuming the mask mandating as 'No', meaning there is no masking policy in force at that point of time.

## Authors
- [Sravan Hande](https://github.com/sravankr96)

![GitHub Contributors Image](https://contrib.rocks/image?repo=sravankr96/hcd_proj_part1_common_analysis)

## License
This work is licensed under MIT license. Read through the attached LICENSE file for more details about the use and distribution of this work.
