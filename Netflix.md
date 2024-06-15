```python
import pandas as pd
import numpy as np
import matplotlib.pyplot as plt
import seaborn as sns
```


```python
df = pd.read_csv('/Users/saibalajikondapalli/Documents/Python Practice/Netflix-Movies-and-TV-Shows-Data-Analysis/netflix_titles.csv')
df.head(10)
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>show_id</th>
      <th>type</th>
      <th>title</th>
      <th>director</th>
      <th>cast</th>
      <th>country</th>
      <th>date_added</th>
      <th>release_year</th>
      <th>rating</th>
      <th>duration</th>
      <th>listed_in</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>s1</td>
      <td>Movie</td>
      <td>Dick Johnson Is Dead</td>
      <td>Kirsten Johnson</td>
      <td>NaN</td>
      <td>United States</td>
      <td>September 25, 2021</td>
      <td>2020</td>
      <td>PG-13</td>
      <td>90 min</td>
      <td>Documentaries</td>
      <td>As her father nears the end of his life, filmm...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>s2</td>
      <td>TV Show</td>
      <td>Blood &amp; Water</td>
      <td>NaN</td>
      <td>Ama Qamata, Khosi Ngema, Gail Mabalane, Thaban...</td>
      <td>South Africa</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>2 Seasons</td>
      <td>International TV Shows, TV Dramas, TV Mysteries</td>
      <td>After crossing paths at a party, a Cape Town t...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>s3</td>
      <td>TV Show</td>
      <td>Ganglands</td>
      <td>Julien Leclercq</td>
      <td>Sami Bouajila, Tracy Gotoas, Samuel Jouy, Nabi...</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>1 Season</td>
      <td>Crime TV Shows, International TV Shows, TV Act...</td>
      <td>To protect his family from a powerful drug lor...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>s4</td>
      <td>TV Show</td>
      <td>Jailbirds New Orleans</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>1 Season</td>
      <td>Docuseries, Reality TV</td>
      <td>Feuds, flirtations and toilet talk go down amo...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>s5</td>
      <td>TV Show</td>
      <td>Kota Factory</td>
      <td>NaN</td>
      <td>Mayur More, Jitendra Kumar, Ranjan Raj, Alam K...</td>
      <td>India</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>2 Seasons</td>
      <td>International TV Shows, Romantic TV Shows, TV ...</td>
      <td>In a city of coaching centers known to train I...</td>
    </tr>
    <tr>
      <th>5</th>
      <td>s6</td>
      <td>TV Show</td>
      <td>Midnight Mass</td>
      <td>Mike Flanagan</td>
      <td>Kate Siegel, Zach Gilford, Hamish Linklater, H...</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>1 Season</td>
      <td>TV Dramas, TV Horror, TV Mysteries</td>
      <td>The arrival of a charismatic young priest brin...</td>
    </tr>
    <tr>
      <th>6</th>
      <td>s7</td>
      <td>Movie</td>
      <td>My Little Pony: A New Generation</td>
      <td>Robert Cullen, José Luis Ucha</td>
      <td>Vanessa Hudgens, Kimiko Glenn, James Marsden, ...</td>
      <td>NaN</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>PG</td>
      <td>91 min</td>
      <td>Children &amp; Family Movies</td>
      <td>Equestria's divided. But a bright-eyed hero be...</td>
    </tr>
    <tr>
      <th>7</th>
      <td>s8</td>
      <td>Movie</td>
      <td>Sankofa</td>
      <td>Haile Gerima</td>
      <td>Kofi Ghanaba, Oyafunmike Ogunlano, Alexandra D...</td>
      <td>United States, Ghana, Burkina Faso, United Kin...</td>
      <td>September 24, 2021</td>
      <td>1993</td>
      <td>TV-MA</td>
      <td>125 min</td>
      <td>Dramas, Independent Movies, International Movies</td>
      <td>On a photo shoot in Ghana, an American model s...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>s9</td>
      <td>TV Show</td>
      <td>The Great British Baking Show</td>
      <td>Andy Devonshire</td>
      <td>Mel Giedroyc, Sue Perkins, Mary Berry, Paul Ho...</td>
      <td>United Kingdom</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>TV-14</td>
      <td>9 Seasons</td>
      <td>British TV Shows, Reality TV</td>
      <td>A talented batch of amateur bakers face off in...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>s10</td>
      <td>Movie</td>
      <td>The Starling</td>
      <td>Theodore Melfi</td>
      <td>Melissa McCarthy, Chris O'Dowd, Kevin Kline, T...</td>
      <td>United States</td>
      <td>September 24, 2021</td>
      <td>2021</td>
      <td>PG-13</td>
      <td>104 min</td>
      <td>Comedies, Dramas</td>
      <td>A woman adjusting to life after a loss contend...</td>
    </tr>
  </tbody>
</table>
</div>



#### Initial Impressions of the Data
This details has all the details regarding the Title of the Movie / TV Show. Just looking at the first 10 rows of the data we can already see some missing values. 


```python
print(df.shape)

