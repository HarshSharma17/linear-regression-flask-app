# 🔥 Fire Weather Index Prediction using Ridge Regression & Flask

An end-to-end Machine Learning project that predicts the **Fire Weather Index (FWI)** using **Ridge Regression**, with a Flask-based web application for making predictions through a simple web interface.

This project was built as part of my Machine Learning learning journey to understand the complete workflow from **data preprocessing and exploratory data analysis to model training, evaluation, serialization, and deployment using Flask**.

---

## 📌 Project Overview

The project uses the **Algerian Forest Fires Dataset** to predict the Fire Weather Index based on different weather and fire-related attributes.

The complete workflow includes:

**Data Collection → Data Cleaning → Exploratory Data Analysis → Feature Engineering → Feature Selection → Model Training → Model Evaluation → Model Serialization → Flask Web Application**

---

## 🎯 Objective

The main objective of this project is to build a regression model capable of predicting the **Fire Weather Index (FWI)** from environmental and weather-related features.

The project also demonstrates how a trained Machine Learning model can be integrated into a Flask web application so that users can enter feature values and receive a prediction.

---

## 📊 Dataset

The project uses the **Algerian Forest Fires Dataset**, containing observations from two regions of Algeria:

* Bejaia Region
* Sidi Bel-abbes Region

After data cleaning and preprocessing, the dataset contains **243 observations**.

### Features Used

The final model uses the following 9 input features:

| Feature     | Description                                              |
| ----------- | -------------------------------------------------------- |
| Temperature | Temperature measurement                                  |
| RH          | Relative Humidity                                        |
| Ws          | Wind Speed                                               |
| Rain        | Rainfall                                                 |
| FFMC        | Fine Fuel Moisture Code                                  |
| DMC         | Duff Moisture Code                                       |
| ISI         | Initial Spread Index                                     |
| Classes     | Fire/Not Fire classification converted to numerical form |
| Region      | Region encoded numerically                               |

### Target Variable

**FWI — Fire Weather Index**

---

## 🔍 Exploratory Data Analysis

During EDA, different aspects of the dataset were analyzed, including:

* Distribution of numerical variables
* Fire and non-fire observations
* Relationships between variables
* Correlation between features
* Relationship between input features and FWI

The project uses:

* Matplotlib
* Seaborn

for data visualization.

---

## 🛠️ Data Preprocessing & Feature Engineering

The following preprocessing steps were performed:

### 1. Data Cleaning

* Removed unnecessary rows and columns
* Handled missing values
* Cleaned column names
* Converted columns to appropriate data types

### 2. Feature Engineering

* Created the `Region` feature
* Converted the categorical `Classes` feature into numerical values
* Removed unnecessary date-related information

### 3. Handling Multicollinearity

A correlation analysis was performed to identify highly correlated features.

Features with a correlation greater than the selected threshold of **0.85** were considered for removal.

As a result:

* `DC`
* `BUI`

were removed from the final feature set.

### 4. Feature Scaling

The independent variables were standardized using **StandardScaler** from Scikit-learn.

The scaler fitted on the training data was saved and reused during prediction.

---

## 🤖 Machine Learning Models

Several regression algorithms were experimented with:

* Linear Regression
* Lasso Regression
* LassoCV
* Ridge Regression
* RidgeCV
* ElasticNet
* ElasticNetCV

### Model Comparison

| Model             |    MAE | R² Score |
| ----------------- | -----: | -------: |
| Linear Regression | 0.5468 |   0.9848 |
| Lasso             | 1.1332 |   0.9492 |
| LassoCV           | 0.6200 |   0.9821 |
| Ridge             | 0.5642 |   0.9843 |
| RidgeCV           | 0.5642 |   0.9843 |
| ElasticNet        | 1.8822 |   0.8753 |
| ElasticNetCV      | 0.6576 |   0.9814 |

The final deployed model is **Ridge Regression**.

### Final Model Performance

**Mean Absolute Error (MAE):** 0.5642

**R² Score:** 0.9843

> These results are based on the project's test split and should not be interpreted as a guarantee of performance on new real-world data.

---

## 🌐 Flask Web Application

The trained Machine Learning model was integrated into a Flask web application.

The application allows a user to enter the required input features through a web form.

The application then:

1. Receives the user's input
2. Converts the input into the required format
3. Applies the saved StandardScaler
4. Loads the trained Ridge Regression model
5. Generates the FWI prediction
6. Displays the prediction on the web page

---

## 📁 Project Structure

```text
linear-regression-flask-app/
│
├── application.py
│
├── models/
│   ├── ridge.pkl
│   └── scaler.pkl
│
├── notebooks/
│   ├── EDA And FE.ipynb
│   └── Model Training.ipynb
│
├── templates/
│   ├── index.html
│   └── home.html
│
├── data/
│   └── cleaned_data.csv
│
├── requirements.txt
├── README.md
└── .gitignore
```

---

## 💻 Technologies Used

### Programming Language

* Python

### Data Analysis

* NumPy
* Pandas

### Data Visualization

* Matplotlib
* Seaborn

### Machine Learning

* Scikit-learn

### Web Development

* Flask
* HTML
* CSS

### Model Serialization

* Pickle

---

## ⚙️ Installation & Setup

### 1. Clone the Repository

```bash
git clone <your-github-repository-url>
```

Navigate into the project directory:

```bash
cd linear-regression-flask-app
```

### 2. Create a Virtual Environment

You can use either `venv` or Conda.

Using `venv`:

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

### 3. Install Dependencies

```bash
pip install -r requirements.txt
```

### 4. Run the Flask Application

```bash
python application.py
```

The application will start on the local Flask server.

Open the URL shown in your terminal, typically:

```text
http://127.0.0.1:5000/
```

---

## 🔮 Making Predictions

Enter the required values for:

```text
Temperature
RH
Ws
Rain
FFMC
DMC
ISI
Classes
Region
```

Submit the form to receive the predicted **Fire Weather Index (FWI)**.

---

## 📚 What I Learned

Through this project, I practiced:

* Data cleaning with Pandas
* Exploratory Data Analysis
* Data visualization
* Feature engineering
* Correlation analysis
* Handling multicollinearity
* Feature scaling
* Train-test splitting
* Regression algorithms
* Model evaluation using MAE and R²
* Ridge, Lasso and ElasticNet regression
* Model serialization using Pickle
* Building a Flask ML application
* Connecting a trained ML model with a web interface

Most importantly, this project helped me understand the transition from:

**"Training a model in a notebook" → "Building an application around that model."**

---

## 🚀 Future Improvements

Some possible improvements for this project include:

* Deploying the application to a cloud platform
* Adding better input validation
* Improving the UI/UX
* Creating a complete preprocessing pipeline
* Adding automated model retraining
* Experimenting with additional regression algorithms
* Adding more comprehensive model monitoring

---

## 👨‍💻 Author

**Harsh Sharma**

B.Tech Computer Science & Engineering

Currently learning and building projects in:

**Python | Data Science | Machine Learning | Flask**

---

## ⭐ Acknowledgements

This project was created as part of my ongoing journey of learning Machine Learning and applying concepts through hands-on projects.

If you found this project useful, feel free to ⭐ the repository.
