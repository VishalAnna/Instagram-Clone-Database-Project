## Instagram Clone Database

Welcome to the Instagram Clone Database repository! This project is a SQL-based representation of a simplified Instagram clone, showcasing the database schema and tables required for core features of a social media platform.

## Table of Contents

- [Introduction](#introduction)
- [Schema](#schema)
- [Tables](#tables)
- [Queries](#queries)


## Introduction

This project aims to demonstrate the database structure needed for creating an Instagram-like social media platform. It includes tables for users, photos, comments, likes, followers, tags, and more.

## Schema

The database schema consists of several interconnected tables that enable different features of the platform.

![Database Schema](https://github.com/VishalAnna/Instagram-Clone-Project/assets/95202004/320c680a-b289-43c9-a1d0-07d169c2bdc0)
## Tables


## Table 1: users
- Columns:
  - `id`: INT (Primary Key, Auto Increment)
  - `username`: VARCHAR(255), NOT NULL
  - `created_at`: TIMESTAMP, Default: NOW()
- Description: This table stores information about users who are registered on the platform. Each user has a unique ID, a username, and a timestamp indicating when they joined.

## Table 2: photos
- Columns:
  - `id`: INT (Primary Key, Auto Increment)
  - `image_url`: VARCHAR(355), NOT NULL
  - `user_id`: INT, NOT NULL (Foreign Key referencing users.id)
  - `created_at`: TIMESTAMP, Default: NOW()
- Description: The photos table holds details about uploaded photos. It includes a unique photo ID, the URL to the image, the user ID of the uploader, and a timestamp indicating when the photo was uploaded.

## Table 3: comments
- Columns:
  - `id`: INT (Primary Key, Auto Increment)
  - `comment_text`: VARCHAR(255), NOT NULL
  - `user_id`: INT, NOT NULL (Foreign Key referencing users.id)
  - `photo_id`: INT, NOT NULL (Foreign Key referencing photos.id)
  - `created_at`: TIMESTAMP, Default: NOW()
- Description: This table stores comments made on photos. It contains a unique comment ID, the comment text, the user ID of the commenter, the photo ID on which the comment was made, and a timestamp for the comment creation.

## Table 4: likes
- Columns:
  - `user_id`: INT, NOT NULL (Foreign Key referencing users.id)
  - `photo_id`: INT, NOT NULL (Foreign Key referencing photos.id)
  - `created_at`: TIMESTAMP, Default: NOW()
- Description: The likes table tracks the likes given to photos. It uses a composite primary key (user_id, photo_id) to prevent duplicate likes from the same user on the same photo.

## Table 5: follows
- Columns:
  - `follower_id`: INT, NOT NULL (Foreign Key referencing users.id)
  - `followee_id`: INT, NOT NULL (Foreign Key referencing users.id)
  - `created_at`: TIMESTAMP, Default: NOW()
- Description: This table maintains the relationship between users who follow each other. It uses a composite primary key (follower_id, followee_id) to prevent duplicate follow entries.

## Table 6: tags
- Columns:
  - `id`: INT (Primary Key, Auto Increment)
  - `tag_name`: VARCHAR(255), UNIQUE, NOT NULL
  - `created_at`: TIMESTAMP, Default: NOW()
- Description: The tags table stores unique tag names that can be associated with photos. Each tag has a unique ID and a timestamp indicating when it was created.

## Table 7: photo_tags
- Columns:
  - `photo_id`: INT, NOT NULL (Foreign Key referencing photos.id)
  - `tag_id`: INT, NOT NULL (Foreign Key referencing tags.id)
- Description: This junction table establishes a many-to-many relationship between photos and tags. It enables photos to have multiple tags and tags to be associated with multiple photos. The composite primary key (photo_id, tag_id) ensures uniqueness.



## Queries

The project SQL files include sample queries to interact with the database. These queries include retrieving user posts, adding comments, getting likes, and more

[Here are some SQL queries and there answers based on the above schema](https://github.com/VishalAnna/Instagram-Clone-Project/blob/6d0271f2285bec0af53e2323d9c241c6695d319e/15.Instagram%20Clone%20Database%20-%20Challenges.sql)







