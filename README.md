# project-2-
Brandon &amp; Stephanie 

# Media ETL-

Purpose: extract, load and transform datasets concerning different kinds of media. We will clean and join these together, as well as examine popular genres in each. We want to see if there’s any overlap between these different categories.   

Datasets(taken from Kaggle): 
Netflix Originals: https://www.kaggle.com/luiscorter/netflix-original-films-imdb-scores 

Anime: https://www.kaggle.com/vishalmane10/anime-dataset-2022 

Youtube: https://www.kaggle.com/ammar111/youtube-trending-videos-analysis/data 

---Before you begin---
Import pandas, datetime, sql alchemy. 
Create a Postgres database called media.

---Objective---
Process and clean 3 csvs and generate a 4th combined table that will be exported to the media database. 

---Anime Table---
Drop nulls and duplicates.
Rename name column to Title.
Reset the index, this will generate a column called "index" leave as is. 

Use the datetime library to convert the given time to release year.
Extract only the year and leave as string. 
Refer to the images folder for how the cleaned table should look like. 


---Netflix Table---
Drop nulls and duplicates.
Rename columns to match Anime table.
Import requires encoding = "ISO-8859-1"
If the datetime includes a word example "August" use "%B" instead of "%M"
Some lines will separate the date by "." instead of ",". Replace all "." with ",".
Reset the index this will generate a column called "index" leave as is. 
Add column called "Type" and fill with value "Netflix"


Use the datetime library to convert the given time to release year.
Extract only the year and leave as string. 
Refer to the images folder for how the cleaned table should look like.


---Youtube Table---
Drop nulls and duplicates.
Rename columns to match Anime Table
Reset the index this will generate a column called "index" leave as is. 
Add column called "Type" and fill with value "YT Video"

Use the datetime library to convert the given time to release year.
Extract only the year and leave as string. 
Refer to the images folder for how the cleaned table should look like.


---All Media Table---
Append all 3 previous tables together.
Drop nulls and duplicates.
Drop index column.


---Final step---
Export all 4 tables using the toSQL method and SQL Alchemy engine
Inside PGAdmin assign them primary keys as follows:
All_Media primary key is Title
Anime primary key is index.
Neflix primary key is index.
Youtube/US primary key is index.