df.info()
```

    (8807, 12)
    <class 'pandas.core.frame.DataFrame'>
    RangeIndex: 8807 entries, 0 to 8806
    Data columns (total 12 columns):
     #   Column        Non-Null Count  Dtype 
    ---  ------        --------------  ----- 
     0   show_id       8807 non-null   object
     1   type          8807 non-null   object
     2   title         8807 non-null   object
     3   director      6173 non-null   object
     4   cast          7982 non-null   object
     5   country       7976 non-null   object
     6   date_added    8797 non-null   object
     7   release_year  8807 non-null   int64 
     8   rating        8803 non-null   object
     9   duration      8804 non-null   object
     10  listed_in     8807 non-null   object
     11  description   8807 non-null   object
    dtypes: int64(1), object(11)
    memory usage: 825.8+ KB


#### Data Details

This dataset contains 8807 rows and 12 columns. Out of these 12 columns one is int64 data type and the rest are object type.


```python
df.isnull().sum()
```




    show_id            0
    type               0
    title              0
    director        2634
    cast             825
    country          831
    date_added        10
    release_year       0
    rating             4
    duration           3
    listed_in          0
    description        0
    dtype: int64



#### Data Details

This data set has missing values in a couple of columns. `director` has 2634, `cast` has 825, `country` has 831, `date_added` has 10, `rating` has 4 and `duration` has 3 missing values.


```python
df.describe()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>release_year</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>count</th>
      <td>8807.000000</td>
    </tr>
    <tr>
      <th>mean</th>
      <td>2014.180198</td>
    </tr>
    <tr>
      <th>std</th>
      <td>8.819312</td>
    </tr>
    <tr>
      <th>min</th>
      <td>1925.000000</td>
    </tr>
    <tr>
      <th>25%</th>
      <td>2013.000000</td>
    </tr>
    <tr>
      <th>50%</th>
      <td>2017.000000</td>
    </tr>
    <tr>
      <th>75%</th>
      <td>2019.000000</td>
    </tr>
    <tr>
      <th>max</th>
      <td>2021.000000</td>
    </tr>
  </tbody>
</table>
</div>



The dataset contains information on movies released between the years 1925 and 2021. Here is a summary of the `release_year` column:

- **Count:** The dataset includes 8807 movies.
- **Mean:** The average release year of the movies is approximately 2014.
- **Standard Deviation:** The standard deviation is 8.82, indicating the variability in the release years of the movies.
- **Minimum:** The earliest movie in the dataset was released in 1925.
- **25th Percentile (Q1):** 25% of the movies were released before 2013.
- **Median (Q2):** 50% of the movies were released before 2017.
- **75th Percentile (Q3):** 75% of the movies were released before 2019.
- **Maximum:** The most recent movie in the dataset was released in 2021.

From this summary, we can observe that the majority of the movies in the dataset are relatively recent, with 50% of them released in or after 2017. A significant portion of the dataset consists of movies released in the last decade, with 75% of the movies being released in or after 2013 and 25% being released in or after 2019.



```python
df = df.dropna()
```


