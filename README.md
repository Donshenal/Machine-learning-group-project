# Machine Learning Project -- Turtle rescue forecast

This repository contains the results of a machine learning group project, which was done during a data science course at Spiced Academy.

The data used for this was from Zindi:
 [turtle rescue forecast](https://zindi.africa/competitions/turtle-rescue-forecast-challenge)  

The deliverables are:
* [slides](turtle_stakeholder_slides.pdf) for a stakeholder presentation
* [jupyter notebooks](notebooks/)
* scripts for generating and running model from the terminal -- see files final_script.sh and src/predict.py

This project was done by:

[DonShenal](https://github.com/Donshenal)

[papayakaja](https://github.com/papayakaja)

[larixlarix](https://github.com/larixlarix)

[RiptideDS](https://github.com/RiptideDS)

---

## The project's Kanban board on github

[Kanban board](https://github.com/users/RiptideDS/projects/1) of this 

## Requirements and Environment

Requirements:
- pyenv with Python: 3.11.3

Environment: 
For installing the virtual environment you can either use the Makefile and run `make setup` or install it manually with the following commands: 

```Bash
pyenv local 3.11.3
python -m venv .venv
source .venv/bin/activate
pip install --upgrade pip
pip install -r requirements.txt
```

Data: 
Please download the .csv files containing the data as provided by Zindi, unzip them and put them into a 'data' subfolder. 


## Usage

We wrote a script, which will:

* load and clean the raw data
* perform some data wrangling and basic feature engineering 
* train the model and make predictions
* test and evaluate the predictions
* perform error analysis,

In order to use the script please run:

```bash
source final_script.sh
```

As the training of the CatBoost model includes a grid search for hyperparameter optimization, this will take a little while (expect 15-20 mins).



In order to perform prediction on a test set you created (consisting of csv files for X_test and y_test), run from a shell:

```bash
python3 src/predict.py models/linear_regression_model.sav data/X_test.csv data/y_test.csv
``` 
for the linear baseline model, or

```bash
python3 src/predict.py models/cat_boost_model.sav data/X_test.csv data/y_test.csv
```
for the catboost model. You may replace ```data/X_test.csv data/y_test.csv``` with the paths to your own test data sets.

Cheers from Team Turtle!

![](https://vignette.wikia.nocookie.net/great-characters/images/b/bb/TMNT.jpeg/revision/latest?cb=20200716144943)


