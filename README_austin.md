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
