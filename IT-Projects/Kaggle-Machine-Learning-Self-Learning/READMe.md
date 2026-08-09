# Kaggle Machine Learning – Self-Learning & Continuous Development

## Overview

As a finance and accounting professional, I have deliberately invested personal time in developing my understanding of data science, machine learning and artificial intelligence.

I used Kaggle competitions and related practical exercises as a hands-on learning environment. The objective was not to become a machine-learning engineer, but to understand how data, models and technology can be used to solve practical problems.

These projects were undertaken **in my free time, alongside my professional responsibilities**, as part of my continuing self-improvement and technology-learning journey.

The notebooks reviewed for this portfolio show practical work in Python, data preparation, feature engineering, regression, classification, NLP, neural networks, computer vision and model evaluation.

---

# My Kaggle Portfolio

I have participated in nine Kaggle competitions/projects.

| # | Competition | Kaggle result/status shown in my workspace | Main area |
|---|---|---:|---|
| 1 | **Russian Car Plates Prices Prediction** | **644 / 694** | Regression & feature engineering |
| 2 | **Backpack Prediction Challenge** | **3,216 / 3,393** | Regression / predictive modelling |
| 3 | **Regression with an Insurance Dataset** | Unranked / 2,350 | Regression |
| 4 | **Binary Prediction of Poisonous Mushrooms** | **2,070 / 2,422** | Binary classification |
| 5 | **Natural Language Processing with Disaster Tweets** | Unranked / 534 | NLP / text classification |
| 6 | **Predict Future Sales** | Unranked / 16,991 | Forecasting |
| 7 | **House Prices – Advanced Regression Techniques** | Unranked / 3,794 | Regression / ensemble models |
| 8 | **Leaf Classification** | Unranked / 15,995 | Classification |
| 9 | **Digit Recognizer** | Unranked / 1,087 | Computer vision / neural networks |

*Leaderboard positions are recorded from my Kaggle workspace when this portfolio was prepared.*

---

# What the Code Shows

I reviewed the Python/Colab notebooks available in my archived material.

The code provides particularly strong evidence of hands-on work for **Russian Car Plates, Backpack Prediction, Insurance, Poisonous Mushrooms, Disaster Tweets, House Prices and Digit Recognizer**.

Some older notebooks appear to have been removed or overwritten due to storage constraints. In particular, I do not currently have sufficient surviving code to reconstruct the **Predict Future Sales** and **Leaf Classification** implementations accurately.

I have therefore deliberately **not invented technologies or algorithms for those two projects**. Their inclusion in the portfolio is based on the Kaggle competition record, while the detailed technical descriptions below are based on the code that remains available.

---

# 1. Russian Car Plates Prices Prediction

## Problem

The project involved predicting the price of Russian vehicle registration plates.

The surviving notebook shows several iterations of the modelling approach, progressing from a relatively simple regression model to more extensive feature engineering and model comparison.

## Data Preparation

The code included:

- Reading training and test data from Google Drive
- Converting dates to datetime
- Exploratory analysis
- Missing-data checks
- Examination of price distribution and skewness
- Correlation analysis

The target variable was `price`.

## Feature Engineering

Several features were created from the available data.

### Date features

- Year
- Month
- Day
- Day of week
- Weekend indicator
- Quarter
- Day of year
- Week of year

### Cyclical features

The code experimented with:

- Month sine/cosine
- Day sine/cosine
- Day-of-week sine/cosine

This is a useful machine-learning technique for representing cyclical variables such as months and weekdays.

### Plate characteristics

The code extracted:

- First character of the plate
- Whether the plate contained numbers
- Plate length
- Encoded plate value

### Aggregate features

The notebook also created price statistics by:

- Plate first character
- Month

including:

- Mean
- Median
- Standard deviation
- Minimum
- Maximum

Interaction features such as `month_day` and `month_dow` were also explored.

## Models Tested

The code tested:

- Linear Regression
- Ridge Regression
- Lasso Regression
- Random Forest
- Gradient Boosting
- Decision Tree
- XGBoost in later iterations

The more advanced notebook also used:

- Cross-validation
- GridSearchCV
- Feature selection using F-scores
- Stacking concepts
- RMSE
- MAE
- R²

## Results Observed in the Notebook

In the initial model comparison:

- Linear Regression: R² approximately **0.004**
- Ridge Regression: R² approximately **0.004**
- Lasso Regression: R² approximately **0.004**
- Random Forest: R² approximately **-0.042**
- Gradient Boosting: R² approximately **0.027**
- Decision Tree: R² approximately **-0.749**

