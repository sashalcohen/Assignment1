# Assignment1
Cannabis Licensing Timeline Analysis

This repository contains data, analytic code, and findings that support portions of the upcoming article, “The End of Social Equity in Cannabis,” not yet published.

### Data
This analysis uses the "Current OCM Licenses" spreadsheet, provided by the State Office of Cannabis Management. The spreadsheet consists of data from the Cannabis Control Board, which is the governing body responsible for issuing cannabis licenses at every level of production--seed to sale.

Current_OCM_Licenses_20241129.csv: Raw data of all cannabis business licenses issued in New York State since legalization. The spreadsheet only includes businesses that have recieved "proximity protection." Proximity protection means that the applicant has recieved approval from the state , indicating that the site of the business does not violate any of the spacing requirements: at least 200 feet from a house of worship, 500 feet from a school or community center, and 1000 feet from the nearest dispensary. Some of these applications are still pending even though they have recieved proximity protection, because there are other details that the OCM wants confirmed before they are oficcially ready to do business. I have removed these businesses because they do not have an "issue date," and the purpose of this analysis is to establish a timeline for when these licenses were issued and to whom. 

#### The spreadsheets contain, among others, the following columns relevant to the analysis:

"Issued Date" — The date that the license became active, when the applicant was formally authorized to start doing business with it. These were not initially parsed as datetime objects, so in order to create a timeline I had to make a new column, "Month/Year Issued," and use the datetime dictionary to make it so that Python could read the "Issued Date" as datetimes instead of strings.

"License Type" — This column describes the type of license being issued. Because the goal of this analysis was to gain a better understanding of the licensing rollout and assess the success of the state's landmark "CAURD" program. The CAURD program was XXX. Sorting this column into CAURD and non-CAURD allowed me to differentiate justice-affiliated applicants--people who had been harmed by the war on drugs through cannabis related offenses--and general licenses. 

### Methodology

#### The notebook 2018-09-ftc-analysis.ipynb performs two analyses:

Part 1: Creates a new dataframe that re-classifies the licenses into CAURD licenses and non-CAURD licenses, along with their corresponding issue dates, represented as datetime objects so that further analysis can be performed. 

Part 2: Create a timeline of when applicants were issued licenses, and compare the number of licenses issued monthly to CAURD-holders and non-CAURD holders. This allows me to assess the rate at which CAURD licenses were issued license compared to other licenses, and offer numerical insight into how much the introduction of general licenses has flooded the market. Industry insiders have told me that market saturation is leading to the devaluation of CAURD licenses--meaning that justice-involved applicants are having trouble finding substantial investors, because they no longer have a coveted commodity, one that offers a head start in the legal market.

### Outputs
The results of "Part 2" above are saved as output/word_counts.csv.