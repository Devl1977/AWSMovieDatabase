# 🎬 Samm’s Movie Database (AWS Serverless Migration)

## 📌 Section 1 - Project Description

### 1.1 Project Name
**Samm’s Movies (AWS Migration Project)**

### 1.2 Description  
This is a serverless movie discovery and watchlist management application, migrated from a traditional stack (**Express + MongoDB**) to **fully AWS-managed services**. The app allows users to **search for movies**, **manage their personal watchlists**, **upload profile pictures**, and **monitor activity with CloudWatch** — all while being scalable, efficient, and cost-effective.

---

## ☁️ Section 2 - AWS Services Used

| AWS Service        | Purpose                                                   |
|--------------------|-----------------------------------------------------------|
| **Lambda**         | Backend logic for searching movies, profile updates, etc. |
| **API Gateway**    | Routing HTTP requests to Lambda functions                 |
| **DynamoDB**       | NoSQL storage for Users and Watchlists                    |
| **Amazon Cognito** | Authentication & Authorization (Login, Signup, Logout)    |
| **S3**             | Static site hosting and storing profile images            |
| **CloudWatch**     | Custom metrics and alarm notifications                    |
| **SNS**            | Sends alerts from alarms to email                         |
| **IAM**            | Secured permission boundaries for each service            |

---

## 🎯 Section 3 - Key Features

- ✅ **Movie Search via TMDB API**
- ✅ **User Login & Signup via Cognito**
- ✅ **Profile Management (Names, Picture Upload to S3)**
- ✅ **Watchlist (Add/Delete Movies via DynamoDB)**
- ✅ **CloudWatch Metrics**:
  - `WatchlistActions` metric (Add/Remove)
  - `ProfileUpdates` metric (Basic Info vs Picture Upload)
- ✅ **CloudWatch Alarms**:
  - Alert when profile is updated
  - Alert when watchlist is modified
- ✅ **SNS Notifications**:
  - Email alerts triggered by alarm thresholds

---

## 🔧 Section 4 - Architecture Diagram

> ![Diagram Placeholder](https://github.com/user-attachments/assets/cf828bb4-515f-4b02-936b-e68b60ebc5d1)

---

## 🗃️ Section 5 - DynamoDB Tables

### Users Table

| Field           | Type   | Description                        |
|-----------------|--------|------------------------------------|
| UserID          | String | Email used as the primary key     |
| FirstName       | String | User’s first name                  |
| LastName        | String | User’s last name                   |
| ProfilePicture  | String | URL to the image stored in S3     |

### Watchlists Table

| Field         | Type   | Description                                |
|---------------|--------|--------------------------------------------|
| WatchlistID   | String | Unique ID for the watchlist item           |
| UserID        | String | Email to identify which user added the movie |
| MovieID       | String | ID from TMDB                               |
| MovieTitle    | String | Title of the movie                         |
| ReleaseDate   | String | Movie release date                         |
| Overview      | String | Description of the movie                   |

---

## 🧪 Section 6 - Cloud Monitoring

### 📊 CloudWatch Metrics:
- `ProfileUpdates` (Tracks Basic Info edits and Picture uploads)
- `WatchlistActions` (Tracks movie add/remove actions)

### 🚨 CloudWatch Alarms:
- Alarm if more than 5 watchlist actions happen in a minute
- Alarm if more than 2 profile updates occur in a minute

### 📩 SNS Integration:
- Alerts emailed to instructor or admin for threshold breaches

---

## 🧑‍💻 Section 7 - DevOps Practices

- All Lambda functions are **modular**, **scalable**, and use **environment-specific IAM roles**
- Static frontend is hosted via **S3** with direct link routing
- Cognito manages **session tokens** and **logout redirects**
- Frontend includes:
  - **Authentication state checks**
  - **Auto-profile creation on signup**
  - **Search without login**, but gated watchlist/profile actions

---

## 🧑‍🏫 Section 8 - For Instructors

**To access the AWS environment:**
- IAM User: `teacher-readonly`
- Attached policy: `ReadOnlyAccess`
- Please refer to AWS Management Console for Lambda, CloudWatch, Cognito, S3, and DynamoDB read-only insights

---

## 🧠 Bonus Features / UX Enhancements

- 👤 Profile picture upload via S3
- 🛑 Logged-out users cannot add to watchlist or view profile
- 🎨 Tailored alerts:
  - `⚠️ You are logged out` (red badge above search bar)
  - `✅ Logged in as:` visible on login
- 🎯 Clean logout URL hash handling

---

## ✅ Final Status

This project is **fully deployed**, **monitored**, and meets the migration requirements from local dev to **AWS Serverless Production**.
