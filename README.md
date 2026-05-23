# Real Estate Price Predictor

Full-Stack ML Web App for Bangalore Real Estate Price Prediction

# 🛠️ Tech Stack & Tools
 ![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Flask](https://img.shields.io/badge/Flask-000000?style=for-the-badge&logo=flask&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/scikit--learn-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?style=for-the-badge&logo=pandas&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white)
![HTML5](https://img.shields.io/badge/HTML-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![jQuery](https://img.shields.io/badge/jQuery-0769AD?style=for-the-badge&logo=jquery&logoColor=white)
![Flask-CORS](https://img.shields.io/badge/Flask--CORS-black?style=for-the-badge)
![Git](https://img.shields.io/badge/Git-F05032?style=for-the-badge&logo=git&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=for-the-badge&logo=nginx&logoColor=white)

---
# 📌 Project Overview

The application allows users to estimate the price of a house in Bangalore based on features such as area (in square feet), number of bedrooms (BHK), number of bathrooms, and location. The prediction is powered by a machine learning model trained on real-world housing data.

# 🤖 Machine Learning Model

## Type
Supervised Regression — Linear Regression

## Features Used

- Total square footage
- Number of bathrooms
- Number of bedrooms (BHK)
- Location (One-Hot Encoded)

## Training Dataset

- Bangalore House Price Dataset
- Extensive preprocessing performed:
  - Data cleaning
  - Outlier removal
  - Feature engineering
  - One-hot encoding
 
## Artifacts:

- Trained model serialized as banglore_home_prices_model.pickle
- Feature/column metadata in columns.json

# ⚙️ Backend — Flask REST API

- Framework: Python Flask
- Endpoints:
  - GET /get_location_names — Returns all available locations for the dropdown
  - POST /predict_home_price — Accepts form data and returns the predicted price
- Model Loading:
  - Loads the pickled model and column metadata at startup (or on first request)
- Prediction Flow:
  - Receives user input, constructs a feature vector/DataFrame, and returns the model's price prediction
- CORS:
  - Configured to allow cross-origin requests from the frontend (for local/dev and production)
# 🎨 Frontend
 Technologies
 - HTML
 - CSS
 - JavaScript
 - jQuery
 Features
 - Dynamic location dropdown
- Interactive user interface
- Real-time price prediction
- Responsive UI design
- API integration with Flask backend

# 🏗️ Project Architecture

```text
User (Browser)
      │
      ▼
Frontend UI (HTML/CSS/JS)
      │
      ▼
Flask REST API
      │
      ▼
Machine Learning Model (Pickle) + Feature Metadata (JSON)
      │
      ▼
Predicted House Price
```

# Technical Highlights

- End-to-end ML pipeline: Data cleaning, feature engineering, model training, serialization
- API-first backend: Clean separation of model logic and HTTP interface
- Modern frontend: Angular standalone components, Tailwind for rapid UI development
- Production-ready: Dockerized backend, CORS, environment-agnostic frontend
- Extensible: Easy to swap out the ML model, add new features, or adapt to other cities

# Authors & Credits

 - ML, backend, and frontend: Ardra Sunil
 - Data: Banglore Housing Dataset(public sources)
   
For more details on the ML pipeline, API contract, or frontend architecture, see the code and comments in each respective directory.

# Table of Contents

- [Installation](#installation)
- [Usage](#usage)
- [Features](#features)
- [Repository Contents](#repository-contents)
- [Contributing](#contributing)
- [License](#license)

# Installation

1. Clone the repository:

```bash
git clone https://github.com/yourusername/real-estate-price-prediction.git
```

2. Navigate to the project directory:

```bash
cd real-estate-price-prediction
```

3. Install the required packages:

```bash
pip install -r requirements.txt
```

# Usage

1. Run the Flask server:

```bash
cd server
python3 server.py
```

2. Open the frontend using Live Server:

```bash
http://127.0.0.1:5500/client/app.html
```

# Features

- Data preprocessing
- Model training
- Model evaluation
- House price prediction

# Repository Contents

| File/Folder | Description |
|---|---|
| `app.html` | Frontend HTML page for the project UI. |
| `app.css` | Styling for the frontend interface. |
| `app.js` | Frontend JavaScript logic and API integration. |
| `server.py` | Flask backend server with REST API endpoints. |
| `util.py` | Utility functions for loading model and prediction logic. |
| `columns.json` | JSON file containing feature column names. |
| `real_estate.ipynb` | Jupyter Notebook for the project. |
| `Bengaluru_House_Data.csv` | Dataset used for model training. |
| `README.md` | This README file. |

# Code Excerpt

```python
import json

columns = {
    'data_columns': [col.lower() for col in x.columns]
}

with open('columns.json', 'w') as f:
    f.write(json.dumps(columns))
```