Gradient Boosting was therefore selected in that iteration.

A later feature-engineered iteration improved the validation R² to approximately **0.047**, again selecting Gradient Boosting.

The Kaggle workspace shows a final competition position of **644 / 694**.

## Skills Learned / Reinforced

- Regression modelling
- Feature engineering
- Date/time feature extraction
- Cyclical encoding
- Categorical encoding
- Model comparison
- Cross-validation
- Hyperparameter tuning
- Feature selection
- Understanding RMSE, MAE and R²
- Understanding that sophisticated models do not automatically produce strong predictive results

## Key Learning

This was particularly useful in reinforcing the importance of **feature engineering and data understanding**. The initial model results were weak, and experimentation showed that simply changing algorithms was less important than understanding what information could actually explain the target variable.

---

# 2. Backpack Prediction Challenge

## Problem

The surviving notebook clearly corresponds to a backpack-price prediction dataset.

The objective was to predict `Price` using product characteristics.

## Data Preparation

The code used:

- Pandas
- NumPy
- Google Colab / Google Drive
- Missing-value checks
- Removal of rows with missing values
- Additional training data (`training_extra.csv`)

The use of additional training data was an important part of the modelling process.

## Categorical Data

The following product attributes were encoded:

- Brand
- Material
- Size
- Laptop Compartment
- Waterproof
- Style
- Color

The notebook used `LabelEncoder`.

## Models & Optimisation

The code initially used:

**Random Forest Regressor**

It subsequently used:

**GridSearchCV**

with parameters including:

- Number of estimators
- Maximum depth
- Minimum samples split
- Minimum samples leaf

The final model was trained using the combined original and additional training data.

The notebook also used:

- StandardScaler
- RMSE
- Train/test split
- Kaggle submission generation

## Skills Learned / Reinforced

- Regression
- Handling categorical variables
- Label encoding
- Using additional training data
- Random Forest
- Hyperparameter tuning
- GridSearchCV
- RMSE
- Model optimisation
- Kaggle submission workflow

## Important Learning

The project reinforced the practical value of **data quantity and model tuning**. I experimented with combining additional training data with the original dataset rather than treating the first model as the final solution.

The Kaggle workspace records a position of **3,216 / 3,393**.

---

# 3. Regression with an Insurance Dataset

## Problem

The objective was to predict the `Premium Amount` for insurance customers.

This provided a practical regression problem with a mixture of demographic, health, lifestyle and policy-related variables.

## Data Preparation

The code included:

- Reading training and test datasets
- Missing-data analysis
- Removal of rows with missing values
- Removal of `Policy Start Date`
- Conversion of `Health Score`
- Descriptive statistics

## Feature Transformation

Several categorical variables were converted into numerical representations.

Examples included:

- Location
- Policy Type
- Customer Feedback
- Smoking Status
- Exercise Frequency
- Property Type

The code also replaced missing values in:

- Previous Claims
- Vehicle Age

## Models

The notebook used:

- Gradient Boosting Regressor
- Linear Regression
- Random Forest Regressor
- Gradient Boosting Regressor

The final surviving implementation used:

**GradientBoostingRegressor**

with one-hot encoding through `pd.get_dummies()`.

## Skills Learned / Reinforced

- Regression
- Data cleaning
- Missing-value handling
- Categorical encoding
- Feature preparation
- Gradient boosting
- Prediction generation
- Submission-file preparation

## Key Learning

This project reinforced the importance of **data preprocessing before model selection**. It also provided practical experience translating business-style variables into machine-learning inputs.

---

# 4. Binary Prediction of Poisonous Mushrooms

## Problem

The objective was to classify mushrooms as:

- Edible
- Poisonous

The target variable was converted from `e/p` into binary values.

## Data Preparation

The notebook included:

- Missing-value analysis
- Numerical and categorical variable identification
- Numerical imputation using mean values
- Categorical imputation using most-frequent values
- Memory optimisation
- Separation of ID, target and predictors

## Feature Engineering / Encoding

The categorical variables were transformed using:

**OneHotEncoder**

Numerical features were processed using:

**StandardScaler**

The notebook also experimented with feature selection.

## Models Tested

The surviving code shows experiments with:

- SGDClassifier
- Logistic Regression
- Gradient Boosting Classifier

It also explored:

- `SelectFromModel`
- Pipelines
- Classification reports
- Confusion matrices
- Accuracy
- Precision
- Recall
- F1 score

## Validation Results

The surviving notebook records validation accuracy of approximately:

