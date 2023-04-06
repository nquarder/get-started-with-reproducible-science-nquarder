---

1. Open reproducible science is easy to share, find, and transparent in terms of its methods and findings.

2. Github is a great reproducible science tool for sharing code and workflows.

3. No it does not. We could rename it but adding a numerical value at the start. Also hyphens between words, and remove ! ;) 

I can write clean code by:
  * using loops + functions so I'm not repeating myself
  * adding helpful comments
  * following pep8 standards; using expressive variable names


Advantages of clean code include:
  * easy to read
  * easy to share
  * easy to reproduce


```python
# Import Python libraries
import matplotlib.pyplot as plt
import pandas as pd
```

The test cell below will tell you if you completed the task successfully when you run it. **Do not try to modify any test cells as our software we use to give you feedback, nbgrader, will be grumpy about that.** If a test cell isn't working, check that you ran your code **immediately before** running the test.


```python
points = 0
try:
    pd.DataFrame()
    points += 5
    print('\u2705 Great work! You correctly imported the pandas library.')
except:
    print('\u274C Oops - pandas was not imported correctly.')
print('You earned {} of 5 points for importing pandas'.format(points))
```

    ✅ Great work! You correctly imported the pandas library.
    You earned 5 of 5 points for importing pandas


**YOUR DATA DESCRIPTION AND CITATION HERE**


```python
rapid_city_tmax_url = ('https://www.ncei.noaa.gov/access/monitoring/'
                   'climate-at-a-glance/city/time-series/USW00024090/'
                   'tmax/ann/1/1940-2023.csv')

rapid_city_tmax_url
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00024090/tmax/ann/1/1940-2023.csv'




```python
# List all current variables
%whos
```

    Variable              Type      Data/Info
    -----------------------------------------
    pd                    module    <module 'pandas' from '/o<...>ages/pandas/__init__.py'>
    plt                   module    <module 'matplotlib.pyplo<...>es/matplotlib/pyplot.py'>
    points                int       5
    rapid_city_tmax_url   str       https://www.ncei.noaa.gov<...>/tmax/ann/1/1940-2023.csv



```python
#download
rapid_city_tmax_df = pd.read_csv(
    rapid_city_tmax_url, 
    header=3, 
    names=['Date', 'Temp'])
rapid_city_tmax_df
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
      <th>Date</th>
      <th>Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>194912</td>
      <td>58.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>195012</td>
      <td>55.3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>195112</td>
      <td>54.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>195212</td>
      <td>59.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>195312</td>
      <td>59.6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>201812</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>201912</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>202012</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>202112</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>202212</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
tmax_df_resp = _
points = 0

if isinstance(tmax_df_resp, pd.DataFrame):
    points += 1
    print('\u2705 Great work! You called a DataFrame.')
else:
    print('\u274C Oops - make sure to call your DataFrame for testing.')
    
summary = [round(val, 2) for val in tmax_df_resp.mean().values]
if summary == [198562.0, 58.89]:
    points += 4
    print('\u2705 Great work! You correctly downloaded data.')
else:
    print('\u274C Oops - your data are not correct.')
print('You earned {} of 5 points for downloading data'.format(points))
```

    ✅ Great work! You called a DataFrame.
    ✅ Great work! You correctly downloaded data.
    You earned 5 of 5 points for downloading data



```python
# Check that the data was imported into a pandas DataFrame
type(rapid_city_tmax_df)
```




    pandas.core.frame.DataFrame




```python
# Remove the 12 from data column by // 
rapid_city_tmax_df.iloc[:,0] = rapid_city_tmax_df.iloc[:,0] // 100
rapid_city_tmax_df
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
      <th>Date</th>
      <th>Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>58.1</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>55.3</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>54.4</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>59.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>59.6</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>57.2</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>54.7</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>61.8</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>62.1</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>60.9</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>



<img src="https://static.thenounproject.com/png/5640527-200.png" width=20 style="float: left; padding: 3px" /> **What just happened?**
 1. `+`, `-`, `*` and `/` are known as **operators** in Python, and are used for arithmetic (add, subtract, multiply, and divide, respectively). What do you think the `//` **operator** does?
 
 >**ANSWER:**  _It rounds the answer to the neareast whole value (integer)._

 2. `iloc` is an **attribute** of `DataFrame`s, meaning that it is available for all `DataFrame`s by attaching `.iloc` to its name. What do you think the `iloc` is?
 
 >**ANSWER:** _.iloc is a way of selecting a certain value or variable from a DataFrame_

    
  > HINT: It's ok if you can't figure out the answers yet. You can also list an experiment you tried. For example, you could run `4 // 2` and `4 // 3` and record the answers to help you figure out what `//` does. Or, you could change the `0` in `.iloc[:,0]` to `1` to see what happens. Play around with the code! It doesn't cost you anything to try things when you're coding.


