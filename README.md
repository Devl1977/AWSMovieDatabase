# My Movie Database (AWS Migration)

## Section 1 - Project Description

### 1.1 Project Name
**My Movie Database (AWS Migration)**

### 1.2 Description
My Movie Database is a web application that allows users to discover movies, manage their watchlist, and view details such as genres, ratings, and release dates. The application integrates with **The Movie Database (TMDB) API** to fetch movie data and is being migrated to **AWS** for improved scalability, performance, and availability.

The AWS migration replaces the traditional backend setup (**Express.js & MongoDB**) with a **fully serverless architecture** using:
- **AWS Lambda** (Backend functions)
- **Amazon API Gateway** (Routing API requests)
- **DynamoDB** (Database for users & watchlists)
- **Amazon Cognito** (User authentication)
- **Amazon S3** (Static file storage)
- **AWS CloudWatch**
- **AWS IAM**
- **AWS Amplify** (Frontend hosting) : Attempted however never utilized, went a different route.

## Section 2 - Overview

### 2.1 Purpose
The purpose of this migration is to modernize the My Movie Database backend by leveraging AWS services to provide **a scalable, reliable, and cost-effective** infrastructure. This transition will:
- Improve **performance** and **availability**
- Allow **seamless watchlist management**
- Integrate **authentication via AWS Cognito**

### 2.2 Scope
#### ✅ Included in This Migration:
- Migrating backend from **Express.js & MongoDB** → **AWS Lambda & DynamoDB**.
- Hosting frontend using **AWS Amplify**, This was the intention however ended up going static website through S3 bucket hosting the Index and Profile htmls along side lambda functions.
- Storing static assets (e.g., user avatars) in **Amazon S3**.
- Implementing **API Gateway** for client-server communication.
- Using **Cognito** for authentication & authorization.
- The use of IAM roles and permissions when needed.
- Using **AWS Cloudwatch** to maintain and monitor metrics.

#### ❌ Not Included in This Milestone (Planned for Final Project):
- **TV Show Search** (The search was specific to TMDB movie api).
- **AI-Based Recommendations**
- **Live Streaming** (along side trailers)


## Section 3 - System Architecture

### 3.1 Overview
The new system follows a **serverless AWS architecture**, where the **frontend communicates with API Gateway**, which then routes requests to AWS Lambda functions. These functions interact with DynamoDB for data storage, while user authentication is managed using Amazon Cognito.

### 3.2 Architectural Diagram
> *[Insert System Architecture Diagram Here]*

## Section 4 - Data Dictionary

### **Users Table**
| Field          | Description                               | Type   |
|---------------|-------------------------------------------|--------|
| UserID        | Unique user identifier                    | String |
| Name          | User's full name                          | String |
| Email         | User's email address                      | String |
| ProfilePicture | Link to profile picture stored in S3    | String |

### **Watchlist Table**
| Field         | Description                              | Type   |
|--------------|------------------------------------------|--------|
| WatchlistID  | Unique identifier for each watchlist entry | String |
| UserID       | Foreign key linking to Users table       | String |
| MovieID      | Identifier for the movie added to the watchlist | String |

## Section 5 - Data Design
The system uses **DynamoDB** as a NoSQL database, with separate tables for **Users** and **Watchlists**. Relationships are maintained via **UserID references**.

## Section 6 - User Interface Design

### 6.1 UI Overview
The UI is built using **React.js** and is hosted on **AWS Amplify**.

### 6.2 UI Navigation Flow
> ![2025-03-19_22h02_09](https://github.com/user-attachments/assets/b2348337-35ce-4432-86aa-65a9794e331a)


### 6.3 Use Cases / User Functions
- ✅ Users can **search for movies** 
- ✅ Users can **add movies to their watchlist**.
- ✅ Users can **view & manage their watchlist**.

---

## 🚀 Completed Steps from last project overview
This serves as a **high-level overview** of the migration process. Future milestones will include:
1. **Implementing API Gateway & Lambda for Search**    ✅  Successfully implimented 
2. **Adding Authentication with Cognito**  -- ✅  Successfully implimented
3. **Deploying the Frontend via AWS Amplify**  -- ✅  Successfully implimented However, pivoted towards using static website via s3 bucket, lambda functions.
