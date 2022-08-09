# Movies-ETL


## Background
The task was to create a clean database so that it could be utilized for a hackathon's projects. Wikipedia, Kaggle, and MovieLens data was extracted, transformed and loaded into a SQL database. Once this had been completed the task of automating this data extraction, transforming, and loading was started.

This automated pipeline’s intended purpose was to daily take in new data, perform the appropriate transformations, and load the data into existing PostgreSQL database tables for analyzation.
<br>


## Optimizing the code

A function was created first as a test to create an automated pipeline by converting the data into Pandas DataFrame. Below are displayed results of this function:

- The Wikipedia data converted to a DataFrame.
![wiki_movies_df](/Resources/wiki_movies_df.png)

- The Kaggle Metadata converted into a DataFrame.
![wiki_movies_df](/Resources/kaggle_metadata.png)

- The MovieLens Data converted into a DataFrame.
![wiki_movies_df](/Resources/ratings.png)

The next Notebook was created off of the Wikipedia DataFrame so that after refactoring, extracting and transforming it could merge with the Kaggle metadata.

- `wiki_movie_df` DataFrame prepared for merging.
![wiki_movies_df](/Resources/cleaned_wiki_movies_df.png)

- Listed columns to confirm preparation for merging.
![wiki_movies_df_columns](/Resources/wiki_movies_df_columns.png)


Then another Notebook was created off of the Kaggle and MovieLens DataFrames so that after refactoring, extracting and transforming they could merge with the Wikipedia DataFrame.

- Image of the `movies_with_ratings_df` DataFrame
![movies_with_ratings_df](/Resources/movies_with_ratings_df.png)


- Image of the `movies_df` DataFrame
![movies_df](/Resources/movies_df.png)


Finally, a Notebook was created to load all of the previously created data into a PostgreSQL database. This was to make it easier to access for the hackathon. The following images are output of a SQL query to check if all of the data was converted.

- Movies query with 6,052 rows.
![movies_query](/Resources/movies_query.png)


- *BUG* Ratings query is supposed to say 26,024,289 rows. 

- The create_database Notebook has that 26,024,289 rows were imported

![row_imported_from_nb](/Resources/26024289\ rows\ imported\ proof.png)

- pgAdmin 4 outputs the count as "24289" like it got cut off. 
  - Expanding the cell does not work, and changed the config to allowing larger row numbers in output. Dropped the tables and have reimported a number of times with the exact same results.

![ratings_query](/Resources/ratings_query.png)






<!-- With this the hackathon has a clean and reliable dataset to be analyzed for their projects. -->
