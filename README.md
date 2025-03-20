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
- **AWS Amplify** (Frontend hosting)

## Section 2 - Overview

### 2.1 Purpose
The purpose of this migration is to modernize the My Movie Database backend by leveraging AWS services to provide **a scalable, reliable, and cost-effective** infrastructure. This transition will:
- Improve **performance** and **availability**
- Allow **seamless watchlist management**
- Integrate **authentication via AWS Cognito**

### 2.2 Scope
#### ✅ Included in This Migration:
- Migrating backend from **Express.js & MongoDB** → **AWS Lambda & DynamoDB**.
- Hosting frontend using **AWS Amplify**.
- Storing static assets (e.g., user avatars) in **Amazon S3**.
- Implementing **API Gateway** for client-server communication.
- Using **Cognito** for authentication & authorization.

#### ❌ Not Included in This Milestone (Planned for Final Project):
- **TV Show Search**
- **AI-Based Recommendations**
- **Live Streaming**
- **Movie Search will be included in the final project but is not part of this milestone.**

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
> *[Insert Navigation Flow Diagram Here]*

### 6.3 Use Cases / User Functions
- ✅ Users can **search for movies** (Planned for final version).
- ✅ Users can **add movies to their watchlist**.
- ✅ Users can **view & manage their watchlist**.

---

## 🚀 Next Steps
This serves as a **high-level overview** of the migration process. Future milestones will include:
1. **Implementing API Gateway & Lambda for Search**
2. **Adding Authentication with Cognito**  -- still reasearching this.
3. **Deploying the Frontend via AWS Amplify**  -- still reasearching this as well.