- SGD/log-loss approach: **84%**
- Logistic Regression: **83%**
- Feature-selection SGD approach: **84%**
- Gradient Boosting: **90%**

The 90% validation accuracy was the strongest recorded result in the notebook.

The Kaggle workspace records a position of **2,070 / 2,422**.

## Skills Learned / Reinforced

- Binary classification
- One-hot encoding
- Numerical standardisation
- Imputation
- Feature selection
- Logistic regression
- SGD
- Gradient boosting
- Classification metrics
- Confusion-matrix interpretation

## Key Learning

This project reinforced that model performance can change substantially depending on **preprocessing, feature representation and algorithm selection**.

---

# 5. Natural Language Processing with Disaster Tweets

## Problem

The objective was to classify tweets and determine whether they referred to real disasters.

This was the first major NLP problem visible in the surviving Kaggle code.

## Exploratory Analysis

The notebook explored:

- Number of positive and negative examples
- Tweet length
- Word counts
- Hashtags
- Word distributions
- Differences between disaster and non-disaster tweets

This demonstrated an important NLP principle:

**Before modelling, understand the language contained in the data.**

## Baseline Models

The notebook initially established baseline approaches including:

- Majority-class model
- TF-IDF + Logistic Regression

The TF-IDF pipeline used:

- `TfidfVectorizer`
- Logistic Regression

The notebook also experimented with:

- CountVectorizer
- TF-IDF Transformer
- Gradient Boosting

## Recurrent Neural Network

The code then moved into neural-network approaches.

An LSTM architecture was developed using:

- Keras
- Tokenizer
- Sequence padding
- Embedding layer
- LSTM
- Dense layers
- Dropout
- Sigmoid output

## BERT

The project progressed further into transformer-based NLP.

The code used:

- BERT Tokenizer
- TensorFlow Hub
- `bert-base-uncased`
- BERT embeddings
- Fine-tuning
- Binary classification

## Hybrid Deep Learning

The notebook also experimented with combining BERT representations with:

- Conv1D
- MaxPooling1D
- Bidirectional LSTM

This is a particularly strong example of hands-on experimentation beyond basic machine learning.

## XLM-RoBERTa

The final surviving code also experimented with:

**XLM-RoBERTa**

using the `simpletransformers` library.

Training parameters included:

- Batch size
- Epochs
- Early stopping
- Maximum sequence length
- Gradient accumulation

## Skills Learned / Reinforced

- NLP
- Text preprocessing
- TF-IDF
- Text vectorisation
- Logistic Regression
- LSTM
- Bidirectional LSTM
- BERT
- Transformer models
- XLM-RoBERTa
- Transfer learning
- Neural-network training
- Early stopping
- Model experimentation

## Why This Project Matters

This project is particularly important in the context of my broader AI journey.

It provided a bridge from traditional structured-data machine learning into **unstructured text and NLP**.

That experience subsequently complemented my AI legal-language project.

---

# 6. Predict Future Sales

## Competition

The Kaggle workspace shows participation in:

**Predict Future Sales**

with a displayed status of **Unranked / 16,991**.

## Available Evidence

The original implementation code is not present in the archived material supplied with this portfolio.

I therefore have not reconstructed or claimed specific models or libraries for this competition.

## Learning Area

The competition is retained in the portfolio because it represents exposure to:

- Sales forecasting
- Time-dependent data
- Predictive analytics
- Business forecasting

## Status

**Technical implementation: archived code not currently available.**

If the original notebook is recovered later, the case study can be expanded with the actual modelling approach and results.

---

# 7. House Prices – Advanced Regression Techniques

## Problem

The objective was to predict residential property sale prices.

This project provided one of the most comprehensive surviving examples of my structured-data machine-learning work.

## Data

The notebook worked with:

- 1,460 training observations
- 81 columns
- Numerical and categorical variables
- Significant missing data

## Data Preparation

The code included:

- Exploratory Data Analysis
- Missing-value analysis
- Numerical imputation
- Categorical imputation
- One-hot encoding
- Standardisation
- Feature/target separation

## Machine Learning Approaches

The notebooks experimented with:

- Random Forest
- XGBoost
- TensorFlow Decision Forests
- Gradient Boosted Trees
- CART
- Distributed Gradient Boosted Trees
- Ridge/Lasso in a separate modelling exercise

## Hyperparameter Tuning

The Scikit-learn implementation used:

**GridSearchCV**

with five-fold cross-validation.

The Random Forest implementation tuned:

- Number of estimators
- Maximum depth
- Minimum samples split
- Minimum samples leaf