```python
df['date_added'] = df['date_added'].str.strip()

df['date_added'] = pd.to_datetime(df['date_added'], format='%B %d, %Y')


df['day_added'] = df['date_added'].dt.day
df['month_added'] = df['date_added'].dt.strftime('%B')
df['year_added'] = df['date_added'].dt.year
df.drop(columns=['date_added'],inplace=True)
df.insert(6,'day_added', df.pop('day_added'))
df.insert(7, 'month_added', df.pop('month_added'))
df.insert(8, 'year_added', df.pop('year_added'))
df.head()
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>show_id</th>
      <th>type</th>
      <th>title</th>
      <th>director</th>
      <th>cast</th>
      <th>country</th>
      <th>day_added</th>
      <th>month_added</th>
      <th>year_added</th>
      <th>release_year</th>
      <th>rating</th>
      <th>duration</th>
      <th>listed_in</th>
      <th>description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7</th>
      <td>s8</td>
      <td>Movie</td>
      <td>Sankofa</td>
      <td>Haile Gerima</td>
      <td>Kofi Ghanaba, Oyafunmike Ogunlano, Alexandra D...</td>
      <td>United States, Ghana, Burkina Faso, United Kin...</td>
      <td>24</td>
      <td>September</td>
      <td>2021</td>
      <td>1993</td>
      <td>TV-MA</td>
      <td>125 min</td>
      <td>Dramas, Independent Movies, International Movies</td>
      <td>On a photo shoot in Ghana, an American model s...</td>
    </tr>
    <tr>
      <th>8</th>
      <td>s9</td>
      <td>TV Show</td>
      <td>The Great British Baking Show</td>
      <td>Andy Devonshire</td>
      <td>Mel Giedroyc, Sue Perkins, Mary Berry, Paul Ho...</td>
      <td>United Kingdom</td>
      <td>24</td>
      <td>September</td>
      <td>2021</td>
      <td>2021</td>
      <td>TV-14</td>
      <td>9 Seasons</td>
      <td>British TV Shows, Reality TV</td>
      <td>A talented batch of amateur bakers face off in...</td>
    </tr>
    <tr>
      <th>9</th>
      <td>s10</td>
      <td>Movie</td>
      <td>The Starling</td>
      <td>Theodore Melfi</td>
      <td>Melissa McCarthy, Chris O'Dowd, Kevin Kline, T...</td>
      <td>United States</td>
      <td>24</td>
      <td>September</td>
      <td>2021</td>
      <td>2021</td>
      <td>PG-13</td>
      <td>104 min</td>
      <td>Comedies, Dramas</td>
      <td>A woman adjusting to life after a loss contend...</td>
    </tr>
    <tr>
      <th>12</th>
      <td>s13</td>
      <td>Movie</td>
      <td>Je Suis Karl</td>
      <td>Christian Schwochow</td>
      <td>Luna Wedler, Jannis Niewöhner, Milan Peschel, ...</td>
      <td>Germany, Czech Republic</td>
      <td>23</td>
      <td>September</td>
      <td>2021</td>
      <td>2021</td>
      <td>TV-MA</td>
      <td>127 min</td>
      <td>Dramas, International Movies</td>
      <td>After most of her family is murdered in a terr...</td>
    </tr>
    <tr>
      <th>24</th>
      <td>s25</td>
      <td>Movie</td>
      <td>Jeans</td>
      <td>S. Shankar</td>
      <td>Prashanth, Aishwarya Rai Bachchan, Sri Lakshmi...</td>
      <td>India</td>
      <td>21</td>
      <td>September</td>
      <td>2021</td>
      <td>1998</td>
      <td>TV-14</td>
      <td>166 min</td>
      <td>Comedies, International Movies, Romantic Movies</td>
      <td>When the father of the man she loves insists t...</td>
    </tr>
  </tbody>
</table>
</div>




```python
day_counts = df.groupby('day_added').size().reset_index(name='count')
day_counts = day_counts.sort_values('day_added')

