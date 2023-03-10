# Kaggle Entries for the GoDaddy: Microbusiness Density Forecasting Contest

The contest can be found [here](https://www.kaggle.com/competitions/godaddy-microbusiness-density-forecasting).

## Goal of the Competition:

The goal of this competition is to predict monthly microbusiness density in a given area. A accurate model is to be trained and developed on the U.S county-level data. 

The developed model will help policymakers gain visibility into microbusinesses, a growing trend of very small entities. Additional information will enable new policies and programs to improve the success and impact of these smallest of businesses.

## Context:

American policy leaders strive to develop economies that are more inclusive and resilient to downturns. They're also aware that with advances in technology, entrepreneurship has never been more accessible than it is today. Whether to create a more appropriate work/life balance, to follow a passion, or due to loss of employment, studies have demonstrated that Americans increasingly choose to create businesses of their own to meet their financial goals. The challenge is that these "microbusinesses" are often too small or too new to show up in traditional economic data sources, making it nearly impossible for policymakers to study them. But data science could help fill in the gaps and provide insights into the factors associated these businesses.

Over the past few years the Venture Forward team at GoDaddy has worked hard to produce data assets about the tens of millions of microbusinesses in the United States. Microbusinesses are generally defined as businesses with an online presence and ten or fewer employees. GoDaddy has visibility into more than 20 million of them, owned by more than 10 million entrepreneurs. We've surveyed this universe of microbusiness owners for several years and have collected a great deal of information on them that you can access via our survey data here.

Current models leverage available internal and census data, use econometric approaches, and focus on understanding primary determinants. While these methods are adequate, there's potential to include additional data and using more advanced approaches to improve predictions and to better inform decision-making.

Competition host GoDaddy is the world???s largest services platform for entrepreneurs around the globe. They're on a mission to empower their worldwide community of 20+ million customers???and entrepreneurs everywhere???by giving them all the help and tools they need to grow online.

Your work will help better inform policymakers as they strive to make the world a better place for microbusiness entrepreneurs. This will have a real and substantial impact on communities across the country and will help our broader economy adapt to a constantly evolving world.

## Dataset Description:

In this competition, the challenge is to forecast microbusiness activity across the United States, as measured by the density of microbusinesses in US counties. Microbusinesses are often too small or too new to show up in traditional economic data sources, but microbusiness activity may be correlated with other economic indicators of general interest.

As historic economic data are widely available, this is a forecasting competition. The forecasting phase public leaderboard and final private leaderboard will be determined using data gathered after the submission period closes. You will make static forecasts that can only incorporate information available before the end of the submission period. This means that while we will rescore submissions during the forecasting period we will not rerun any notebooks.

## File Descriptions:

A great deal of data is publicly available about counties and was not attempted to be gathered here.

1. **train.csv**

   - row_id - An ID code for the row.
   - cfips - A unique identifier for each county using the Federal Information Processing System. The first two digits correspond to the state FIPS code, while the following 3 represent the county.
   - county_name - The written name of the county.
   - state_name - The name of the state.
   - first_day_of_month - The date of the first day of the month.
   - microbusiness_density - Microbusinesses per 100 people over the age of 18 in the given county. This is the target variable. The population figures used to calculate the density are on a two-year lag due to the pace of update provided by the U.S. Census Bureau, which provides the underlying population data annually. 2021 density figures are calculated using 2019 population figures, etc.
   - active - The raw count of microbusinesses in the county. Not provided for the test set.

2. **sample_submission.csv** 
    
    A valid sample submission. This file will remain unchanged throughout the competition.

    - row_id - An ID code for the row.
    - microbusiness_density - The target variable.

3. **test.csv**

    Metadata for the submission rows. This file will remain unchanged throughout the competition.

   - row_id - An ID code for the row.
   - cfips - A unique identifier for each county using the Federal Information Processing System. The first two digits correspond to the state FIPS code, while the following 3 represent the county.
   - first_day_of_month - The date of the first day of the month.

4. **census_starter.csv**
    
    Examples of useful columns from the Census Bureau's American Community Survey (ACS) at data.census.gov. The percentage fields were derived from the raw counts provided by the ACS. All fields have a two year lag to match what information was avaiable at the time a given microbusiness data update was published.

   -  pct_bb_[year] - The percentage of households in the county with access to broadband of any type. Derived from ACS table B28002: PRESENCE AND TYPES OF INTERNET SUBSCRIPTIONS IN HOUSEHOLD.
   -  cfips - The CFIPS code.
   -  pct_college_[year] - The percent of the population in the county over age 25 with a 4-year college degree. Derived from ACS table S1501: EDUCATIONAL ATTAINMENT.
   -  pct_foreign_born_[year] - The percent of the population in the county born outside of the United States. Derived from ACS table DP02: SELECTED SOCIAL CHARACTERISTICS IN THE UNITED STATES.
   -  pct_it_workers_[year] - The percent of the workforce in the county employed in information related industries. Derived from ACS table S2405: INDUSTRY BY OCCUPATION FOR THE CIVILIAN EMPLOYED POPULATION 16 YEARS AND OVER.
   -  median_hh_inc_[year] - The median household income in the county. Derived from ACS table S1901: INCOME IN THE PAST 12 MONTHS (IN 2021 INFLATION-ADJUSTED DOLLARS).


## Evaluation:

The submissions made to the competition are evaluated on [SMAPE](https://en.wikipedia.org/wiki/Symmetric_mean_absolute_percentage_error) between the actual and forecasted values. SMAPE is 0 when the actual and predicted values are both 0.

# Submissions:

|#|Submission Date|Submission Score (Lower is Better)|Leaderboard Position|File Name|
|-|---------------|----------------|--------------------|---------|
|1|30-01-2023|1.8725|1564|Holt-Winters Exponential Smoothing (Additive - 4 Seasonal Periods)|
|2|31-01-2023|1.6479|1515|Holt-Winters Exponential Smoothing (Additive - 2 Seasonal Periods)|
|3|31-01-2023|1.8471|Nan|Holt-Winters Exponential Smoothing (Additive - 3 Seasonal Periods)|
|4|03-02-2023|1.482|1595|Auto ARIMA - Univariate (No Constraints & No Seasonality)|
|5|03-02-2023|1.4659|1594|Auto ARIMA - Univariate (No Constraints & with Seasonality)|