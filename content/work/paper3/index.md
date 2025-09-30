---
title: "Chocolate Ratings" 
date: 2025-09-30
tags: ["machine learning", "visualizations"]
author: ["Suhas Sompalli"]
description: ""
summary: "Predicting final ratings of various chocolate products"
cover:
    image: chocolate.jpg
    alt: "Chocolate Banner"
    relative: true
editPost:
    URL: "https://github.com/s-sompalli/chocolate-ratings"
    Text: "github.com/chocolate-ratings"
---


##### Introduction

The Chocolate Bar Ratings dataset, sourced from Kaggle, offers a profile of 1,795 reviews of 440 unique chocolate bars. The set was collected between 2006 and 2017, and each review was submitted by chocolate enthusiasts. The dataset was selected for its relevance to specialty food analysis in regard to origin and quality.

---

##### Model

The dataset comprises the following key features:

| Feature         | Description                                                                 |
|-----------------|-----------------------------------------------------------------------------|
| Company         | Chocolate manufacturer (416 unique)                                         |
| BarName         | Bean origin or bar variant (1,039 unique)                                   |
| REF             | Unique bar identifier                                                       |
| ReviewDate      | Year reviewed (2006–2017)                                                   |
| CocoaPercent    | Cocoa content (%)                                                           |
| Location        | Country of production (60 total)                                            |
| Rating          | Sensory score (1.0 to 5.0)                                                  |
| BeanType        | Cacao variety or blend (41 types; ~50% missing)                             |
| BroadOrigin     | Country of bean origin (100 total)                                          |


The data was voluntarily submitted.    

*Major limitations include*:   
- no reviews post-2017   
- potential bias from enthusiast reviewers     
- approximately 50% of BeanType cells were empty  

---

##### Cleaning


- **Column Standardization**: Removed line breaks and extra spaces; standardized names 
- **Type Conversion**: Transformed CocoaPercent from string (“70%”) to float (70.0); ensured ReviewDate and Rating were numeric.
- **Missing Values**: Replaced 887 missing BeanType entries with “Unknown”; kept one missing BroadOrigin for transparency.
- **Duplicates**: No exact duplicates found; multiple entries for each REF exist
- **Integrity Checks**: Validated all key fields; no out-of-range values in CocoaPercent.

---

##### Analysis

The cleaned dataset enables exploration of several compelling questions:

-  **CocoaPercent vs. Rating**: Investigate whether higher cocoa content correlates with better sensory scores.
	- In general lower cocoa percentages resulted in higher reviews
-  **Temporal Trends**: Examine rating patterns over time.
	- Weak association of ratings creep
-  **BeanType Comparison**: Assess how different cacao varieties perform in average ratings.
	- Generally weak association, perhaps due to missing data
-  **Predictive Modeling**: Explore whether a bar’s Rating can be predicted from CocoaPercent, Origin, and Company.
	- Yes, but high variability
-  **Preference Shifts**: Analyze trends in consumer preference for dark vs. lower-percentage chocolate.
	- Inconclusive

---
