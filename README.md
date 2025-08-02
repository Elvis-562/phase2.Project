# Determining The Best Performing Type Of Films At The Box Office
## Project Overview
* A detailed finding of which types of films make the most revenue at the box office.
* Clean and explore the different types of datasets and find out which datasets are best suited for this project.
* Merge the different datasets I have decided to use.
* Communicate insights using visualizations, clearly depicting which types of films the head of the movie studio should create in the new movie studio.
## Business Understanding
Project goals:
1. Explore the different datasets showing the reviews, budgets, and gross.
2. Find the type of films that perform well at the Box Office.
3. Provide the head of the movie studio with information on which type of movies to create.

Once these goals have been met, I will be able to identify the type of films that offer a large revenue to the head of the movie studio as they partake in this new venture.
## Data Understanding
Here I am going to explore the different datasets, which include(Bom movie gross csv, im.db, rt.movie.info, rt.reviews.tsv, tmdb.movies.csv, tn.movie_budgets.csv) to find the suitable datasets that would work with this project.

I then loaded the libraries that I would use

```python
import pandas as pd
import seaborn as sns
import matplotlib.pylot as plt
import warnings
warnings.filterwarnings("ignore")
```
I then reviewed the 6 datasets and I decided to work with two datasets.

The datasets include Box Office Mojo(BOM) and the numbers dataset.

I picked the Box Office Mojo dataset since it contains domestic and foreign gross so it helps us know how much money was made locally and internationally.

I picked the numbers dataset(df6) since it contains the production budget and the gross of the films so we can see how much profit the movies are making, hence identifying the type of films that won't incur loss and  are popular films among the audiences.
## Data Preparation
I cleaned the (BOM) dataset by filling  missing values in the column foreign gross with median and dropping rows with minimal missing values.

The numbers dataset contained no missing values, but to create more similar columns with the (BOM) dataset, I renamed and split some of the columns.

I renamed the column movie to title to match the title column in the (BOM) dataset.

I split the column release date to get a column year in the numbers dataset to match the year column in the (BOM) dataset.

This is to avoid dealing with a lot of missing values.

I then dropped  the column release date and column month date that I made after splitting the release date.

Finally, I merged the two datasets.

```python
# merging df2 and df6 which are different databases
#merge with the same column names
#concat=with different data types, and because I can't merge with numerical values
# using ignore_index argument so we can create a new index
#using sort  argument to keep the original order

df7=pd.concat([df6,df2],ignore_index=True,sort=False)
df7
```

After merging, I further cleaned the data, creating uniformity in the column values that are in domestic gross, foreign gross, worldwide gross and production budget columns.

I filled in the missing values and dropped the columns containing a lot of missing values  and the ones I didn't need.

The final step was to drop duplicates, as there were many in the column title.

## Data Visualization

I will display the visuals I used in Tableau.
## Visualization 1
!<img width="1848" height="753" alt="Top 10 Highest Grossing Films(1)" src="https://github.com/user-attachments/assets/c7c2d185-a595-47a5-889d-4bdb6ef0afbd" />

This bar chart shows the top 10 grossing movies.
## Observation
* The top-grossing movie is Avatar with (2,776,345,000 billion dollars) made at the box office.
* The majority of the top-grossing movies are action movies,  so I would advise the head of a new movie studio to create action movies.
##  Visualization 2
!<img width="1848" height="753" alt="Top 10 Lowest Grossing Films" src="https://github.com/user-attachments/assets/39a602ce-0ca9-40e9-a3b8-ffc8845b00a6" />

The movies that performed badly at the box office are different genre films, suggesting that they were just bad movies.

## Interactive dashboard 1
!<img width="1859" height="1199" alt="Movie Gross Dashboard" src="https://github.com/user-attachments/assets/cbe85263-9db7-41c3-9a90-b90d49b2497b" />

This dashboard shows all the information about the Top 10 grossing movies with the total domestic gross, foreign gross, and worldwide gross.


In Tableau, I can show how interactive the information  is by filtering and showing what a specific movie made at the box office. 
## Interactive dashboard 2
!<img width="1859" height="1649" alt="Profit and loss Dashboard" src="https://github.com/user-attachments/assets/c928496b-600f-4d15-825e-868c2f3587f1" />

This dashboard contains the product budget and the profit and losses made after releasing the movie.
## Observation
* Some of the best-performing movies had a large budget.
* Dark Phoenix made a huge loss despite being an action movie, indicating that sometimes you can get it wrong even if action movies are popular among the audience.