```python
# Convert to celcius
rapid_city_tmax_df.iloc[:,1] = (rapid_city_tmax_df.iloc[:,1] - 32) * 5 / 9
rapid_city_tmax_df

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
      <th>Date</th>
      <th>Temp</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1949</td>
      <td>14.500000</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1950</td>
      <td>12.944444</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1951</td>
      <td>12.444444</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1952</td>
      <td>15.111111</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1953</td>
      <td>15.333333</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>69</th>
      <td>2018</td>
      <td>14.000000</td>
    </tr>
    <tr>
      <th>70</th>
      <td>2019</td>
      <td>12.611111</td>
    </tr>
    <tr>
      <th>71</th>
      <td>2020</td>
      <td>16.555556</td>
    </tr>
    <tr>
      <th>72</th>
      <td>2021</td>
      <td>16.722222</td>
    </tr>
    <tr>
      <th>73</th>
      <td>2022</td>
      <td>16.055556</td>
    </tr>
  </tbody>
</table>
<p>74 rows × 2 columns</p>
</div>




```python
fig, ax = plt.subplots()
rapid_city_tmax_df.plot(
    ax=ax,
    x='Date', 
    y='Temp',
    #xlabel='Year',
    #ylabel='Temp (C)',
    legend=False,
    figsize=(10,6),
    fontsize=15,
    )

ax.set_title('Max Temp (Celsius) - Rapid City, SD\n1949-2022', 
            fontsize= 20,
            weight='bold')

ax.set_xlabel('Year',fontsize = 18, weight='bold') # xlabel
ax.set_ylabel('Temp (C)', fontsize = 18, weight='bold') # ylabel
plt.show()
```


    
![png](Get%20Started%20with%20Open%20Reproducible%20Science%21_files/Get%20Started%20with%20Open%20Reproducible%20Science%21_15_0.png)
    


## Maximum annual temperatures in Rapid City are on the rise
Between 1949 and 2022 the maximum annual temperature in Rapid City, SD has risen by almost 1.5 Celsius.
In 1949 the maximum temperature was 14.5 C and in 2022 it was 16.0 C.

## Your turn: pick a new location and/or measurement to plot
Below, recreate the workflow you just did in a place that interests you OR with a different measurement. You will need to make your own new Markdown and Code cells.


```python
# Define url to Wausau, WI
wausau_tmax_url = ("https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00014897/tmax/ann/1/1842-2023.csv")
wausau_tmax_url
```




    'https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series/USW00014897/tmax/ann/1/1842-2023.csv'




```python
# Open and clean data using pandas
wausau_tmax_df = pd.read_csv(
                    wausau_tmax_url,
                    header=3,
                    na_values="-99.0")

wausau_tmax_df.iloc[:,0] = wausau_tmax_df.iloc[:,0] // 100
wausau_tmax_df

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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1942</td>
      <td>54.6</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1943</td>
      <td>53.0</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1944</td>
      <td>55.6</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1945</td>
      <td>53.2</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1946</td>
      <td>56.5</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>76</th>
      <td>2018</td>
      <td>54.8</td>
    </tr>
    <tr>
      <th>77</th>
      <td>2019</td>
      <td>52.7</td>
    </tr>
    <tr>
      <th>78</th>
      <td>2020</td>
      <td>55.9</td>
    </tr>
    <tr>
      <th>79</th>
      <td>2021</td>
      <td>57.6</td>
    </tr>
    <tr>
      <th>80</th>
      <td>2022</td>
      <td>54.0</td>
    </tr>
  </tbody>
</table>
<p>81 rows × 2 columns</p>
</div>




```python
wausau_tmax_df["Value"].max()
```




    60.4




```python
# Convert F to C
wausau_tmax_df.iloc[:,1] = (wausau_tmax_df.iloc[:,1] - 32) * 5/9
wausau_tmax_df
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
      <th>Date</th>
      <th>Value</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>1942</td>
      <td>12.555556</td>
    </tr>
    <tr>
      <th>1</th>
      <td>1943</td>
      <td>11.666667</td>
    </tr>
    <tr>
      <th>2</th>
      <td>1944</td>
      <td>13.111111</td>
    </tr>
    <tr>
      <th>3</th>
      <td>1945</td>
      <td>11.777778</td>
    </tr>
    <tr>
      <th>4</th>
      <td>1946</td>
      <td>13.611111</td>
    </tr>
    <tr>
      <th>...</th>
      <td>...</td>
      <td>...</td>
    </tr>
    <tr>
      <th>76</th>
      <td>2018</td>
      <td>12.666667</td>
    </tr>
    <tr>
      <th>77</th>
      <td>2019</td>
      <td>11.500000</td>
    </tr>
    <tr>
      <th>78</th>
      <td>2020</td>
      <td>13.277778</td>
    </tr>
    <tr>
      <th>79</th>
      <td>2021</td>
      <td>14.222222</td>
    </tr>
    <tr>
      <th>80</th>
      <td>2022</td>
      <td>12.222222</td>
    </tr>
  </tbody>
</table>
<p>81 rows × 2 columns</p>
</div>




```python
# Plot data
wausau_tmax_df.plot(x='Date', y='Value')

```




    <AxesSubplot:xlabel='Date'>




    
![png](Get%20Started%20with%20Open%20Reproducible%20Science%21_files/Get%20Started%20with%20Open%20Reproducible%20Science%21_22_1.png)
    


### Describe your plot here

#### Citation
NOAA National Centers for Environmental information, Climate at a Glance: City Time Series, published March 2023, retrieved on April 5, 2023 from https://www.ncei.noaa.gov/access/monitoring/climate-at-a-glance/city/time-series
