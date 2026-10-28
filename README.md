# Flight Ticket Price Prediction using Regression Techniques

## Overview
This project builds and evaluates regression models to predict domestic airfares in India based on historical booking data [cite: 1]. Airfares vary significantly depending on the airline, route, number of stops, travel class, and how many days before departure the ticket is booked [cite: 1].

## Dataset Details
- **Source:** Kaggle (Flight Price Prediction dataset) [cite: 1]
- **Target Variable:** `Price` (Continuous - ticket fare in INR) [cite: 1]
- **Key Features:** Airline, Source City, Destination City, Stops, Class, Duration, Days Left [cite: 1].

## Tasks Performed
1. **Data Preparation:** 
   - Loaded and inspected dataset shape, data types, and missing values [cite: 1].
   - Handled missing values and duplicate records [cite: 1].
   - Detected and treated outliers in `Price` and `Duration` using the Interquartile Range (IQR) method [cite: 1].
   - Applied Ordinal Encoding on `Stops` and One-Hot Encoding on categorical features (`airline`, `source_city`, `destination_city`, `class`) [cite: 1].
   - Applied `StandardScaler` on continuous features (`duration`, `days_left`) [cite: 1].
   - Split the data into 80% training and 20% testing sets [cite: 1].

2. **Model Building:**
   - **Simple Linear Regression:** Built using the most correlated feature (`class_Economy`) [cite: 1].
   - **Multiple Linear Regression:** Built using all relevant features [cite: 1].
   - **Polynomial Regression:** Built with degree = 2 on `duration` and `days_left` [cite: 1].

3. **Model Evaluation & Comparison:**
   - Evaluated models using MAE, MSE, RMSE, and $R^2$ Score on test data [cite: 1].
   - Generated Actual vs Predicted fare plots and Residual distribution plots [cite: 1].

### Model Performance Summary
| Model | MAE | RMSE | R² Score | Rank |
| :--- | :--- | :--- | :--- | :--- |
| **Multiple Linear Regression** | 4486.85 | 6789.28 | 0.9105 | 1 |
| **Simple Linear Regression** | 4873.19 | 7844.49 | 0.8805 | 2 |
| **Polynomial Regression** | 18749.38 | 21690.00 | 0.0865 | 3 |

## Findings & Conclusions
- **Multiple Linear Regression** emerged as the best-performing model with an $R^2$ score of approximately **0.9105** [cite: 1].
- **Travel Class & Days Left:** Class (Economy vs. Business) and the number of days left before departure are among the strongest pricing factors, reflecting standard airline surge and tier-based pricing structures [cite: 1].
