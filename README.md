# Employment-Salary-Prediction-ShreyashKumar

Employee Salary Classification App

This project is a web application built with Streamlit that uses a pre-trained machine learning model to predict whether an employee's salary is likely to be above or below $50,000. It provides both a user-friendly interface for single-employee predictions and a feature for making batch predictions from a CSV file.

🌟 Features
 * Single Prediction: Use the interactive sidebar to input an employee's details (age, education, occupation, hours per week, experience) and get an instant salary prediction.
 * Batch Prediction: Upload a CSV file containing employee data to get predictions for multiple employees at once.
 * Prediction Download: Download the batch prediction results as a new CSV file, with the predicted salary class added as a new column.
 * Professional UI: A clean and intuitive user interface built with the Streamlit library.

🚀 Getting Started
Prerequisites
To run this application, you need to have Python installed on your system. The required libraries are listed in requirements.txt.
Installation
 * Clone or download this repository: If this project is in a Git repository, clone it using:
   git clone <repository_url>
cd <repository_name>

   Alternatively, you can download the project files as a ZIP archive.
 * Set up the environment: Navigate to the project directory and install the necessary Python libraries using pip.
   pip install -r requirements.txt

Project Structure
Make sure your project directory has the following structure:
.
├── app.py              # The main Streamlit application code
├── best_model.pkl      # The pre-trained machine learning model
└── requirements.txt    # List of required Python libraries

Note: The best_model.pkl file must be present in the same directory as app.py.
Usage
 * Run the application: From your terminal, execute the following command in the project directory:
   streamlit run app.py

 * Access the app: Your default web browser will automatically open a new tab with the application running at http://localhost:8501.
 * Make a prediction:
   * Single Prediction: Use the sliders and dropdowns in the sidebar to input an employee's details, then click the "Predict Salary" button.
   * Batch Prediction: Scroll down to the "Batch Prediction" section, click "Choose a CSV file," and upload your data. The predictions will be displayed and a download button will appear.
🛠 Troubleshooting
ValueError: The feature names should match those that were passed during fit.
This is a common error that occurs when the columns in your input data do not match the columns the model was trained on.
Cause: Your machine learning model was trained on a dataset with a specific number of columns (e.g., after one-hot encoding categorical variables and including all original features like capital-gain). Your app.py must apply the same transformations to the user's input before making a prediction.
Solution: The provided app.py code already includes the fix for this issue. It manually creates a DataFrame with all the expected feature columns and applies a simple form of one-hot encoding to ensure the input data format is correct.
If you encounter this error on batch prediction, ensure that your CSV file contains all the columns that your model expects, with the same names and data types.
