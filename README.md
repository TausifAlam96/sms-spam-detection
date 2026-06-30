# sms-spam-detection

Here is a complete guide to building your Flask application with user authentication and an SMS spam detection model.

We will break this project into three parts:
- Training the Model: A script to parse your spam.csv file, train a machine learning model, and save it.
- The Flask Backend: The app.py file that handles routing, database connections for authentication, and running predictions.
- The Frontend Templates: The HTML files for login, registration, and user input.

## 1. Project Setup and Prerequisites
First, organize your project directory like this:

>`` flask_spam_app/  
>│  
>├── spam.csv                 # Your training dataset  
>├── train_model.py           # Script to train and save the model  
>├── app.py                   # Main Flask application  
>└── templates/               # Folder for HTML files  
>```   ├── layout.html  
>   ├── login.html  
>   ├── register.html  
>   └── index.html  

Install the required Python libraries via your terminal:

> pip install Flask Flask-SQLAlchemy Flask-Login pandas scikit-learn werkzeug

## 2. Training the Model (train_model.py)
This script reads your .csv data, trains a Naive Bayes classifier, and saves both the model and the vectorizer (which converts text to numbers) into .pkl files so your Flask app can use them.

Assumes your spam.csv has two columns: v1 (labels like "ham" or "spam") and v2 (the message text).

>Run this script once using python train_model.py. It will generate model.pkl and vectorizer.pkl in your project folder.

## 3. The Flask Application (app.py)
>This file sets up a local SQLite database for users, manages user sessions via Flask-Login, and handles the POST request to predict spam.

## Next Steps
- Run python app.py in your terminal.
- Open your browser and navigate to [http://127.0.0.1:5000/](http://127.0.0.1:5000/).
- Register a new user, log in, and test some text messages!
