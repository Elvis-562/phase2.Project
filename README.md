# Determining The Best Performing Type Of Films At The Box Office
## Project Overview
* A detailed findings of which types of films make the most revenue in the box office.
* Clean and explore the different types of datasets and find out which datasets are best suited for this project.
* Merge the different datasets I have decided to use.
* Communicate insights using visualizations, clearly depicting which types of films the head of the movie studio should create in the new movie studio.
## Business Understanding
Project goals:
1. Explore the different datasets showing the reviews,budgets and gross.
2. Find the type of films that perform well in the Box Office.
3. Provide the head of the movie studio with information on which type of movies to create.

Once these goals have been met I will be able to identify the type of films that offer a large revenue to the head of the movie studio as they partake in this new venture.
## Data Understanding
Here i am going to explore the different datasets which include(Bom movie gross csv, im.db, rt.movie.info, rt.reviews.tsv,tmdb.movies.csv,tn.movie_budgets.csv) to find the suitable datasets that would work with this project.

I then loaded the libraries that I would use

```python
import pandas as pd
import seaborn as sns
import matplotlib.pylot as plt
import warnings
warnings.filterwarnings("ignore")
```
I then reviewed the 6 datasets and i decided to work with two datasets.

The datasets include Box Office Mojo(BOM) and the numbers dataset.

I picked the box office mojo dataset since it contains domestic and foreign gross so it helps us know how much money was made locally and internationally.

I picked the numbers dataset(df6) since it contains the production budget and the gross of the films so we can see how much profit the movies are making hence identifying the type of films that won't incur loss and  are popular films among the audiences.
## Data Preparation
I cleaned the (BOM) dataset by fill missing values in column foreign gross with median and dropping rows with minimal missing values.

The numbers dataset contained no missing values but to create more similar columns with the (BOM) dataset I renamed and split some of the columns.

I renamed the column movie to title to match the title column in (BOM) dataset.

I split the column release date to get a column year in the numbers dataset to match the year column in (BOM) dataset.

This is to avoid dealing with a lot of missing values.

I then dropped  the column release date and column month date that i made after splitting release date.

Finally I merged the two datasets.

```python
# merging df2 and df6 which are different databases
#merge with the same column names
#concat=with different data types and because i can't merge with numerical values
# using ignore_index argument so we can create a new index
#using sort  argument inorder to keep the original order

df7=pd.concat([df6,df2],ignore_index=True,sort=False)
df7
```

After merging i further cleaned the data creating uniformity in the column values in domestic gross, foreign gross, worldwide gross and production budget columns.

I filled in the missing values and dropped the columns containing a lot of missing values and the ones i didn't need.

The final step was dropping duplicates with a lot of duplicates in the column title.

## Data Visualization

I am going to display visuals I used in Tableau.
## Visualization 1
!<img width="1848" height="753" alt="Top 10 Highest Grossing Films(1)" src="https://github.com/user-attachments/assets/c7c2d185-a595-47a5-889d-4bdb6ef0afbd" />

This bar chart is showing the top 10 grossing movies.
## Observation
* The top grossing movie is Avatar with (2,776,345,000 billion dollars) made in the box office.
* Majority of the top grossing movies are action movies  so I would advice the head of new movie studio to create action movies.
##  Visualization 2
!<img width="1848" height="753" alt="Top 10 Lowest Grossing Films" src="https://github.com/user-attachments/assets/39a602ce-0ca9-40e9-a3b8-ffc8845b00a6" />

The movies that performed badly in the box office are different genre films suggesting that they were just bad movies.

## Interactive dashboard 1




