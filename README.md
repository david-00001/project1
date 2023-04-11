Part 1: Analysis
Part 2: Layout of repository and descriptions of files





~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ ANALYSIS ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


Question: What portion of a senator’s lobbying contributions come from out of state vs within state.

Based on the pie chart located in david_results/lda_senate_add_out_of_state.ipynb, 3.0% of contributions for 2022 came from within the senator’s state. 31% of contributions came from another state. 66.0% of contributions come from DC. 






Question: Which political party gets more lobbying money for a specific time frame? And what is the impact on elections?

<project1/austin_data_viz/dem_vs_rep.png>

Both Democrats and Republicans have had a negative trend in political contributions since 2014. However, Republicans average slightly higher.

When looking at one year of contributions:

<project1/austin_data_viz/contributions_party.png>

Republicans have a higher variance in their donations, which causes a right skew in the data. This can be seen in the upper limit being at a high level, as well as the mean (pink dotted line) but much further away from the median (solid yellow line). However, Democrats also skew to the right as well, just not as significantly.

<project1/austin_data_viz/Dems_vs_repub_contributions.png>
<project1/austin_data_viz/repub_vs_dem_contributions.png>

When looking at the contributions again by year, and compare it to the number of new senators, it appears that there is a relationship between contribution totals and how successful the opposing party is at electing new senators. For example, when democrats dropped their contributions in 2015, there was a big increase in number of new republican senators. When republicans dropped their contributions in 2021, there was a large increase in new democratic senators.

<project1/austin_data_viz/year_vs_cont.png>

When looking at the relationship between years in office and total contributions, it appears that is a positive trend, however, the correlation is very weak with a r value of .20.





Question: Does gender have an effect on contributions?

According to the data provided by congress.gov, females averaged more in contributions from 2013 to 2022. This is especially true in 2014, when the total contribution for females was over $600,000 whereas the male contribution for that same year was slightly under $400,000. Female Democrats and Independent females averaged the most contributions throughout the 10 years this data goes through and female Republicans averaged slightly less than their male counterparts. There is a  limitation to this data and the first being that there are unidentified genders. Due to how the gender was pulled, anyone who did not select an honorific name was placed as unidentified. All output graphs are stored under congress_csv. 





Question: Does the average contribution to a political party vary significantly across multiple states?

My research was intended to investigate the average number of contributions made to political campaigns across different states. With this in mind I sought to view if there is a connection between contribution amounts received across multiple states. By using data collected from the FEC Commission I was able to gather my data and make some diagrams to display my results for the contributions per state. Looking at the data collected, Wisconsin has the largest number of contributions between 2016-2020. With close contenders including New York, North Carolina, and Nevada. In my research I focused on viewing the contribution information for Colorado and Wisconsin. For the state of Colorado I found the main recipients of these contributions to be Gail Schwartz ($19,010.30), Diane Bush ($58,933.98), Michael Bennet ($605,034.00), and Mark Udall ($1,389,663.00). 

Collectively Mark Udall accounted for over 67% of the overall contributions received, Michael Bennet with 29.2%, Diane 0.9%, and Gail with 2.8%. Looking at my original data of contributions per state I thought it would be interesting to break up the contributions received by candidates for Wisconsin being that it was the state that received the largest number of contributions. The top recipients for contributions for the state of Wisconsin include: Feingold 18.4% ($821,824.00), Mandela Barnes 14.8% ($624,040.56), Russ 43.4% ($1,844,899.00), and Tammy Baldwin 26.2% ($1,170,659.00). Gathering this data didn’t come without its share of issues. While collecting the initial sample to use for my dataframe there were many samples that had to be removed due to ‘NaN’ inputs, this would have had a large impact on my data as a whole because every instance of ‘NaN’ would have been difficult to assign to a state due to the ‘NaN’ input being located in the ‘Contribution State’ column. I believe this data could prove useful for conducting further research on possible reasons why there is a discrepancy between the total contributions a state receives. Lobbyists and candidates could use future research to uncover underlying implications for political participation and campaign finance in different states.
The data graphs that were used in reference above can be found in the fec_bulkdata.ipynb







