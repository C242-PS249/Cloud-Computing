# Cloud-Computing
Welcome to the cloud computing repository. This repository contains the code and deployment for the cloud computing capstone project. The project is written in Node.js using Hapi framework. The project is then deployed on the Google Cloud Platform and uses the Google Cloud Storage, Cloud Firestore, and Google Cloud Run services.

## Project Description
We will integrate all the three learning paths (Machine Learning, Cloud Computing, and Mobile Development) using Google Cloud Platform

### API Features:
- Predict Batik Class

    Enable user to upload an image to predict batik class.
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

#### Get All Batik Metadata 
```http
GET /batikmetadata
```

| Parameter (query) | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `namaBatik` | `string` | **Required**. Specific item |
| `asalBatik` | `string` | **Required**. Specific item |
| `filosofiBatik` | `string` | **Required**. Specific item |
| `sejarahBatik` | `string` | **Required**. Specific item |
| `url` | `string` | **Required**. Specific image with same id |

* **Status code:** 200</br>
```
{
    "success": true,
    "data": [
        {
            "id": "1",
            "namaBatik": "Batik Name",
            "asalBatik": "Batik Region",
            "filosofiBatik": "Batik Phylosophy.",
            "sejarahBatik": "Batik History.",
            "imageUrl": {
                "url": [
                    "batik-image-url-bucket"
                ]
            }
        },
    ]
}
```

#### Get Batik Metadata by ID
```http
GET /batikmetadata
```

| Parameter (query) | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `namaBatik` | `string` | **Required**. Specific item |
| `asalBatik` | `string` | **Required**. Specific item |
| `filosofiBatik` | `string` | **Required**. Specific item |
| `sejarahBatik` | `string` | **Required**. Specific item |
| `url` | `string` | **Required**. Specific image with same id |

* **Status code:** 200</br>
```
{
    "success": true,
    "data": {
        "namaBatik": "Batik Name",
        "asalBatik": "Batik Origin",
        "filosofiBatik": "Batik Phylosophy.",
        "sejarahBatik": "Batik history."
    },
    "imageUrl": {
        "url": [
            "batik-image-url-bucket"
        ]
    }
}  
```
  
#### Get User History

```http
  GET /history
```

| Parameter (query) | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `namaBatik` | `string` | **Required**. Specific item |
| `asalBatik` | `timestamp` | **Required**. Specific item |
| `filosofiBatik` | `string` | **Required**. Specific item |
| `sejarahBatik` | `string` | **Required**. Specific item |
| `url` | `string` | **Required**. A specific image with the same idBatik, idMetadata, and idImage |

* **Status code:** 200</br>
```
  {
    "success": true,
    "data": {
        "namaBatik": "Batik Name",
        "asalBatik": "Batik Origin”,
        "filosofiBatik": "Batik Philosophy.",
        "sejarahBatik": "Batik History."
    },
    "imageUrl": {
        "url": [
            "batik-image-url-bucket"
          ]
      },
      {
      etc.
      }
  }
```
  
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

* **Status code:** 200</br>
```
  {
    "status": "success",
    "message": "Model is predicted successfully. And saved to history",
    "predictData": {
        "id": "unique–uuid",
        "idBatik": “batik-id”,
        "result": "Batik Name",
        "confidenceScore": 99.60592985153198,
        "createdAt": "2024-12-10T21:26:33.139Z"
    },
    "metadata": {
        "namaBatik": "Batik Name",
        "asalBatik": "Batik Origin”,
        "filosofiBatik": "Batik Philosophy.",
        "sejarahBatik": "Batik History."
    },
    "imageUrl": {
        "url": ‘batik-image-url-bucket’
        }
  }
```

## Contact

Wahyu Prasetya - [LinkedIn](https://www.linkedin.com/in/wahyuprasetya2110/)  
Bryantnata Imam Safi'i - [LinkedIn](https://www.linkedin.com/in/bryantnata-imam-safi-i-204a7223a/)
