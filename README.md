# School District Analysis

## Overview of the School District Analysis

### Purpose
The purpose of this analysis is to assist Tom, a Board of Elections employee, with an election-audit of the tabulated results for a US congressional voting district in Colorado. His manager, Seth, is asking to automate the process using Python and report the results to a text file. After all votes are counted, we need to generate a vote count report to certify this US congressional race.

## Results

### Source and Files
* The School District Analysis analysis is based on the following data source: [election_results](Resources/election_results.csv).
* The completed election-audit analysis is available here: [PyPoll_Challenge](PyPoll_Challenge.py).

### Software and Application
The software and web-based application used for this analysis are:
* Python 3.7.11
* Anaconda 4.11.0
* Jupyter Notebook 6.4.6

Python files created with Jupyter Notebook are given the .ipynbextension rather than .py, so they cannot be easily read or altered within a typical text editor like VS Code.

### Outcomes
* How many votes were cast in this congressional election?

The total votes in this congressional election is 369,711.  

* Provide a breakdown of the number of votes and the percentage of total votes for each county in the precinct.

The county votes are as follows:

![County_Votes](County_Votes.png)

To generate this county list with its respective number of votes and the percentage of total votes, we first had to create a county list and county votes dictionary in the Python script:
```
county_list = []
county_dictionary = {}
```

A **for loop** was also used to get each county result from the county dictionary.
```    
    for county_name in county_dictionary:

        countyvotes = county_dictionary.get(county_name)

        countyvote_percentage = float(countyvotes) / float(total_votes) * 100

        county_results = (
            f"{county_name}: {countyvote_percentage:.1f}% ({countyvotes:,})\n")
        
        print(county_results, end="") 
```

* Which county had the largest number of votes?

For this election, the largest county turnout was Denver with a total count of 306,055 votes.


## Summary of the School District Analysis
In summary, the election-audit successfully analyzed the election results for a US congressional voting district in Colorado using Python and Visual Studio Code. In general, Python code is easy to write, it can perform complex calculations quickly and can handle large data files. Visual Studio Code, or VS Code, allows you to write, edit, save and execute scripts. 

Congressional elections determine who represents your state in Congress and occur every two years. These midterm elections occur halfway between presidential elections and use the popular vote to choose winners.

The election commission can highly benefit from using software like Python and Visual Studio Code to automate the process of reporting results, especially when they must be run every two years. The Python script provided in this election-audit analysis can be easily used with a few adjustments for any election across the United States. 

Lastly, Python is a powerful tool that allows programmers access, process, manipulate and store large data files. Organizations in many industries can take advantage of it to simplify and automate processes of repetitive calculations to boost efficiency.

