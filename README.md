# Car-Price-Prediction-Model

This project builds a regression model to predict car prices based on historical car listing data.
The dataset (`autos.csv`) contains various vehicle attributes such as brand, fuel type, gearbox, power, and mileage.

---

## **Project Overview**

The goal is to create a machine learning model that can accurately predict car prices.
The project includes:

* Data cleaning and preprocessing.
* Handling missing values in key columns (`fuelType`, `gearbox`, `vehicleType`, etc.).
* Feature selection and encoding of categorical variables.
* Model training, evaluation, and improvement.

---

## **Dataset**

The dataset includes the following key columns:

* **`price`** – Target variable (car price).
* **`vehicleType`** – Type of the vehicle (SUV, limousine, etc.).
* **`yearOfRegistration`** – Year the car was registered.
* **`gearbox`** – Type of gearbox (automatic or manual).
* **`powerPS`** – Power of the car in PS.
* **`odometer`** – Mileage in kilometers.
* **`fuelType`** – Type of fuel (benzin, diesel, LPG, etc.).
* **`brand`** – Car brand.
* **`notRepairedDamage`** – Whether the car has unrepaired damage.

---

## **Steps in the Project**

### **1. Load and Inspect Data**

* Load the dataset using `pandas`.
* Inspect rows, columns, and data types.

### **2. Data Cleaning**

* Remove duplicates and irrelevant columns (`dateCrawled`, `name`, etc.).
* Fix data types (e.g., convert `price` and `odometer` to numeric).
* Remove unrealistic values (e.g., negative prices or impossible registration years).

### **3. Handle Missing Values**

* **fuelType**: Filled using brand-year mode, brand mode, or global mode.
* **gearbox**: Imputed based on year logic (older cars → manual).
* **vehicleType**: Predicted using a Random Forest model trained on other features.
* **notRepairedDamage**: Missing values replaced with `nicht_angegeben`.
* **model**: Missing values replaced with `andere`.

### **4. Feature Selection**

* Keep only relevant columns for prediction.
* Drop irrelevant or noisy features.

### **5. Encoding Categorical Variables**

* Apply one-hot encoding for columns like `vehicleType` and `fuelType`.
* Use label encoding where appropriate.

### **6. Train-Test Split**

* Split the dataset into training and testing sets (80/20).

### **7. Build and Evaluate Regression Model**

* Start with Linear Regression.
* Evaluate performance using:

  * Mean Squared Error (MSE)
  * Root Mean Squared Error (RMSE)
  * R² Score
* Experiment with advanced models (Random Forest, Gradient Boosting).

---

## **Project Structure**

```
├── autos.csv                # Original dataset
├── autos_cleaned.csv        # Preprocessed dataset
├── notebooks/               # Jupyter notebooks with EDA and modeling
├── scripts/                 # Python scripts for data cleaning and model training
├── README.md                # Project documentation
```

---

## **Setup Instructions**

### **Requirements**

* Python 3.8+
* Install required libraries:

  ```bash
  pip install -r requirements.txt
  ```

### **How to Run**

1. Place `autos.csv` in the project root directory.
2. Run the data cleaning script:

   ```bash
   python scripts/clean_data.py
   ```
3. Train the regression model:

   ```bash
   python scripts/train_model.py
   ```

---

## **Next Steps**

* Tune hyperparameters for better accuracy.
* Deploy the model as a web API (e.g., using Flask or FastAPI).
* Visualize results with interactive dashboards (e.g., Power BI, Tableau).

---

## **License**

This project is open-source and available under the MIT License.
