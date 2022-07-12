This is a detailed documentation to walk any reader through the notebook.
In-line markdowns have also been provided for readablity and reproducibility.
# Documentation for data wrangling steps: gather, assess, and clean

# Importing needed modules and Gathering my dataset
Firstly, all needed packages were correctly imported.
Three important datasets were used for this analysis.
Twitter_archive_advanced -  A csv file made available by @weratedogs to udacity for the purpose of this analysis.   This file contains a total of 2356 records.
The image prediction file - A tsv file containing images of dogs tweeted and predictions on the breed by a neural network algorithm carried out in three stages and its corresponding url. This was hosted on udacity server and I downloaded it programmatically using the `request` library.This contained 2075 records.
The retweets and favourite counts file - I also requested for this as I was unable to get access to twitter developer account. This was successfully read and converted to a datframe as the the other two files. contained  2354 records.

# Assessing my dataset.

### Visual Assessment
 This was done using the `head()` function to see the dataset. other similar functions as head are using `tail()` or `sample()` numbers can be passed into the call to limit the size of the slice. Here i used `head(3)`

### Programmatic Assessment
This was done using the `info()`, `nunique()`, `duplicated()` and `isnull()` on all three datasets

# Cleaning/Wrangling my datasets.

Firstly, copies were made for all three datasets to preserve the original dataset.
Then the wrangling was done using the DEFINE-CODE-TEST method on all the issues listed below.
- Issue 1: Convert tweet_ids of all three dataset from int to string
- Issue 2: Convert the timestamp column to datetime for timeseries analysis.
- Issue 3: Drop rows which holds records for the 2 replies column - `in_reply_to_status_id` , `in_reply_to_user_id`
- Issue 4: Drop rows which holds records for the 2 replies column - `retweeted_status_id` , `retweeted_status_user_id ` , `retweeted_status_timestamp`
- Issue 5: Drop the five columns with 0 non-null values (two reply and three retweets columns)
- Issue 6: Check the rating_numerator column and fix possible issues.
- Issue 7: Inconsistensies and wrong values in name column
- Issue 8: Merge the four dog stages column into one named `stage`
Then I merged all my three clean datasets together on tweet_id which served as the primary key. I further assessed it and confirmed it was okay for analysis.
I stored it as the `tweet_archive_master` csv  file.

# Analysis and visualisation

Imported needed libraries. My viz was done with basic pandas plots and matplotlib.
The matplotlib magic statement was used to keep the vizes within the notebook.

My Analysis answered the following questions
- 1: What is the relationship between retweet counts and favorite(likes) counts
- 2: What day of the week holds the highest retweets and favorite counts?
- 3: Impact of the hour of the day on retweet and favorite counts.
- 4: Which dog stage had the highest no of retweets and likes (Favorite counts)
- 5: Mostly used channel of tweets - tweet source
- 6: Top five breeds of dogs discovered by the algorithm.
The timeframe of the dataset used for the analysis.

``` import a
    export b
    a = b =c
    print ab 
