# Book Recommender System

This repository contains the implementation of a Book Recommender System using collaborative filtering. The system is designed to suggest books to users based on their reading history and preferences.

## Table of Contents
1. [Introduction](#introduction)
2. [Recommendation System Overview](#recommendation-system-overview)
   - [Definition and Purpose](#definition-and-purpose)
   - [Types of Recommendation Systems](#types-of-recommendation-systems)
3. [Book Recommender System with Collaborative Filtering](#book-recommender-system-with-collaborative-filtering)
4. [Data Collection and Preprocessing](#data-collection-and-preprocessing)
   - [Datasets](#datasets)
   - [Preprocessing Steps](#preprocessing-steps)
5. [Model Implementation](#model-implementation)
   - [Creating the User-Book Interaction Matrix](#creating-the-user-book-interaction-matrix)
6. [Conclusion](#conclusion)

## Introduction

This project implements a Book Recommender System using collaborative filtering to provide personalized book recommendations based on user ratings and preferences.

## Recommendation System Overview

### Definition and Purpose

A recommendation system is a subclass of information filtering systems that seeks to predict the "rating" or "preference" a user would give to an item. The main purpose of a recommendation system is to enhance the user's experience by suggesting items that are most relevant to their tastes and preferences.

### Types of Recommendation Systems

1. **Collaborative Filtering**: Builds a model from a user's past behavior (items previously purchased or rated) as well as similar decisions made by other users.
   - **User-Based Collaborative Filtering**: Recommends items based on similarity between users.
   - **Item-Based Collaborative Filtering**: Recommends items based on similarity between items.

2. **Content-Based Filtering**: Uses item features to recommend other items similar to what the user likes, based on their previous actions or explicit feedback. For instance, if a user likes a book, the system will recommend other books that have similar attributes (e.g., genre, author).

## Book Recommender System with Collaborative Filtering

Our Book Recommender System employs collaborative filtering to provide personalized book recommendations. The system uses user ratings to find similarities between users and books, enabling it to suggest books that users with similar tastes have liked.

## Data Collection and Preprocessing

### Datasets

The dataset used for this project is obtained from [Kaggle](https://www.kaggle.com/datasets/ra4u12/bookrecommendation) and includes:
- **BX-Books**: Contains information about the books.
- **BX-Book-Ratings**: Contains user ratings for different books.
- **BX-Users**: Contains information about the users.

### Preprocessing Steps

1. **Filtering Users**: Select users who have rated more than 200 books.
2. **Merging Datasets**: Merge the ratings dataset with the books dataset to include book information.
3. **Filtering Books**: Filter books that have been rated more than 50 times to ensure a good amount of information.

## Model Implementation

### Creating the User-Book Interaction Matrix

Create a pivot table where rows represent book titles and columns represent user IDs, with the values being the ratings.

```python
book_pivot = final_rating.pivot_table(columns='user_id', index='title', values='rating')

### Building the Collaborative Filtering Model
Use the Nearest Neighbors algorithm to find similar books and generate book recommendations.

## Conclusion
The **Book Recommender System** effectively provides personalized book recommendations using collaborative filtering. The system leverages user rating data to identify similar books and users, offering tailored suggestions.