plt.figure(figsize=(10,6))
sns.barplot(x='day_added', y='count', data=day_counts, palette='viridis')
plt.grid(visible=True, which='both', linestyle='--', linewidth=0.1)
plt.gca().set_axisbelow(True) 
plt.gca().yaxis.grid(True)    
plt.gca().xaxis.grid(True)
plt.ylim(0, None) 
plt.title('Number of Movies/TV Shows Released on Each Date')
plt.xlabel('Date added')
plt.ylabel('No of Movies / TV Shows released on this date')
plt.xticks(rotation=45, fontsize=14)
plt.show()
```

    /var/folders/d5/0nkl4bqj2712httng60lv1cr0000gn/T/ipykernel_20571/2544744739.py:5: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x='day_added', y='count', data=day_counts, palette='viridis')



    
![png](Netflix_files/Netflix_11_1.png)
    



```python
month_added = df.groupby('month_added').size().reset_index(name='count')
month_order = ['January', 'February', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October', 'November', 'December']
month_added['month_added'] = pd.Categorical(month_added['month_added'], categories=month_order, ordered=True)
month_added = month_added.sort_values('month_added')
month_added
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>month_added</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>4</th>
      <td>January</td>
      <td>489</td>
    </tr>
    <tr>
      <th>3</th>
      <td>February</td>
      <td>341</td>
    </tr>
    <tr>
      <th>7</th>
      <td>March</td>
      <td>469</td>
    </tr>
    <tr>
      <th>0</th>
      <td>April</td>
      <td>471</td>
    </tr>
    <tr>
      <th>8</th>
      <td>May</td>
      <td>368</td>
    </tr>
    <tr>
      <th>6</th>
      <td>June</td>
      <td>415</td>
    </tr>
    <tr>
      <th>5</th>
      <td>July</td>
      <td>464</td>
    </tr>
    <tr>
      <th>1</th>
      <td>August</td>
      <td>449</td>
    </tr>
    <tr>
      <th>11</th>
      <td>September</td>
      <td>427</td>
    </tr>
    <tr>
      <th>10</th>
      <td>October</td>
      <td>491</td>
    </tr>
    <tr>
      <th>9</th>
      <td>November</td>
      <td>458</td>
    </tr>
    <tr>
      <th>2</th>
      <td>December</td>
      <td>490</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.figure(figsize=(10,6))
sns.barplot(x='month_added', y='count', data=month_added, palette='viridis')
plt.grid(visible=True, which='both', linestyle='--', linewidth=0.1)
plt.gca().set_axisbelow(True) 
plt.gca().yaxis.grid(True)    
plt.gca().xaxis.grid(True)
plt.ylim(0, None) 
plt.title('Total number of Movies / TV Shows released on each month')
plt.xlabel('Month')
plt.ylabel('Count')
plt.xticks(rotation=45, fontsize=14)
plt.show()
```

    /var/folders/d5/0nkl4bqj2712httng60lv1cr0000gn/T/ipykernel_20571/440090499.py:2: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x='month_added', y='count', data=month_added, palette='viridis')



    
![png](Netflix_files/Netflix_13_1.png)
    



```python
year_added = df.groupby('year_added').size().reset_index(name='count')
year_added = year_added.sort_values('year_added')
year_added
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>year_added</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>2008</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>2009</td>
      <td>2</td>
    </tr>
    <tr>
      <th>2</th>
      <td>2010</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>2011</td>
      <td>13</td>
    </tr>
    <tr>
      <th>4</th>
      <td>2012</td>
      <td>3</td>
    </tr>
    <tr>
      <th>5</th>
      <td>2013</td>
      <td>7</td>
    </tr>
    <tr>
      <th>6</th>
      <td>2014</td>
      <td>14</td>
    </tr>
    <tr>
      <th>7</th>
      <td>2015</td>
      <td>50</td>
    </tr>
    <tr>
      <th>8</th>
      <td>2016</td>
      <td>202</td>
    </tr>
    <tr>
      <th>9</th>
      <td>2017</td>
      <td>724</td>
    </tr>
    <tr>
      <th>10</th>
      <td>2018</td>
      <td>1101</td>
    </tr>
    <tr>
      <th>11</th>
      <td>2019</td>
      <td>1265</td>
    </tr>
    <tr>
      <th>12</th>
      <td>2020</td>
      <td>1194</td>
    </tr>
    <tr>
      <th>13</th>
      <td>2021</td>
      <td>755</td>
    </tr>
  </tbody>
</table>
</div>




```python
plt.figure(figsize=(10,6))
sns.barplot(x='year_added', y='count', data=year_added, palette='viridis')
plt.grid(visible=True, which='both', linestyle='--', linewidth=0.1)
plt.gca().set_axisbelow(True) 
plt.gca().yaxis.grid(True)    
plt.gca().xaxis.grid(True)
plt.ylim(0, None)  
plt.title('Total number of Movies / TV Shows added through out the years')
plt.xlabel('Year')
plt.ylabel('Count')
plt.xticks(rotation=45, fontsize=14)
plt.show()
```

    /var/folders/d5/0nkl4bqj2712httng60lv1cr0000gn/T/ipykernel_20571/2137804607.py:2: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x='year_added', y='count', data=year_added, palette='viridis')



    
