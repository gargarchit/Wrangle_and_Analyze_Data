### Introduction

Real-world data rarely come clean. Using Python and its libraries, we have gathered data from a variety of sources and in a variety of formats, assessed its quality and tidiness, then cleaned it. 

The dataset on which we have done wrangling (and analyzing and visualizing) is the tweet archive of Twitter users [@dog_rates](https://twitter.com/dog_rates), also known as [WeRateDogs](https://en.wikipedia.org/wiki/WeRateDogs). WeRateDogs is a Twitter account that rates people's dogs with a humorous comment about the dog. These ratings almost always have a denominator of 10. The numerators, however? Almost always higher than 10. 11/10, 12/10, 13/10, etc. Why? Because ["they're good dogs, Brent."](http://knowyourmeme.com/memes/theyre-good-dogs-brent) WeRateDogs has over 4 million followers and has received international media coverage.

![alt text](https://d17h27t6h515a5.cloudfront.net/topher/2017/October/59dd378f_dog-rates-social/dog-rates-social.jpg)

### Project Details

  * Data wrangling, which consists of:
    * Gathering data
    * Assessing data
    * Cleaning data
        
* Storing, analyzing, and visualizing your wrangled data
* Reporting on 1) Data wrangling efforts and 2) Data analyses and visualizations

### Gathering Data for this Project

Here, we have to Gather each of the three pieces of data as described below in a Jupyter Notebook titled <code><mark>wrangle_act.ipynb</mark></code>:

1. The WeRateDogs Twitter archive <code><mark>twitter_archive_enhanced.csv</mark></code>. It has instructed that this file be downloaded manually from an URL provided by Udacity.
2. The tweet image predictions, i.e., what breed of dog (or another object, animal, etc.) is present in each tweet according to a neural network. This file (<code><mark>image_predictions.tsv</mark></code>) hosted on Udacity's servers and downloaded programmatically using the [Requests](http://docs.python-requests.org/en/master/) library and the following URL: https://d17h27t6h515a5.cloudfront.net/topher/2017/August/599fd2ad_image-predictions/image-predictions.tsv

3. Each tweet's retweet count and favorite. Using the tweet IDs in the WeRateDogs Twitter archive, we queried the Twitter API for each tweet's JSON data using Python's [Tweepy](http://www.tweepy.org/) library and stored each tweet's entire set of JSON data in a file called <code><mark>tweet_json.txt</mark></code> file. Each tweet's JSON data should be written to its line. Then read this .txt file line by line into a pandas DataFrame with (at minimum) tweet ID, retweet count, and favorite count.

### Assessing Data for this Project

After gathering each of the above pieces of data, assessed them visually and programmatically for quality and tidiness issues. Detected and document **quality issues** and **tidiness issues** in the <code><mark>wrangle_act.ipynb</mark></code> Jupyter Notebook. 

### Key Points

* We only want original ratings (no retweets) that have images. Though there are 5000+ tweets in the dataset, not all are dog ratings, and some are retweets.
* Fully assessing and cleaning the entire dataset requires exceptional effort, so only a subset of its issues i.e., quality issues and tidiness issues, needs to be assessed and cleaned.
* Cleaning includes merging individual pieces of data according to the rules of [tidy data](https://cran.r-project.org/web/packages/tidyr/vignettes/tidy-data.html).
* The fact that the rating numerators are higher than the denominators does not need to be cleaned. This [unique rating system](http://knowyourmeme.com/memes/theyre-good-dogs-brent) is a big part of the popularity of WeRateDogs.
* We do *not* need to gather the tweets beyond August 1st, 2017. we can, but note that we will not be able to gather the image predictions for these tweets since we do not have access to the algorithm used.

### Cleaning Data for this Project

We cleaned each of the issues and documented them while assessing. Perform this cleaning in <code><mark>wrangle_act.ipynb</mark></code> as well and got the result of high quality and tidy master pandas DataFrame

### Storing, Analyzing, and Visualizing Data for this Project

Finally, Store the clean master DataFrame in a CSV file with the main one named <code><mark>master_archive.csv</mark></code>.
