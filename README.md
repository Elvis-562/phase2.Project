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
I then reviewe the 6 datasets and i decided to work with two datasets.

The datasets include Box Office Mojo(BOM) and the numbers dataset.

I picked the box office mojo dataset since it contains domestic and foreign gross so it helps us know how much money was made locally and internationally.

I picked the numbers dataset(df6) since it contains the production budget and the gross of the films so we can see how much profit the movies are making hence identifying the type of films that won't incur loss and  are popular films among the audiences.
## Data Preparation

