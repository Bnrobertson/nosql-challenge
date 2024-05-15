# Eat, Safe, Love

# Introduction

Welcome to the Eat Safe, Love project! This project aims to set up and analyze a food establishment database using MongoDB and Python. 
The data includes various food establishments, their hygiene scores, and other relevant information. This README will guide you through
the setup process, including importing data, updating the database, and performing exploratory analysis.

# Table of Contents

- Project Setup
- Database Update
- Exploratory Analysis
- Dependencies
- Usage
# Project Setup

# Import the Data
1. First, import the data provided in the establishments.json file into MongoDB. Use the following command in your terminal:
mongoimport --type json -d uk_food -c establishments --drop --jsonArray establishments.json

# Database and Jupyter Notebook Setup
1. Import necessary dependencies:
from pymongo import MongoClient
from pprint import pprint
2. Create an instance of MongoClient and connect to the database:
mongo = MongoClient(port=27017)
print(mongo.list_database_names())  # Verify connection
3. Assign the uk_food database to a variable and review the collections:
establishments = db['establishments']
pprint(db.establishments.find_one())  # Review a document
4. Assign the establishments collection to a variable:
establishments = db['establishments']
pprint(db.establishments.find_one())  # Review a document

# Database Update

### Add a New Restaurant
Add the following restaurant "Penang Flavours" to the database.
### Update Restaurant BusinessTypeID
Find and update the BusinessTypeID for "Penang Flavours".
### Delete Documents with Specific Local Authority
Delete all documents where LocalAuthorityName is "Dover".
### Data Type Conversion
Convert latitude and longitude to decimal numbers.
Set non 1-5 Rating Values to Null and convert RatingValue to Integer.

# Exploratory Analysis

### Setup
1. Import necessary dependencies:
from pymongo import MongoClient
import pandas as pd
from pprint import pprint
2. Connect to the database:
mongo = MongoClient(port=27017)
db = mongo['uk_food']
establishments = db['establishments']

# Analysis Questions
1. Establishments with a hygiene score equal to 20.
2. Establishments in London with a RatingValue >= 4.
3. Top 5 establishments near "Penang Flavours" with a RatingValue of 5.
4. Establishments with a hygiene score of 0, grouped by Local Authority.

# Dependencies

- Python 3.x
- MongoDB
- pymongo library
- pandas library
Install the necessary dependencies using:
pip install pymongo pandas

# Usage

1. Clone the repository:
git clone https://github.com/Bnrobertson/nosql-challenge.git
cd nosql-challenge
2. Follow the steps in the Project Setup section to set up the database and import the data.
3. Run the analysis scripts in a Jupyter Notebook or your preferred Python environment.
