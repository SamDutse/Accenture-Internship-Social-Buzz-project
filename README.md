# Accenture-Internship-Poject-Social-Buzz
![](SocialBuzzGraphics.png)

## INTRODUCTION
During my virtual Internship, I had the opportunity of working on a project for a company called **Social Buzz** which is a fast growing Technology unicorn that needs to adapt quickly to its global scale. The social media and content creator company houses a huge data of 100,000 per day and an approximate 36,500,000 per year which grow in time, with much people joining social Buzz in time.

## PROBLEM STATEMENT
Our team at **Accenture** has begun a 3 months **POC** (Proof of concept) focusing on these task:
1.	An audit Social Buzz big data
2.	Recommendations for a successful **IPO** (Initial Public Offering)
3.	**Analysis to find Social Buzz Top 5 most popular category of content.**

The most relevant task assigned to me as a data analyst and what I will be working on is 
-	Analysis of sample data sets with visualizations to understand the popularity of different content categories
## DATA SOURCING
I was provided with 7 datasets and a data model. I didn’t need all the datasets to complete my task or analysis.
So, the first step is to use this data model to identify which datasets will be required to answer your business question - **which is to figure out the top 5 categories with the largest popularity.**
I identify three out of the seven data sets which I will need to complete my analysis and they are;
-	Reaction with 25,553 Rows and 5 Columns
-	Content with 1,001 Rows and 4 Columns
-	Reaction Types with 17 Rows and 4 Columns
## DATA TRANSFORMATION/CLEANING
Data was efficiently cleaned and transformed using Excel, some of the applied steps are
-	First I apply filter using **crtl+shift+L** to the Reaction table which will be the base of connecting the other tables.
-	Selecting blanks under the **Types** column and removing them, which reduces the number of rows by 980
-	The user ID is irrelevant to answering our business task, so we deleted the column in both the reaction and content table.
-	Next was to remove data that are not in the proper format, e.g. some fields under the **Type** column are having a **“ “**, attach to the same values, so I perform a replacement using **ctrl+H**, to replace the quotations mark with empty fields.
-	Remove columns from the three tables that are not relevant to the business task
## DATA MODELLING 
To find out the top 5 categories. I created a data model, using these steps:
-	I Created a final data set by merging the three tables together using **=VLOOKUP(B2,Content.csv!$B$2:$D$1001,2,FALSE)
-	Category
-	=VLOOKUP(B2,Content.csv!$B$2:$D$1001,3,FALSE)
-	Sentiment
-	=VLOOKUP(C2,ReactionTypes.csv!$B$2:$D$17,2,FALSE)
-	Score
-	=VLOOKUP(C2,ReactionTypes.csv!$B$2:$D$17,3,FALSE)
-	** with the Reaction table as the base table
-	Figure out the Top 5 performing categories using **Pivot tables** and run some insightful findings that will help the company.
## DATA ANALYSIS AND VISUALIZATION
![](Social_Buzz.png)
1.	From the above Report 16 Unique categories were identified.
2.	The top 5 most popular category of content are **Animal, Science, Health eating, Technology and Food**
3.	A time series Analysis Carried also shows that the months with high content posts or interactions was **May** follow by **January** but the **Holiday season of December and the next month of January carried highest consecutive months of high interactivity**
4.	Content Type also reveals that photos is mostly used follow by video, then GIF and the audio
5.	Reaction type used often is the heart, users exchange more of pleasant feeling towards each other, hence modifications with better user experience should be applied to some of the most used reaction type.
6.	Generally positive sentiment is mostly shared by users about 56% out of hundred are positive.

## CONCLUSION AND RECOMMENDATION
-	Out of the seven dataset provided, three were useful for solving our business task.
-	The entire dataset was 24,000 + in number
-	I identified 16 unique categories in the content provided by social Buzz
-	The Top 5 most performing category were; **Animal, Science, Health eating, Technology and Food.** Hence, more features relating to above contents need to be added or conversation about them sparked using influencers or content creators
-	Time series also shows months of **May and January** as the top 2 and Holiday seasons of December and beginning of the year as months with highest consecutive post.

## ADDITIONAL KNOWLEDGE TO ANALYST
Alternatively we can use SQL to join the table 
SQL: joining the tables using
>SELECT
>>React.F1,
>>React.[Content ID],
>>React.Type,
>>React.Datetime,
>>Cont.Type,
>>Cont.Category,
>>React_T.Sentiment,
>>React_T.Score

>FROM

>>samdutse.dbo.Reaction$ AS React


>INNER JOIN

>>samdutse.dbo.Content$ AS Cont

>>>ON React.[Content ID] = Cont.[Content ID]


>INNER JOIN

>>Samdutse.dbo.Reaction_Types$ AS React_T

>>>ON React.Type = React_T.Type

### DEFINITION
POC: A Proof of concept is a demonstration of a product, service or solution in a sales context. A POC should generally demonstrate that the product or concept will fulfill a customer requirement while also providing a compelling case of adoption
