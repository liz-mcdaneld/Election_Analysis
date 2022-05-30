# Election Analysis

## Overview of Election Audit: 
At the request of a Colorado Board of Election employee the purpose of this election audit of  a local congressional election analysis is to;
1. Calculate the number of total votes.
2. Have a complete list of candidates who received votes, and their vote counts and percentages won based upon votes.
3. View County turnouts on voters, and which county had the largest turnout.
4. Determine a candidate winner based upon popular vote.

## Election Audit Results: 
#### The total votes cast during this congressional election are:
- Total Votes: 369,711

#### Broken down by county the votes are:
- Jefferson County Votes: 38,855. Total vote percentage is 10.5%
- Denver County Votes: 306,055. Total vote percentage is 82.8%
- Arapahoe County Votes: 24,801. Total votes percentage 6.7%

The county that had the largest turnout of voters is Denver County with 306,055 votes, making the county carrying 82.8% of the total votes cast.

#### The votes obtained by each candidate are:
- Charles Casper Stockham: 85,213 votes. Total vote percentage is 23%
- Diana DeGette: 272,892 votes. Total vote percentage is 73.8%
- Raymon Anthony Doane: 11,606 votes. Total vote percentage is 3.1%

Based on popular vote the winner of this election is Diana DeGette with 272,892 votes, carrying 73.8% of the total votes cast.

## Election Audit Summary

   In summary the code written for this election created a fast and efficient way to tally votes to find the winner of the election campaign. This code can be applied to future congressional elections, or any election data set so that it can be run in a matter of minutes, or even seconds. The code is written with the best practices method using modular code. This means it can be applied to multiple election datasets without changing the code itself, just the paths to the dataset.

   First, we can apply this code to a different dataset with similar structure. To do this we modify the path to the dataset by using the code 
[file_to_load = os.path.join("..", "Resources", "new_election_dataset.csv")]
The name of the candidates is extracted from the data using Python code [candidate_name = row[2]]. This means that a list of candidate names is not required, allowing this code to be applied to different candidates. The “row” part of the code references where in the data to search for the name and can be changed to match the data by changing it to read [candidate_name = row [i]] where the value of "i" is replaced by the needed row value; 0, 1, 2, 3 etc.

   If there is a name written in and not from the given list, the code:
[if candidate_name not in candidate_options: 
    candidate_options.append(candidate_name)] 
adds the candidate to the list to be counted.

   This code could be modified to find counties that had the least turnout so that business proposal for increasing voter engagement can be applied to those areas. To do so we still use the original code:
[for counties_name in counties_votes:
        votes = counties_votes.get(counties_name)
        votes_percentage = float(votes) / float (total_votes) * 100
        counties_results = (
        f"{counties_name}: {votes_percentage: .1f}% ({votes:,})\n")]. This code gets the county from the county directory, retrieves the county vote, and calculates the percentage of votes for the county. Then we can write an "if" statement to find the losing county by searching for the less than value of the votes cast and assigning that to a value of "losing_county".
        
   As the use for this code changes, we also can change the path the code is saved to by using the code
[file_to_save = os.path.join("analysis", "new_dataset_analysis.txt")] so that it can be saved to the appropriate file.


## Resources
-	Data source: election_results.csv
-	Software: Visual Studio Code 1.38.1, Python 3.6.1
