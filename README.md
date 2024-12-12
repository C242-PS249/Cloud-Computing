# Cloud-Computing
Welcome to the cloud computing repository. This repository contains the code and deployment for the cloud computing capstone project. The project is written in Node.js using Hapi framework. The project is then deployed on the Google Cloud Platform and uses the Google Cloud Storage, Cloud Firestore, and Google Cloud Run services.

## Project Description
We will integrate all the three learning paths (Machine Learning, Cloud Computing, and Mobile Development) using Google Cloud Platform

### API Features:
- Predict Batik Class

    Enable user tu upload an image to predict batik class.
- Metadata:

    Users can view comprehensive details about each batik pattern, helping them understand its origin, philosophy, and history
- History:
  
    Enables users to access and review previous predictions and metadata.

## Cloud Architecture
<div align="center">
    <img src="https://storage.googleapis.com/service-acc/cloud%20architecture/BatikLens.png" alt="Cloud Infrastructure" width="700" height="400">
</div>

## Prerequisites
- Cloud Storage (Open access to public)
- Firestore database
- Artifact Registry
- Service Account with required permission (Write)

## Installation
### Run Locally

Clone the project
```bash
git clone https://github.com/C242-PS249/Cloud-Computing.git
```

Go to the project directory
```bash
cd Cloud-Computing
```

Install dependencies
```bash
npm install
```

Start the server
```bash
npm run start
```

*Feel free to modify the code to suit your requirements and needs*

## Usage

After successfully deploying the application to Cloud Run on Google Cloud Platform, you should test it using Postman or any other API testing tool.

#### Get Batik Metadata

```http
  GET /batikmetadata
```

| Parameter (query) | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `asalBatik` | `string` | **Required**. Specific item |
| `filosofiBatik` | `string` | **Required**. Specific item |
| `namaBatik` | `string` | **Required**. Specific item |
| `sejarahBatik` | `string` | **Required**. Specific item |

#### Get User History

```http
  GET /history
```

| Parameter (query) | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `confidenceScore` | `string` | **Required**. Specific item |
| `createdAt` | `timestamp` | **Required**. Specific item |
| `id` | `string` | **Required**. authentication |
| `idBatik` | `string` | **Required**. Specific item |
| `result` | `string` | **Required**. Specific item |

#### Predict Image

```http
  POST /predict
```

| Parameter (query) | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `confidenceScore` | `string` | **Required**. Specific item |
| `createdAt` | `timestamp` | **Required**. Specific item |
| `id` | `string` | **Required**. authentication |
| `idBatik` | `string` | **Required**. Specific item |
| `result` | `string` | **Required**. Specific item |

## Contact

Wahyu Prasetya - [LinkedIn](https://www.linkedin.com/in/wahyuprasetya2110/)  
Bryantnata Imam Safi'i - [LinkedIn](https://www.linkedin.com/in/bryantnata-imam-safi-i-204a7223a/)