~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ LAYOUT OF REPOSITORY ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


~~~~~~~~~~~~~~~~~~~~~~ Geography Question and general information ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~ Data Used ~~~
Congress Member information including Name, Political Party, Gender, and Bills Sponsored were pulled using https://api.congress.gov/

Senator lobbying information was pulled using https://lda.senate.gov/api/ and was explored using /lda_senate/lda_senate_exploring_top_levels.ipynb



~~~ Files Used to Pull Data ~~~
Congress Member information (excluding gender and bills) was pulled using political_party.ipynb located at the root directory and was stored at the root directory in legislator_info.csv

Congress Member information (gender and bills) was pulled using Congress Gender.ipynb located at the root directory.

Senate lobbying information was pulled using /lda_senate/lda_senate_contributions.ipynb and was stored in csv files located at /lda_senate/lda_senate_output. The files pulled were merged using /lda_senate/lda_senate_merge_contribution_outputs.ipynb



~~~ Files Used to Clean Data ~~~
Congress Member name information was cleaned up using /congress_gov/congress_gov_clean_name.ipynb

Senate lobbying information was merged together using /lda_senate/lda_senate_merge_contribution_outputs.ipynb (Ended up not using any of this).

Senate_info was merged with Senate Lobbying information using /lda_senate/lda_senate_add_amount_columns.ipynb




~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ Political Party and Time Line Information ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~ Data Used ~~~
Congress Member information including Name, Political Party, Gender, and Bills Sponsored were pulled using https://api.congress.gov/

Senator lobbying information was pulled using https://lda.senate.gov/api/ and was explored using /lda_senate/lda_senate_exploring_top_levels.ipynb



~~~ Files Used to Pull Data ~~~
Congress Member information (excluding gender and bills) was pulled using political_party.ipynb located at the root directory and was stored at the root directory in legislator_info.csv **and then split this into senate_df and house_df to seperate the chambers of Congress. In addition, the data was cleaned and grouped by year to create new_senators_by_year.csv**

Congress Member information (gender and bills) was pulled using Congress Gender.ipynb located at the root directory.

Senate lobbying information was pulled using /lda_senate/lda_senate_contributions.ipynb and was stored in csv files located at /lda_senate/lda_senate_output. The files pulled were merged using /lda_senate/lda_senate_merge_contribution_outputs.ipynb



~~~ Files Used to Clean Data ~~~
Congress Member name information was cleaned up using /congress_gov/congress_gov_clean_name.ipynb

Senate lobbying information was merged together using /lda_senate/lda_senate_merge_contribution_outputs.ipynb and then produced amount_by_registrant.csv and amount_by_honoree.csv at the root directory

**Political party and election data cleaning was done using senate_data_viz.ipyn. Within this kernel senate_info_with_contributions.csv and new_senators_by_year were merged to analayze political contributions with politcal party information. All of the visualizations of data were saved into austin_data_viz







~~~~~~~~~~~~~~~~~~~~~~ Gender Question ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
~~~ Files Used to Pull Data ~~~
Congress Member information (gender and bills) was pulled using Congress Gender Pulling Gender and Bills.ipynb located at the root directory.

Congress Gender Pulling Gender and Bills.ipynb was also used to loop through Bio Guide ID and then create a second API request to pull the names that were attached to the Bio Guide ID


~~~ Files Used to Clean Data ~~~
Congress_Gender_merged with contributions.ipynb was used to combine data from Congress Gender Pulling Gender and Bills.ipynb to create a dataframe and create graphs for the gender data.

Congress_Gender_merged with contributions.ipynb was merged with legislator_info.csv to combine gender and bills information. 

Congress_Gender_merged with contributions.ipynb was then merged with senate_info_with_contributions.csv to combine data to get contributions per senators





~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~ FEC data showing state comparison Question ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

fec_bulkdata.ipynb contains all the code and images used for this question.
