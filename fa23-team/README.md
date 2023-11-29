## Q2 (Bohan Wang)

### q2-final.ipynb

All data should be downloaded from: https://www2.census.gov/programs-surveys/acs/data/pums/

Because the data before 2016 do not have area information: PUMA, so we choose 5 years data in MA from 2016-2021.

#### Description of variables: 
2016-2018: https://data.census.gov/mdat/#/search?ds=ACSPUMS5Y2018 (Can be searched on this website)

2019-2022: https://www2.census.gov/programs-surveys/acs/tech_docs/pums/data_dict/PUMS_Data_Dictionary_2022.pdf

##### The variables I used:

PUMA: 

    Public use microdata area code (PUMA) based on 2020 Census definition 
    (areas with population of 100,000 or more, use with ST for unique code)
    00100..81003 .Public use microdata area codes

JWTRNS:    

    Means of transportation to work
    bb .N/A (not a worker-not in the labor force, including persons
    .under 16 years; unemployed; employed, with a job but not at
    .work; Armed Forces, with a job but not at work)
    01 .Car, truck, or van
    02 .Bus
    03 .Subway or elevated rail
    04 .Long-distance train or commuter rail
    05 .Light rail, streetcar, or trolley
    06 .Ferryboat
    07 .Taxicab
    08 .Motorcycle
    09 .Bicycle
    10 .Walked
    11 .Worked from home
    12 .Other method

JWTR: 

    Same as JWTRNS but data before 2019 use this name.

RAC1P:

    Recoded detailed race code
    1 .White alone
    2 .Black or African American alone
    3 .American Indian alone
    4 .Alaska Native alone
    5 .American Indian and Alaska Native tribes specified; or
    .American Indian or Alaska Native, not specified and no other
    .races
    6 .Asian alone
    7 .Native Hawaiian and Other Pacific Islander alone
    8 .Some Other Race alone
    9 .Two or More Races

JWMNP:

    Travel time to work
    bbb .N/A (not a worker or worker who worked at home)
    1..200 .1 to 200 minutes to get to work (Top-coded)


_Data should be rename to psam_p25_year.csv and put them in the same dirt._

### Data processes include: 

1. Handle missing values by dropping lines with missing JWMNP.
2. According to the PUMA information on https://www2.census.gov/geo/pdfs/reference/puma/2010_PUMA_Names.pdf and updated information on https://www2.census.gov/geo/pdfs/reference/puma/2010_PUMA_Names.pdf, create two dicts to store the area name and code of PUMA.
3. Find the areas which in all years to analysis their average. Calculate the time difference between black and white of different areas across these years. Use (average * 2 * 5 * 50) / 60 to calculate the travel time difference between B&W each year.
4. To draw Geography graph, I processed the result. Change all the areas names to zip codes, and then draw a graph using tableau. 
5. Draw ring diagrams.


## Question 1 & 4（Yu Liang & Xinyu Zhang)
### Overview
This dataset is derived from the `American Community Survey (ACS) Public Use Microdata Sample (PUMS)` and contains information on the means of transportation to work for different racial groups over the time span of 2013 to 2021.

### Dataset Source
The data can be accessed from the U.S. Census Bureau at the following link: [ACS PUMS Data](https://www2.census.gov/programs-surveys/acs/data/pums/).

### Time Span
The dataset covers the period from 2013 to 2021.

### Variables Description
The following key variables are included in the dataset:

- `JWTR(2013-2018)/JWTRNS(1029-2021) = 02`: This variable indicates that the means of transportation to work is by bus.
- `RAC1P = 1`: This variable represents individuals who identify as White alone.
- `RAC1P = 2`: This variable represents individuals who identify as Black or African American alone.

### Data Preprocess
1. Through observation, I found a lot of missing values in JWTRNS. I preprocessed the data by removing the row with missing values.
2. I calculate the average commute time data of black and white people from 2013 to 2021.
   I also calculate the time difference between black and white from 2013 to 2021.
   I also calculate the difference between blacks and whites for each year using (average commute time * 2 * 5 * 50)/ 60.
4. I use T-test to test the commuting differences between blacks and whites before and after the covid to test whether there was statistical significance and whether the covid had an impact on the commuting differences between blacks and whites.

## Q3-Xiang Li ##

Data from https://www.census.gov/programs-surveys/acs/microdata/access.2020.html#list-tab-735824205. 
We are using the  ACS 5-Year PUMS from 2011 to 2021. 
With Label `RAC1P=1,2,3,4,6,7,9` 

JWTRN for year 2019 to year 2021 and JWTR from 2011 to 2018.

Also, we use the `HISP=1` which identifies the Latinx or not to count for the Latinx group.

For visualization, we only use the matplotlib package in Python.

## Data processing ##

1. Handle missing values by dropping lines with missing JWMNP.
2. According to the PUMA information on https://www2.census.gov/geo/pdfs/reference/puma/2010_PUMA_Names.pdf and updated information on https://www2.census.gov/geo/pdfs/reference/puma/2010_PUMA_Names.pdf, create two dicts to store the area name and code of PUMA.
3. Find the areas which in all years to analyze their average. Calculate the time difference between Latinx and other different race groups of different areas across these years. Use (average * 2 * 5 * 50) / 60 to calculate the travel time difference between B&W each year.
4. Convert all the non-numerical value to int or float
5. Draw ring diagrams.

