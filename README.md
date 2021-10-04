# Election_Analysis
## Project Overview
The Colorado Board of Elections has given the following tasks to complete the election aduit of a recent local congressional election. 
- The voter turnout for each county
- The percentage of votes from each county out of the total count
- The county with the highest turnout

## Resources
Data Source: election_analysis.csv

Software:  Python 3.7.6, Visual Code 1.60.2

## Election-Audits Results
The analysis of the election shoes that:

- There were "369,711" votes cast in the election. 

#### County Votes:
- Jefferson County: 10.5% (38,855)
- Denver County: 82.8% (306,055)
- Arapahoe County: 6.7% (24,801)
- Denver County had the largest number of votes cast. 

#### Candidate Breakdown:
- Charles Casper Stockham: 23.0% (85,213)
- Diana DeGette: 73.8% (272,892)
- Raymon Anthony Doane: 3.1% (11,606)

#### Winner:
- Diana DeGette: 73.8% (272,892)

## Election-Audit Summary:
Election commission can use this code in almost any election to determine percentage of vote each candidate recieved as well as percentage of voter turnout per county. This summary contains only three county's data and three candidates, but the script can be easily expanded to include any number of counties or candidates. For instance, the code below allows for additions to both the number of counties and the number of candidates for extensive data analysis.

```
# For each row in the CSV file.
    for row in reader:

        # Add to the total vote count
        total_votes = total_votes + 1

        # Get the candidate name from each row.
        candidate_name = row[2]

        # 3: Extract the county name from each row.
        county_name = row[1]
        
        # If the candidate does not match any existing candidate add it to
        # the candidate list
        if candidate_name not in candidate_options:

            # Add the candidate name to the candidate list.
            candidate_options.append(candidate_name)

            # And begin tracking that candidate's voter count.
            candidate_votes[candidate_name] = 0

        # Add a vote to that candidate's count
        candidate_votes[candidate_name] += 1

        # 4a: Write an if statement that checks that the
        # county does not match any existing county in the county list.
        if county_name not in county_options:

            # 4b: Add the existing county to the list of counties.
            county_options.append(county_name)

            # 4c: Begin tracking the county's vote count.
            county_votes[county_name] = 0

        # 5: Add a vote to that county's vote count.
        county_votes[county_name] += 1
```
In addition, this section of code above can be amended to include additional data points. For example, this code could be modified to look at different demographics or zip codes in order to analyze voter turnout of different aspects of voting groups. 
