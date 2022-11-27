# FosterCareProject

## Introduction

In the United States, there are over 400,000 children in foster care on any given day, with over 200,000 children entering and exiting each year (US ACF, 2021). While many children are placed in group homes, relatives’ homes and other institutions, the largest share (45%) of children are placed in non-relative foster family homes (US ACF, 2021). With the average age of children in foster care being 8.4 years old, placement in non-relative foster family homes is a delicate task. Children in this age group have high developmental needs, and misplacement may result in short and long-term implications on the child’s mental health, emotional wellbeing, academic success and more (Leslie et. al, 2005). 

Despite the large number of cases and effort required to ensure that children are cared for and given the resources they need to succeed, the Child Welfare Departments across the country remain under-resourced and under-funded (Saxena et. al, 2020). In order to maximize their limited resources, some Child Welfare Departments have begun experimenting with algorithmic tools to assist social workers with decision-making, such as predicting risk of maltreatment, recommending placement settings and matching children with foster parents who are able to accommodate for their unique needs (Saxena et. al, 2020). While some tools have been commended by researchers for their improvements to child-outcomes and cost reductions, other analyses skepticize that the tools are biased, difficult to explain, or opaque (Saxena et. al, 2020; Church & Fairchild, 2019; Tushnet, 2018).

A wide range of tools have been deployed to facilitate decision-making and each employs different indicators in their models. Saxena et. al’s (2020) systematic review of research papers regarding algorithms in Child Welfare Services, found that child demographics were discussed in 40% of papers and only 4% of papers discussed foster-parent demographics. According to Mesa (2022), placement in a same-race household can provide foster children with a more familiar environment that leaves them less vulnerable to social isolation and emotional health struggles. As a result, children in mixed-race foster family homes may struggle to form their racial identity and feel connected to family members and members of the community. 

This analysis examines the inclusion of foster child and foster parent demographics into parent-child matching algorithms. In the first analysis, researchers will assess whether demographic variables in the Adoption and Foster Care Analysis and Reporting System 2015 (AFCARS) dataset are representative enough to undermine potential biases in parent-child matching tools if it were used as training data. In the second section, researchers examine whether the use of parent-child matching tools in Kansas resulted in a higher share of same-race placements compared to neighboring states.  

## Research questions
The subsequent sections attempts to answer the following questions: 

RQ1: Is there racial/socioeconomic overrepresentation among foster families? 

RQ2: Is AFCARS representative enough to be used as a training data set?

RQ3: Are states that use placement recommendation models or child-foster parent matching models more likely to take into account children’s wellbeing by placing them in same-race households?

## Literature review


## Methodology 

Note to whomever is doing methodolology: Feel free to change this, I was just messing around
**Data cleaning** 
```python
# Limit columns to the ones that are necessary
foster_data_v2=foster_data_v1[['curplset','st',
'amiakn', 'asian', 'blkafram', 'hawaiipi', 'white', 
'hisorgin', 'untodetm', 'rf1amakn', 'rf1asian', 'rf1blkaa', 
'rf1nhopi', 'rf1white', 'hofcctk1', 'rf1utod','rf2amakn', 
'rf2asian', 'rf2blkaa', 'rf2nhopi', 'rf2white', 'hofcctk2', 
'rf2utod']]
     
```
```python
# Limit observations to those who live in a foster home, non-relative or pre-adoptive home
foster_data_v2= foster_data_v2.loc
[(foster_data_v2['curplset']== 'Foster home, non-relative') 
| (foster_data_v2['curplset'] == 'Pre-adoptive home')]
     
```

## Results

### RQ1: Is there racial/socioeconomic overrepresentation among foster families? 

### RQ2: Is AFCARS representative enough to be used as a training data set?

### RQ3: Are states that use placement recommendation models or child-foster parent matching models more likely to take into account children’s wellbeing by placing them in same-race households?

Given evidence from the literature suggesting that same-race placement is an important indicator of childhood outcomes, we assessed the extent to which social workers with and without algorithmic aid place foster children in same-race households. 

First, we will examine the demographic composition of minority vs. white non-relative foster families. In the dataset, around half of foster children placed in non-relative foster care are white, and the rest are minorities, indicating a relatively even demopraphic dispersion. 

![img1](Child-race.png)

With that said, there are a more white non-relative foster families than homes with at least one minority parent. Since the dataset only includes matched families and does not have access to all foster parent applications, it is conceivable that there are more minority foster families on waiting lists and have not yet been matched with a foster child.

![img1](minority_parent.png)

Using the American population of children placed in non-relative foster families in 2015, 59% are placed in same-race households. However, white children are 10 percentage points statistically significantly more likely to be placed in these households as compared to their minority peers.  

![img1](Total-matching.png)

As outlined in the methodology section, we compared the share of same-race households in Kansas, a state that used algorithmic matching in 2015, with two surrounding states with similar demographic compositions, Colorado and Nebraska. When examining the results in aggregate, it appears that foster children in Kansas, are 12 percentage points more likely than in surrounding states to be placed in same-race households. However, sub-group analysis uncovers a more confounding finding, that minority foster children in Kansas are 8 percentage points significantly less likely to be placed in same-race household, while white foster children in Kansas are significantly more likely to be placed in same-race households. 

![img1](Kansas-compare.png)

On one hand, it is reassuring that a system using algorithmic matching is significantly more likely to place children in same-race households in aggregate. On the other hand, a system using algorithmic matching significantly diminishes the likelihood of a minority foster child being placed in a home that generates long-term positive outcomes. As minority foster children are a particularly vulnerable sub-population, the results suggest that algorithmic matching may disproportionally disadvantage a group that is already systematically disadvantaged. Therefore, the algorthm may appear to its coders and users that it's improving outcomes for foster children, but it is in reality, improving outcomes for white children at the expense of minority children. 

## Limitations
Note to Ludovica: Some placements in Kansas may have occured before their implementation of algorithmic matching. // We grouped minorities into one group rather than matching each minority group for simplicity, but it can be justified because ... // It is possible that Kansas has adjusted their algorithm since 2015

## Discussion


## References