The XGBoost implementation tuned:

- Number of estimators
- Maximum depth
- Learning rate
- Subsample

## TensorFlow Decision Forests

Another notebook used:

**TensorFlow Decision Forests**

and compared tree-based models.

A recorded evaluation of a Random Forest model showed an RMSE of approximately **31,482** on a 1,042-example evaluation dataset.

The model's variable importance output highlighted:

- OverallQual
- GarageCars
- GrLivArea
- ExterQual
- 1stFlrSF
- FullBath
- GarageArea

among the more influential variables.

## Skills Learned / Reinforced

- High-dimensional data handling
- Missing-value treatment
- Categorical encoding
- Pipelines
- ColumnTransformer
- Random Forest
- XGBoost
- TensorFlow Decision Forests
- Cross-validation
- GridSearchCV
- Feature importance
- RMSE
- R²
- Ensemble modelling

## Professional Relevance

This was particularly relevant to my professional exposure to real estate and property-related business processes.

It demonstrated how a traditional business problem can be translated into a predictive analytics problem.

---

# 8. Leaf Classification

## Competition

The Kaggle workspace shows participation in:

**Leaf Classification**

with a displayed status of **Unranked / 15,995**.

## Available Evidence

I could not identify a surviving notebook in the supplied archive that can be reliably attributed to this specific competition.

There are several additional notebooks in the archive, but they either correspond to other datasets or cannot be confidently mapped to the Leaf Classification competition.

I have therefore deliberately avoided claiming specific models or technologies for this project.

## Learning Area

The competition is retained as evidence of exploration of:

- Classification
- Pattern recognition
- Feature-based prediction

## Status

**Technical implementation: archived code not currently available.**

---

# 9. Digit Recognizer

## Problem

The project involved recognising handwritten digits from image data.

The surviving notebook provides strong evidence of hands-on neural-network and computer-vision experimentation.

## Data Preparation

The code:

- Loaded the image dataset
- Separated pixel values from labels
- Reshaped images into 28 × 28 format
- Reshaped them for convolutional neural networks
- Standardised pixel values
- Converted labels into categorical format

## Models Tested

The notebook explicitly compares:

### Linear model

A simple baseline neural model was established.

Recorded training accuracy:

**86.87%**

### Fully Connected Neural Network

A 512-node dense layer was introduced.

Recorded training accuracy:

**90.69%**

### Convolutional Neural Network

The CNN used:

- Convolution layers
- ReLU activation
- Max pooling
- Flattening
- Dense layers

Recorded training accuracy:

**93.93%**

### CNN + Data Augmentation

Image augmentation included:

- Rotation
- Width shifting
- Shearing
- Height shifting
- Zooming

Recorded training accuracy:

**96.06%**

### Batch / Further optimisation

A later experiment recorded:

**98.30% accuracy**

## Technology

- Python
- Pandas
- NumPy
- Keras
- TensorFlow
- CNN
- Dense neural networks
- ImageDataGenerator
- Data augmentation
- Batch processing
- Confusion matrix

## Skills Learned / Reinforced

- Image preprocessing
- Neural networks
- CNN architecture
- Model comparison
- Data augmentation
- Validation
- Confusion-matrix analysis
- Hyperparameter experimentation
- Understanding overfitting and generalisation

## Key Learning

This project demonstrated the value of matching the model architecture to the data.

Moving from a simple dense model to a CNN substantially improved performance, while data augmentation further improved the recorded result.

---

# Technology Stack Across the Portfolio

The surviving code demonstrates practical exposure to:

## Programming

- Python
- Jupyter / Google Colab
- Pandas
- NumPy

## Classical Machine Learning

- Scikit-learn
- Linear Regression
- Ridge
- Lasso
- Random Forest
- Gradient Boosting
- Decision Trees
- SGD
- Logistic Regression
- XGBoost
- Support Vector Machines

## Deep Learning

- TensorFlow
- Keras
- CNN
- LSTM
- Bidirectional LSTM
- Dense neural networks
- Batch Normalisation

## NLP / Transformers

- TF-IDF
- BERT
- BERT Tokenizer
- TensorFlow Hub
- XLM-RoBERTa
- Simple Transformers

## Data Processing

- One-hot encoding
- Label encoding
- Standardisation
- Imputation
- Feature selection
- Feature engineering
- Data augmentation

## Model Development & Evaluation

- Train/test split
- Cross-validation
- GridSearchCV
- Hyperparameter tuning
- Accuracy
- Precision
- Recall
- F1
- RMSE
- MSE
- MAE
- R²
- Confusion matrices
- Feature importance