![png](Netflix_files/Netflix_15_1.png)
    


This shows the trend of adaptaion of internet for movies


```python
year_released = df.groupby('release_year').size().reset_index(name='count')
year_released = year_released.sort_values('release_year')
year_released
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>release_year</th>
      <th>count</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1942</td>
      <td>1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1944</td>
      <td>1</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1945</td>
      <td>1</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1946</td>
      <td>1</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1947</td>
      <td>1</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>67</th>
      <td>2017</td>
      <td>657</td>
    </tr>
    <tr>
      <th>68</th>
      <td>2018</td>
      <td>648</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2019</td>
      <td>519</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2020</td>
      <td>442</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2021</td>
      <td>161</td>
    </tr>
  </tbody>
</table>
<p>72 rows × 2 columns</p>
</div>




```python
plt.figure(figsize=(20,6))
sns.barplot(x='release_year', y='count', data=year_released, palette='viridis')
plt.grid(visible=True, which='both', linestyle='--', linewidth=0.1)
plt.gca().set_axisbelow(True) 
plt.gca().yaxis.grid(True)    
plt.gca().xaxis.grid(True)
plt.ylim(0, None)  
plt.title('Total number of Movies / TV Shows released through out the years')
plt.xlabel('Year')
plt.ylabel('Count')
plt.xticks(rotation=45, fontsize=14)
plt.show()
```

    /var/folders/d5/0nkl4bqj2712httng60lv1cr0000gn/T/ipykernel_20571/2673968643.py:2: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x='release_year', y='count', data=year_released, palette='viridis')



    
![png](Netflix_files/Netflix_18_1.png)
    



```python
types = df['type'].value_counts()

explode = [0.1 if i == 0 else 0 for i in range(len(types))]

plt.figure(figsize=(8,6))
plt.pie(types, labels=types.index, autopct='%1.1f%%',colors=['blue','orange'], startangle=140, explode= explode)
plt.title('Count of Movies and TV Shows')
plt.axis('equal')
plt.show()
```


    
![png](Netflix_files/Netflix_19_0.png)
    



```python
plt.figure(figsize=(15,6))
sns.countplot(x='rating', hue='type', data=df, palette='crest')
plt.title('Rating of Movies, TV Shows')
plt.show()
```


    
![png](Netflix_files/Netflix_20_0.png)
    



```python
countries = df['country'].value_counts()
countries = countries.head(10)
countries


plt.figure(figsize=(15,6))
sns.barplot(x=countries.index, y=countries.values, palette='crest')
plt.title('Country wide count of Movies, TV Shows')
plt.xticks(rotation=45)
plt.show()
```

    /var/folders/d5/0nkl4bqj2712httng60lv1cr0000gn/T/ipykernel_20571/559233721.py:7: FutureWarning: 
    
    Passing `palette` without assigning `hue` is deprecated and will be removed in v0.14.0. Assign the `x` variable to `hue` and set `legend=False` for the same effect.
    
      sns.barplot(x=countries.index, y=countries.values, palette='crest')



    
![png](Netflix_files/Netflix_21_1.png)
    



```python
from wordcloud import WordCloud

text = " ".join(director for director in df['director'])

wordcloud = WordCloud(width=800, height=400, background_color='white').generate(text)

plt.figure(figsize=(10,5))
plt.imshow(wordcloud, interpolation='bilinear')
plt.axis('off')
plt.title('Word Cloud for Directors', fontsize=16)
plt.show()
```


    
![png](Netflix_files/Netflix_22_0.png)
    



```python
text_2 = ' '.join(cast for cast in df['cast'])

wordcloud_2 = WordCloud(width=800, height=400, background_color='white').generate(text_2)

plt.figure(figsize=(10,5))
plt.imshow(wordcloud_2, interpolation='bilinear')
plt.axis('off')
plt.title('Word Cloud of Cast')
plt.show()
```


    
![png](Netflix_files/Netflix_23_0.png)
    



```python

```
