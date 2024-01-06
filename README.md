# Forecasting-YouTube-Content
Developed many predictive models in order to predict popular YouTube content

## Overview

The goal of this project is to develop predictive models that accurately anticipate which YouTube videos are likely to become trending hits on the platform. By analyzing various video features, the project aims to provide insights into the factors contributing to a video's popularity. The predictive models explored include Decision Trees, Random Forest, XGBoost, Tuned XGBoost, K-Nearest Neighbors (KNN), and Multi-Layer Perceptron (MLP).

## Table of Contents

- [Objectives and Significance](#objectives-and-significance)
- [Dataset](#dataset)
- [Methods](#methods)
- [Results](#results)
- [Conclusion](#conclusion)
- [Usage](#usage)
- [Future Scope](#future-scope)


## Objectives and Significance

The goal of this project is to develop predictive models that can accurately anticipate which YouTube videos are likely to become trending hits on the platform.This entails analyzing a range of video features to give insights into the aspects that contribute to the popularity and success of a video. By improving content development tactics, viewer engagement, and the overall user experience on YouTube, the initiative aims to empower content producers, advertisers, and viewers. Furthermore, it adds to data analysis, machine learning, and digital marketing research by providing useful insights into developing media trends.


The ability to forecast popular videos may lead to higher viewing, subscription growth, and income generation for content providers and marketers. Market researchers and marketers learn about consumer behavior and preferences in the digital media ecosystem. Our motivation for taking on this project stems from our firm belief that data-driven decision-making may lead to great outcomes in the digital age. By creating predictive models for YouTube video, we hope to help content producers succeed and viewers be satisfied, while also expanding our understanding of how data analytics can be used in digital media platforms.This initiative is in line with our desire to use technology and data to create significant and lasting contributions in the digital domain.

## Dataset
The YouTube Trending Video Dataset from Kaggle is used for this project. This dataset is a structured and enhanced version of YouTube's own compilation of top-trending videos. It spans multiple regions, including India, the United States, Great Britain, Germany, Canada, France, Russia,Brazil, Mexico, South Korea, and Japan out of which we chose the dataset corresponding to the United States region.  Our original dataset (before pre-processing) consisted of 16 attributes and 236787 data points. The attributes were: video_id,title, publishedAt, channelId, channelTitle, categoryId, trending_date,  view_count, description, likes, dislikes, comment_count, tags, thumbnail_link, comments_disabled, ratings_disabled.
The brief description of each attribute and other details regarding the dataset are available on this website: https://www.kaggle.com/datasets/rsrishav/youtube-trending-video-dataset

Engagement metrics refer to the quantitative measures that assess the level of interaction, participation, and involvement that users have with a particular piece of content or platform. In this dataset, the engagement metrics are:
•	view_count: The number of times the video has been viewed, a key indicator of popularity.
•	likes: Reflects the positive engagement from viewers.
•	dislikes: Indicates the level of controversy or disagreement surrounding the video.


## Data Preprocessing

•	Loaded the data in a dataframe.

•	Created a new column, "days_to_trend," by calculating the difference between the existing columns "trending_Date" and "published_date."

•	Dropped all the rows containing null values from the dataframe.

•	Converted the categorical columns "title" and "tags" into numerical columns.

For the "title" column:

•	Removed non-ASCII values from the column.

•	Loaded stop words from the NLTK library to eliminate stop words from the column.

•	Updated the original dataframe after making the above changes.

•	Obtained the total frequency of each unique word in the column and replaced the word with that frequency, ensuring each row in the "title" column is a list of total frequency values in the column.

•	Calculated the sum of the values of each row and placed those values in a new column called "title_frequency_sum."

For the "tags" column:

•	Rows of tags have values like "Disney|Disney Dreamlight Valley|Gameloft," where the tags of the YouTube videos are separated using the "|" character.           

•	 Splitted these tags using the "|" character and calculated the total occurrences of the tags in the entire column.

•	Similar to "title," calculated the sum of the values of tags in each row and placed those values in a new column called "tag_frequency_sum."

##Feature Selection & Dataset Splitting

•	Used the relevant existing and two new numerical columns from the dataset as features. These columns are ['likes', 'dislikes', 'comment_count', 'categoryId', 'title_frequency_sum', 'tag_frequency_sum', 'days_to_trend'].

•	Considered "view_count" as the "Y_label."

•	Split the dataset into three sections: Train (50%), Tune (25%), and Test (25%).

##Procedure

•	Selected Decision Tree Regressor, Random Forest Regressor,XG Boost, Tuned XGBoost, KNN and MLP as the models to predict the "Y_label."

•	Initially trained all the models using the Training dataset (50%).

•	Then,used the tuned dataset for hyperparameter tuning and found the best parameters for each model.

•	Tested these three models on the Test set (25%), compared the results, and concluded on the best model.

•	Further, based on the results obtained, realized that the Decision Tree model was overfitting the dataset. Hence, extended the scope of the project and performed feature scaling and pruning on the Decision Tree model.

•	Similarly, for XG Boost, extended and tuned the XG Boost model, thereby implementing tuned XG Boost. 

• All the models were evaluated on R^2 score. It ranges from 0 to 1. 1 implies that the performance of the model is exceptional while 0 indicates that the performance of the model is very poor.

## Results

Details the results obtained from the implemented models, including data visualizations, R-squared scores, and comparisons between different models. 

## Conclusion

Summarizes the findings, highlights the best-performing models, and offers insights into the project's success. It may also mention limitations and potential areas for improvement.

## Usage

Provides instructions on how to clone the repository, set up the environment, and run the code. Include any dependencies or specific configurations required.

## Future Scope

Outlines potential future enhancements or expansions for the project, such as incorporating image features, diversifying the dataset, or transforming the task into a binary classification problem.

## Contributing

If you wish to contribute to this project, please follow the guidelines outlined in the CONTRIBUTING.md file.

## License

This project is licensed under the [MIT License](LICENSE).