---

# Skills Developed or Reinforced

## 1. Data Literacy

Learning to inspect data before immediately modelling it.

## 2. Feature Engineering

Understanding that raw data often needs to be transformed into meaningful predictive variables.

## 3. Model Selection

Learning that different problems require different modelling approaches.

## 4. Model Evaluation

Understanding that a model should be assessed using appropriate validation methods and metrics rather than simply accepting the first result.

## 5. Experimentation

Testing alternative models and architectures rather than assuming the first approach is sufficient.

## 6. NLP

Moving from structured data into text-based machine learning and transformer models.

## 7. Deep Learning

Developing practical familiarity with CNNs, LSTMs and transformer-based models.

## 8. Technology Troubleshooting

Working with Google Colab, package installation, memory limitations, training time and model compatibility.

## 9. Critical Thinking

Learning to question results rather than simply accepting a high score.

For example, some of the surviving notebooks contain warnings, incomplete experiments or results that require careful interpretation. That is itself part of the learning experience.

---

# What I Learned About AI/ML

The most important lesson from these projects is that machine learning is **not simply about selecting an algorithm**.

Good results depend on:

**Problem definition → Data quality → Feature engineering → Model selection → Validation → Evaluation → Interpretation**

A sophisticated model cannot compensate for poor data or poor problem definition.

This is closely aligned with my professional experience in audit, analytics and risk management.

---

# A Particularly Valuable Learning Progression

My work progressed across increasingly complex forms of data:

**Structured business data**

↓

**Regression and classification**

↓

**Time-series / forecasting**

↓

**Text classification**

↓

**Deep learning**

↓

**BERT / Transformers**

↓

**Applied AI / NLP**

This progression eventually complemented my separate AI-powered legal-language project.

---

# Why I Did This in My Free Time

These projects were undertaken **outside my professional working responsibilities and in my own time**.

My core professional background is in:

- Chartered Accountancy
- Internal Audit
- Risk Management
- Governance
- Financial Analysis
- Fraud Analytics
- Business Process Improvement

AI and machine learning were not my original academic discipline.

I therefore deliberately invested personal time to understand these technologies by actually writing code, preparing data, testing models and analysing results.

---

# My Perspective

I do not present this portfolio as evidence that I am a professional machine-learning engineer.

I present it as evidence of:

**Curiosity + Initiative + Practical Learning + Technology Adaptability**

My objective is to become a stronger business professional who understands technology well enough to:

- Identify opportunities for AI and analytics
- Ask better questions
- Challenge assumptions
- Understand model limitations
- Translate business problems into analytical problems
- Work effectively with technical specialists
- Assess technology from a business and risk perspective

---

# From Self-Learning to Applied AI

The Kaggle work provided a foundation for my later AI/NLP project involving the paraphrasing of Indian laws and case judgments.

That project moved from individual machine-learning experiments into a more complete AI solution involving:

**Data → NLP Models → Model Evaluation → Semantic Search → Application → User Interaction**

The progression represents my broader technology journey:

> **Learn → Experiment → Understand → Apply**

---

# Personal Learning Philosophy

I believe continuous professional development should extend beyond formal qualifications and mandatory training.

For me, the value of these projects is not primarily the leaderboard ranking.

It is the fact that I was willing to spend my own time working through unfamiliar datasets, unfamiliar technologies, unsuccessful experiments and iterative improvements.

That process has helped me become more comfortable at the intersection of:

**Business / Finance ↔ Data ↔ Technology ↔ AI**

---

# Summary

### 9
Kaggle competitions / projects

### 5+
Major areas explored

**Regression · Classification · NLP · Forecasting · Computer Vision**

### Core technology

**Python + Data Analytics + Machine Learning**

### Learning approach

**Self-directed · Hands-on · Outside professional work · Continuous development**

### Overall objective

> **To become a better business professional who understands technology, rather than a technology professional who understands only technology.**

---

## Evidence & Scope Note

This case study has been prepared from the Kaggle competition record and the surviving Google Colab/Jupyter notebooks available in my archived files.

Some older notebooks were apparently removed or overwritten due to storage constraints. Where the original implementation could not be confidently identified, I have intentionally avoided attributing specific technologies or algorithms to the competition.

The portfolio therefore distinguishes between:

- **Kaggle participation confirmed by my workspace**
- **Technical implementation confirmed by surviving code**
- **Results actually recorded in the notebooks**

This is intended to keep the portfolio accurate and transparent.
