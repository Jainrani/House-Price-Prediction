# 🏠 House Price Prediction

## Project Overview
This project predicts house prices based on features such as area, bedrooms, bathrooms, stories, and parking.  
Models used include **Linear Regression**, **Polynomial Regression**, and **Random Forest Regressor**.  

**Objective:**  
- Accurately predict house prices  
- Understand feature importance  
- Compare linear and non-linear models

---

## Dataset Description

| Feature | Description |
|---------|-------------|
| area | House area in sq. ft |
| bedrooms | Number of bedrooms |
| bathrooms | Number of bathrooms |
| stories | Number of stories/floors |
| parking | Number of parking slots |
| price | Target variable: House price in ₹ |

**Rows:** 40 (example dataset, manually created in Excel)

---

## Exploratory Data Analysis (EDA)

**Scatter Plots:**  
- Area vs Price  
- Bedrooms vs Price  

**Correlation Heatmap:**  
- Shows how features correlate with price  

![Area vs Price](area_vs_price.png)  
![Bedrooms vs Price](screenshots/bedrooms_vs_price.png)  
![Correlation Heatmap](screenshots/correlation_heatmap.png)

---

## Models Implemented

1. Linear Regression

from sklearn.linear_model import LinearRegression
lr_model = LinearRegression()
lr_model.fit(X_train, y_train)
y_pred_lr = lr_model.predict(X_test)

2. Random Forest

from sklearn.ensemble import RandomForestRegressor
rf_model = RandomForestRegressor(n_estimators=100, random_state=42)
rf_model.fit(X_train, y_train)
y_pred_rf = rf_model.predict(X_test)

3. Polynomial Regression (Degree 2)

from sklearn.preprocessing import PolynomialFeatures
poly = PolynomialFeatures(degree=2, include_bias=False)
X_poly = poly.fit_transform(X_scaled)
poly_model = LinearRegression()
poly_model.fit(X_train_poly, y_train_poly)
y_pred_poly = poly_model.predict(X_test_poly)


##Feature Importance

Linear Regression Coefficients:

Area → Most important

Bedrooms & Bathrooms → Moderate impact

Stories & Parking → Smaller impact

Random Forest Feature Importance:

Area → Highest importance

Shows non-linear contribution automatically

Polynomial Regression Coefficients (Approximate):

Captures non-linear trends between features and price



##Prediction Comparison

Actual vs Predicted Prices (All Models)

Observation:

Random Forest predictions align closest to actual prices → best model

Polynomial Regression improves Linear Regression slightly

Linear Regression serves as a baseline


##Key Takeaways

Random Forest Regressor = most accurate, handles non-linear relationships

Polynomial Regression = captures non-linear trends

Linear Regression = baseline, highly interpretable

Area is the strongest predictor

EDA and feature importance are crucial for understanding data
