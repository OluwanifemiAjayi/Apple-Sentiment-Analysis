# Analysis of Apple Users' Reviews and Sentiments
## A Project involving the Analysis of Sentiments with the aid of Python and PowerBI 

## Introduction
This project aims to perform sentiment analysis on customer reviews from Trustpilot for Apple's website. Sentiment analysis helps to understand the overall sentiment expressed in the reviews, whether it is positive, negative, or neutral. I performed a sentiment analysis on reviews from Apple users to understand their feelings about Apple’s products and services using Natural Language Processing (NLP) techniques. Trustpilot, a website where users leave reviews and feedback about various brands and products, was the source of these reviews. I collected the reviews by scraping pages from Trustpilot specifically for Apple. 

![Trustpilot Homepage](https://github.com/OluwanifemiAjayi/Apple-Sentiment-Analysis/blob/main/Trustpilot.png?raw=true)
                     
To achieve this, I used several Python libraries: Pandas for data cleaning and manipulation, BeautifulSoup for web scraping, Natural Language Toolkit (NLTK) and TextBlob for sentiment analysis, Matplotlib and WordCloud for data exploration and visualization. Using these tools, I was able to analyze the sentiments expressed in the reviews and gain insights into how users feel about Apple’s offerings.
As shown in this [Jupyter Notebook](http://localhost:8888/notebooks/Sentiment%20Analysis%20project.ipynb), you will observe how I conducted this project following the steps outlined below:
 1. Introduction

 2. Web Scraping and Data Gathering

3. Data Evaluation and Cleaning

4. Data Preprocessing

5. Sentiment Analysis

6. Data Exploration and Visualization

7. Conclusion

## Web Scraping and Data Gathering
The first major step was to import all the necessary libraries for this sentiment analysis into my Jupyter notebook after which I proceeded to gather customer reviews from Trustpilot for Apple's website. I defined the range of pages to scrape and used the BeautifulSoup library coupled with some functions I defined, to extract relevant information, such as review content, total reviews, user names, ratings, locations, and dates from the HTML structure of the webpage. I split the web scraping process into two batches of 100 pages each to speed up the whole process of scraping. The extracted data is stored in lists and then converted into a Pandas DataFrame for further processing.

## Data Evaluation and Data Cleaning
After gathering the data, I assessed it to identify and handle missing values, duplicates, and inconsistent formatting. This step involved:
- **Removing duplicates:** Identifying and removing duplicate reviews based on the "Username" and "Review_content" columns.
- **Standardizing location names:** Using the country_converter library to convert abbreviated location names to standardized country codes.
- **Cleaning numeric values:** Converting the total number of reviews to integer format by removing non-digit characters.
- **Formatting dates:** Standardizing the date format and handling relative dates (e.g., "3 days ago") by converting them to absolute dates.

## Data Preprocessing 
Next, I preprocessed the "Review_content" column to prepare it for sentiment analysis. I created several functions to clean up the column, these functions removed unnecessary stopwords from each review, leaving only the important words and adjectives free from repeating characters, stop words and punctuations. Then I lemmatized the remaining words for further analysis. This stage required:
- **Lowercasing:** Converting all text to lowercase to ensure uniformity.
- **Tokenization:** Splitting the text into individual words.
- **Removing stopwords and non-alphabetic tokens:** Filtering out common stopwords and non-alphabetic characters to focus on meaningful words.
- **Lemmatization:** Reducing words to their base or root form

## Sentiment Analysis
I performed sentiment analysis using the TextBlob library,creating functions to calculate the subjectivity and polarity of the column "Review_content which provides polarity and subjectivity scores for each review after applying these functions to the column. Polarity indicates the sentiment of the text (negative, neutral, or positive), while subjectivity measures the degree of personal opinion expressed in the text, a polarity score of < 0 is Negative, 0 is Neutral while > 0 is Positive.. I also extracted adjectives from the reviews as they often carry significant sentiment information.

## Data Exploration and Visualization
To visualize the results of our sentiment analysis, I created several plots:

### Sentiment Distribution
I exported the value counts of the sentiment labels to a new DataFrame and then I used MatPlotLib to create a bar chart showing the distribution of positive, negative, and neutral reviews. This distribution is displayed below

### Word Cloud Visualization
A word cloud of the most common adjectives used in the reviews to highlight frequently mentioned descriptors. To find the most common adjectives used to describe Apple"s services, I used the POS-tag (Parts of Speech tagging) module from the NLTK library. With the WordCloud library, I generated a word cloud based on word frequency, displaying the words over an image. I displayed the word cloud with Matplotlib, in this cloud, words with higher frequencies appear in larger text, while less common words are shown in smaller text.

### Word Frequency Analysis
I created a bar chart to visualize the top 20 most common adjectives to provide insights into the most frequently used descriptive words, this way I was able to obtain a clear visual representation of the most frequently used adjectives in the reviews, which helps in understanding common sentiments expressed by the reviewers.

## Conclusion
### Remarks

- **Total Reviews and Average Rating:**
The dashboard shows a total of 4,000 reviews with an average rating of 1.73, which goes to say that the sentiment among the reviewers is generally poor.

- **Reviews This Week:**
With 10 reviews submitted this week, it can be said that there has been a good flow of customer feedback with the usual figures for this week.

- **Countries with the Most Reviews:**
It means the most reviews are from the United Kingdom and the United States having a count of 1,677 and 1,415 respectively. This obviously shows loads of customer engagement coming from these countries.

- **Sentiments Distribution:**
Positive, negative, and neutral reviews come out to an exact equivalent of percentage share, where positive reviews occupy about 50 percent, negative occupies 42 percent of the reviews, and neutral occupies about 8 percent of the reviews. To say this clearly, almost half the reviewers are very dissatisfied.

- **Monthly Reviews:**
The reviews are spread throughout the year, with a maximum in January and December. This shows high engagement in these months of the year probably because of the holiday seasons or due to new product releases.

- **Yearly and Quarterly Reviews:**
The graph of the number of reviews clearly indicates a fluctuation over the years and quarters. The significant peaks and troughs might represent the varying amount of customer engagement, and probably the effect of new product launches or key events.

- **Reviews by Ratings:**
Most of the other reviews are rated 1, indicating bad service. Very few are rated 2, 3, and 4, while at the extreme end, there is another peak for the rating level 5. It turns out to be a bimodal distribution, evidencing that the customers enjoy either very poor or very good experiences .

### Recommendations for Apple

- **Product Quality Improvement/Service:**
It is thus crucial that Apple investigates the common issues laid out by a huge number of negative reviewers and the low average rating. Concerting the defects of the products can bring improvement in the product defectiveness, improvement in the response time to customer service, and consistent performance of the same product.

- **Respond to the Customer in High Review Regions:**
Because engagement is maximum in the United Kingdom and the United States, Apple has to target these markets to better understand the needs and wants of customers. Deeper insights can be obtained through targeted surveys and focus groups.

- **Better After-Sales Support:**
Many of the negative reviews could be due to after-sales support. Apple needs to ensure that their support teams are properly trained, responsive, and efficient in fixing problems. They could try extending support hours and utilizing multiple channels for customer support in order to enhance customer satisfaction.

- **Amplify Positive Feedback:**
As 50% of reviews are positive, Apple should definitely find out what the users appreciate in its products and services. Tons of advertising campaigns could focus on these strengths and, in turn, reinforce these points during future product development. This could build existing customer goodwill.

- **Address Seasonal Trends:**
Peaks noted in the reviews during January and December indicate seasonal influences that may be related to holiday sales and new product releases. Apple should be better prepared for such periods, by making customer support more available and be sure that their products are rigorously tested to meet increased demand from users.

- **Promote Balanced Reviews:**
That there seems to be a great closeness between extreme customer experiences in balance, it would be more balanced reviews that would bring a clearer picture of the customers' sentiments to Apple. A follow-up review request system where customers update their ratings based on continuous use might add further nuances.

- **Monitor and Act on Feedback Trends:**
Regular tracking of sentiment trends and prompt action over emerging issues would help avert negative sentiments from getting amplified. Prediction and action even before it actually happens, by utilizing data analytics, are key to sustaining a positive brand image.

Implementing the above recommendations will help Apple elevate customer satisfaction levels and improve the quality of the products and services offered. As a result, Apple will slowly build a more loyal customer base than it has today. This process can also be replicated for any other company or product with reviews posted by customers leading to actionable insights.










