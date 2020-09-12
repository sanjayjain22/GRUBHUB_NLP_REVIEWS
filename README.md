# GRUBHUB_NLP_REVIEWS
Detailed analysis of Reviews of Grubhub's service segmented by their business operations.

## I. INTRODUCTION

The companies we choose are two of the biggest food delivery companies - Grubhub
and UberEATS. We would like to know the reviews for these two companies are positive
or negative. Also, in general, what the positive and negative reviews are talking about. In
the end, compare the results between the companies and websites.

### A. Project Process
* Data collection
* Data cleaning
* Exploratory Data Analysis
* Sentiment Analysis
* Insight

## II. DATA COLLECTION
In this section, we will describe the methodology we used for data collection, as well as
the short introduction of data source and dataset overview.

### A. Data Source
§ https://www.trustpilot.com
Trustpilot.com is a consumer review website founded in Denmark in 2007. It hosts
reviews of businesses worldwide and there are nearly 1 million new reviews are posted
each month.
§ https://www.influenster.com/
Influenster.com is a product discovery and reviews platform for consumers with 880,000
new reviews generated each month. It is mainly for North America.
§ https://www.facebook.com/
Facebook (FB) is an American online social media and social networking service. 

### B. Method
We used package selenium to do the web-scraping.

### C. Dataset Overview
* GrubHub: 6201 records with 8 columns
* Name: The person who writes the review
* Review: The most important part of our analysis
* Review_Count: The number of reviews by the particular user overall on
trustpilot.com
* Rating: The numbers from 1 to 5. One means the worst and five is the best.
* Verified Bool: 0 or 1. One means that the user was invited by grubhub.com on
trustpilot.com to review Grubhub.
* DateTime: The date and time the person writes the review.
* Location: The city and country where the person writes the review. If there is no
location, it would be 0.

## III. DATA CLEANING
1. Replace number by words
2. Remove punctuations
3. Convert to lower case
4. Stem word - Stemming is the process of reducing inflected (or sometimes derived)
words to their word stem, base or root form. For example, investment, investing,
invested, and investor all have the same root – invest.
5. Remove stop words

## IV. EXPLORATARY DATA ANALYSIS
In this section, we will take a deep look on the dataset – Grub Hub and Uber Eats. We
have an interesting finding here. The first two charts show the overall rating distribution.
Over 40% reviews in Grub hub are rating one star and 35% are rating five stars. But most
reviews in Uber Eats are rating one. If we just take a look at these two plots, we would
say Grub hub has a better overall performance than Uber Eats.

#### first image over here

Why their overall reviews have a significant different? Do Grub hub has a better service
than Uber Eats? We find the answer in the following histogram, we bring in a new
attribution - verified bool. ‘1’ means customers are invited by Grub hub and ‘0’ means
customers are not invited. Obviously, Grub hub invited customers to write reviews while
Uber Eats didn’t. The majority people who are invited tend to give five stars, people who
are not invited are mostly give one star. Our assumption is Grub hub will give customers
rewards if they give a higher star rating.
This is an interesting finding. If we only focus on the people who are not invited. Grub
Hub and Uber Eats seems perform indifference. We doubt at the credibility of those
reviews written by who are invited.

#### second image over here

## V. INSIGHT

Based on the result from sentiment analysis. We give reviews three labels. If sentiment
score less than 0, we label it as –1, if sentiment score larger than 0.1, we label it as 1,
score between 0 and 0.1, we label it as neutral.
After labeling all reviews, we use lemmatization to convert all words to its original
format and use counter, bigrams and trigrams functions in nltk package to check words
combination frequency, so that we can get the ideas about what people are talking
specifically in the positive, negative and neutral reviews.
We classified those words into four categories and those four tables are our findings.

1. Driver
Positive customer service, great experience, great food
Neutral promo code, delivery instruction, delivery charge
Negative driver lie, delivery service, English, GPS, rude driver

2. Food
Positive great service, great selection, great app
Neutral customer service representative, coupon code, credit card
Negative poor customer service, delivery service, customer care, bad
experience, cold food

3. Delivery
Positive favorite restaurant, friendly delivery people
Neutral delivery time, order online, extra tip, replacement
Negative wrong order, wrong address, delivery fee, restaurant fault –
business owner

4. Services
Positive free food, fast service, quick refund
Neutral money back, first time, bank fault
Negative Promo code, poor customer support, wrong address record,
business day refund, delivery fee, gift card, call multiple times

## VI. CONCLUSION
1. The star rating is consistent with the emotion of review.
2. Without those invitation reviews, the performance of Uber Eats and Grub Hub are
similar.
3. People who are invited to write the review truly give higher score.
4. Overall performance for Uber Eats and Grub Hub are not ideal. Most of the reviews
are negative.
5. For the negative reviews side, there are problems on the bad driver, poor customer
service, and order problem. Uber Eats should take notice and could make an
improvement on these parts.


