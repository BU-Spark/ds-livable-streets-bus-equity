## Q2

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
5. Draw