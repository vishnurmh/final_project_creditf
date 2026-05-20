Credit Card Fraud Detection in Transactions

This project is a machine learning-based web application that predicts whether a credit card transaction is legitimate or fraudulent. The main objective of this project is to detect suspicious transactions in real time using historical transaction data and advanced machine learning models.

I developed this project as part of my AI & ML internship project work to gain practical experience in anomaly detection, classification, model evaluation, and deployment.

The application uses the Kaggle Credit Card Fraud Detection dataset, which contains thousands of real transaction records. Each transaction is labeled as either normal or fraudulent. One of the major challenges in this dataset is class imbalance, because fraudulent transactions are very rare compared to legitimate ones.

To address this issue, I performed data preprocessing and balancing techniques before training the models. The preprocessing steps included checking for missing values, scaling important features such as Time and Amount, splitting the data into training and testing sets, and applying SMOTE to balance the classes.

I experimented with multiple machine learning algorithms, including Isolation Forest, Local Outlier Factor, and XGBoost. Isolation Forest and Local Outlier Factor were used for anomaly detection, while XGBoost was used as the primary supervised classification model.

After comparing the performance of all models, XGBoost produced the best results. The model was evaluated using several metrics such as confusion matrix, precision, recall, F1-score, and ROC-AUC score. These metrics helped measure how effectively the model identifies fraudulent transactions while minimizing false alarms.

The trained model and scaler were saved using joblib so they could be reused in the web application without retraining.

The frontend of the application was built using React and Vite, and the backend was developed using FastAPI. The frontend provides a modern dashboard where users can enter transaction details such as Time, Amount, and the PCA-transformed features (V1 to V28). The backend loads the saved model and returns a prediction along with a confidence score.

When a user submits transaction details, the application processes the input, applies the same preprocessing steps used during training, and predicts whether the transaction is fraudulent or legitimate. The result is displayed with a risk score and probability percentage.

Project Structure

fraud-detection-project/

* backend/

  * main.py
  * requirements.txt
  * models/

    * xgboost_fraud_model.pkl
    * scaler.pkl
* frontend/

  * src/
  * public/
  * package.json
  * vite.config.js
* notebooks/

  * fraud_detection.ipynb
* data/

  * creditcard.csv
* screenshots/
* README.md

Technologies Used

* Python
* Pandas
* NumPy
* Scikit-learn
* XGBoost
* Imbalanced-learn (SMOTE)
* FastAPI
* React
* Vite
* Tailwind CSS
* Joblib
* Matplotlib
* Seaborn

Machine Learning Workflow

1. Loaded and explored the credit card transaction dataset.
2. Checked for missing values and class distribution.
3. Scaled Time and Amount features.
4. Split the data into training and testing sets.
5. Applied SMOTE to handle class imbalance.
6. Trained Isolation Forest and Local Outlier Factor models.
7. Trained an XGBoost classifier.
8. Evaluated models using confusion matrix, precision, recall, F1-score, and ROC-AUC.
9. Saved the best-performing model and scaler.
10. Built a React and FastAPI web application for real-time predictions.

Features of the Web Application

* Modern fintech-style dashboard
* Real-time fraud prediction
* Confidence score display
* Risk level indicator
* Responsive design
* API-based architecture

Results

The XGBoost model achieved strong performance and was able to accurately identify fraudulent transactions with a high ROC-AUC score. The model provided reliable predictions while maintaining a good balance between precision and recall.

What I Learned

Through this project, I gained hands-on experience in:

* Handling highly imbalanced datasets
* Anomaly detection techniques
* Supervised classification using XGBoost
* Model evaluation and interpretation
* Saving and loading trained models
* Building REST APIs with FastAPI
* Creating modern frontend applications using React and Vite
* Integrating machine learning models into real-world web applications

How to Run the Project

Backend

```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

Frontend

```bash
cd frontend
npm install
npm run dev
```

After starting both servers, open the frontend URL shown in the terminal, usually:

```text
http://localhost:5173
```

Future Improvements

* Batch prediction using CSV upload
* Authentication and user management
* Prediction history storage
* Cloud deployment
* Explainable AI using SHAP values

Conclusion

This project demonstrates how machine learning can be applied to real-world financial fraud detection problems. By combining XGBoost with a modern React and FastAPI application, I created a complete end-to-end solution capable of detecting suspicious transactions in real time.
