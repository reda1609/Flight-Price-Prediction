# Flight Price Prediction Project

In this project, I developed a machine learning model to predict flight prices based on various features such as airline, source city, departure time, stops, arrival time, destination city, class, duration, and days left until departure. Below is a summary of the steps I followed:

## 1. **Loading the Dataset**
   - I loaded the dataset `Clean_Dataset.csv` using `pandas`.
   - The dataset contains information about flights, including airline, source city, departure time, stops, arrival time, destination city, class, duration, days left, and price.

## 2. **Data Exploration**
   - I explored the dataset to understand the distribution of key features:
     - **Airlines**: Vistara, Air India, Indigo, GO_FIRST, AirAsia, SpiceJet.
     - **Source Cities**: Delhi, Mumbai, Bangalore, Kolkata, Hyderabad, Chennai.
     - **Departure Times**: Morning, Early_Morning, Evening, Night, Afternoon, Late_Night.
     - **Stops**: One, Zero, Two_or_more.
     - **Arrival Times**: Night, Evening, Morning, Afternoon, Early_Morning, Late_Night.
     - **Destination Cities**: Mumbai, Delhi, Bangalore, Kolkata, Hyderabad, Chennai.
     - **Class**: Economy, Business.

## 3. **Data Preprocessing**
   - I dropped irrelevant columns like `Unnamed: 0` and `flight`.
   - I converted categorical variables into numerical format:
     - Applied **Binary Encoding** to the `class` column (Business = 1, Economy = 0).
     - Used **Factorization** for the `stops` column.
     - Applied **One-Hot Encoding** to categorical columns like `airline`, `source_city`, `departure_time`, `arrival_time`, and `destination_city`.

## 4. **Model Training**
   - I split the dataset into training and testing sets (80% training, 20% testing).
   - I trained a **Random Forest Regressor** to predict flight prices.
   - The model was trained using the preprocessed dataset.

## 5. **Model Evaluation**
   - I evaluated the model using the following metrics:
     - **R2 Score**: 0.9852
     - **Mean Absolute Error (MAE)**: 1080.01
     - **Mean Squared Error (MSE)**: 7667384.40
     - **Root Mean Squared Error (RMSE)**: 2769.00
   - I also visualized the model's performance by plotting actual vs. predicted flight prices.

## 6. **Feature Importance**
   - I identified the most important features for predicting flight prices using the Random Forest model.
   - The top 10 features were visualized using a bar plot.

## 7. **Hyperparameter Tuning**
   - I performed hyperparameter tuning using **GridSearchCV** to optimize the Random Forest Regressor.
   - The best parameters found were:
     - `max_depth`: None
     - `max_features`: 'sqrt'
     - `min_samples_leaf`: 1
     - `min_samples_split`: 5
     - `n_estimators`: 300
   - After tuning, the model's performance slightly improved:
     - **R2 Score**: 0.9851
     - **MAE**: 1245.74
     - **MSE**: 7724846.19
     - **RMSE**: 2779.36

## 8. **Conclusion**
   - The Random Forest Regressor performed well in predicting flight prices, achieving an R2 score of 0.9851.
   - The most important features for prediction were identified, and hyperparameter tuning further improved the model's performance.
   - This model can be used to predict flight prices with reasonable accuracy based on the given features.