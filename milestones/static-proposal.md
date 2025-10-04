## Description

On September 25, Chicago's Workforce Development Committee passed a proposed ordinance that requires employers to prevent health-related illnesses for workers outdoor, with the exception of some workers, such as firemen and policemen. The proposal will now go to the Chicago City Council to be voted on. 

This begs the question - Who in Chicago are most affected by heat-related illnesses and injuries? Where are they? Which industries do they work for? How has this changed over time? During extreme heat, do non heat-related illnesses and injuries also go up? 

## Data Sources

### Data Source 1: OSHA Severe Injury Report Data

URL: https://www.osha.gov/severe-injury-reports

Size: 866 rows, 28 columns

This dataset contains all severe work-related injuries that employers reported to OSHA between Jan 1, 2015 and March 31, 2025 in Chicago. The dataset provides information on latitude and longitude, industry sector code, event or exposure, source, and nature of the injury, as well as the event date. I will use this to identify heat-related illnesses, as well as events that occurred during days with extreme heat. 

### Data Source 2: Bureau of Labor Statistics Employment Data

URL: https://www.bls.gov/productivity/technical-notes/industry-hours-and-employment.htm

Size: 4,663 rows, 17 columns

This dataset contains annual average of hours worked and level of employment per industry at the 3- and 4-digit NAICS level. This will be used to normalize the rate of injuries per industry. 

### Data Source 3: Local Weather Data

URL: https://prism.oregonstate.edu/explorer/

Size: About 1,088,340 rows, 4 columns

This dataset contains daily temperature information at a 800m by 800m resolution for the United States. I will obtain the data for Jan 1, 2015 to March 31, 2025 for Chicago, and match OSHA injury data based on location and date. I will use this data to identify dates of extreme heat. 

## Questions

1. I'm a bit concerned about using the BLS data to normalize the rate of injury since the BLS data is at the national level. But it's a bit hard to find city- or state-level employment data for different industries. Do you think this approach would be okay? 
   
2. The employer data is not the cleanest because in the serious injury report data, there is no unique employer ID so we would have to use the name variable but since this is manually inputted, sometimes the names have typos or have different variations. I'm thinking of using the mi-chainlink package to identify name groups but I'm wondering if this is going to overcomplicate things. 
   
3. I'm considering expanding my research scope to Illinois rather than just Chicago because the number of serious injuries may not be high enough for me to identify a seasonal pattern. However, I wonder if the weather data size would become too big. It's also available at the 4km by 4km level so I could try that. 