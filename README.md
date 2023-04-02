# Reddit-Comments-about-ChatGPT---EDA
Explanatory Data Analytics for Reddit Comments about ChatGPT

### Background
Reddit, a popular online platform, is a treasure trove of user-generated content, discussions, and interactions. The platform allows users to submit content, engage in discussions, and vote on submissions in various topic-based communities called subreddits. As a result, Reddit data provides a rich and diverse dataset for natural language processing (NLP) tasks and understanding human conversations.

One of the most intriguing aspects of Reddit is the wealth of conversational data available. The Reddit ChatGPT dataset is an extensive collection of conversations and exchanges between Reddit users, making it an excellent resource for building and training AI models that can understand and generate human-like responses. The dataset is particularly valuable for developing advanced NLP models, like OpenAI's ChatGPT, which is based on the GPT-4 architecture.

In this study, we will perform an Exploratory Data Analysis (EDA) on the Reddit ChatGPT dataset to gain insights into its structure, content, and potential applications. EDA is an essential step in data science projects as it helps identify patterns, trends, and anomalies in the data, which can guide subsequent model building and evaluation processes.

### Methods

#### Data Cleanning

Data cleaning is an essential step in the data analysis process. The quality of the data can significantly impact the accuracy and reliability of the analysis results. In this case, the data is Missing Completely At Random (MCAR), which means that the missing values are not related to any of the observed or unobserved variables in the dataset. To clean the data, we follow the steps outlined below:

1. Check the percentage of missing values for each column: We need to determine the extent of missingness in the dataset to determine the appropriate imputation method. We can calculate the percentage of missing values for each column to identify the columns with the highest missingness.

1. Visualize the missing values by heat map: We can create a heat map to visualize the distribution of missing values across the dataset. This visualization can help us identify patterns of missingness, such as missing values occurring in specific rows or columns. And also there are some columns always missing together, which also show more pattens in the data.

1. Delete columns with missing values above 80%: If a column has more than 80% missing values, we may choose to delete that column. This decision is based on the assumption that a column with such high missingness may not be useful in our analysis. From the plot of the heatmap, the last 2 columns almost completely missing and no column name to describe its information.

1. Impute missing values using mean or mode for the same subreddit and parent_post: For columns with missing values that we choose to keep, we can impute the missing values using the mean or mode of the observed values for the same subreddit and parent_post. This imputation method is appropriate when the missingness is MCAR. When some post's parent_post are also missing, then impute the missing by only use the same subreddit. 

1. Fill timestamp column by post_timestamp with rescaling: We observe that the column "timestamp" has a very high correlation (0.97) with another column "post_timestamp". Therefore, we can use the "post_timestamp" column to impute the missing values in "timestamp". To do this, we can fill the missing values in "timestamp" using the corresponding values in "post_timestamp". However, since "timestamp" and "post_timestamp" may have different scales, we need to rescale "post_timestamp" to the same scale as "timestamp" before filling the missing values.

##### Generate more information from text words:
* Length of comment
* Presence of anger
* Presence of joy
* Presence of special non alphanumeric character
* Number of stop words

##### Preprocess the text words
* Lowercase
* Remove Numbers
* Remove extra spaces
* Convert short words such as I'm, He's
* Remove punctuations
* Remove stop words

##### Preprocess the date

* Extract date information to year, month, day, weekdays and hour

#### Data Visualization
* AFINN scores plots for different categories
* Word Clouds
* Word Frequency Counts
* PCA Plot with number of components
* K-means with-in cluster distance plot
* K-means Silhouette score plot
* K-means segmentation plot

#### Models
* Possion GLM
* Logistic GLM
* XGBoost

### Solutions
In this section, I present the findings and solutions derived from our analysis of the Reddit ChatGPT dataset. Based on the data cleaning, preprocessing, visualization, and modeling techniques applied, the following insights and solutions were obtained:

Sentiment Analysis: By using the AFINN scores and visualizing the results, we were able to identify the general sentiment of comments in different subreddits and categories. This information can be helpful in understanding user opinions and emotions about ChatGPT and tailoring AI responses accordingly.

Keyword Analysis: Through the use of Word Clouds and Word Frequency Counts, we identified the most common and important keywords present in the dataset. These keywords can be used to guide the development of AI models and inform their understanding of the relevant topics discussed on Reddit about ChatGPT.

Dimensionality Reduction and Clustering: By applying PCA and K-means clustering, we discovered underlying patterns and structures in the dataset that may not be immediately apparent. These insights can be used to inform the development of AI models and improve their ability to generate contextually relevant responses.

Predictive Modeling: The application of Poisson GLM, Logistic GLM, and XGBoost models allowed us to identify significant features and relationships in the data. These models can be used to predict various outcomes and inform AI model development, such as predicting user engagement, sentiment, or the likelihood of a comment being highly upvoted.

In conclusion, the EDA performed on the Reddit ChatGPT dataset provided valuable insights that can be leveraged to improve the performance of AI models like ChatGPT. By understanding the underlying patterns, trends, and anomalies in the data, we can inform and guide subsequent model building and evaluation processes, leading to more accurate and contextually relevant AI-generated content on Reddit.
