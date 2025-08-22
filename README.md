# AeroConnect Passenger Forecasting

## Overview
This project focuses on forecasting passenger traffic for AeroConnect flight routes using a variety of machine learning models. By predicting future traffic patterns, AeroConnect can make more informed decisions about where to scale operations and allocate resources effectively.

## Data
The dataset contains passenger, freight and mail counts and weights across multiple international routes. After initial exploration, the data was cleaned to remove inconsistencies, handle missing values, and ensure uniform formatting for modeling.

**Cleaned Data:**  https://drive.google.com/file/d/1EfCjZqelh7I3JUxd6Fx4Y5t0u80f3hi1/view?usp=sharing
**Report:** https://drive.google.com/file/d/1Ze2OP8SHSiwVYMa_z4QoCKqJpVrj6RuT/view?usp=sharing

---

## Process

### 1. Data Cleaning
- Removed missing/null values and checked for duplicates. 
- Had to rename features names to match given convention.
- Added features like proper DateTime format of Month-Year, Quarter and Continent of Foreign Port.
 
### 2. Investigative Analysis
- Time was split by Monthly, Quarterly, Yearly. Additionally, only months and quarters kept to look
for seasonal patterns.
- Locations of Foreign Ports were analyzed individually, grouped by country and then grouped by continent.
- Traffic was grouped by Passenger, Freight & Mail. Often times, the "most popular" routes remained
the same across all three.

### 3. Model Selection
Four different models were implemented and evaluated:

1. **Linear Regression**  
   - Baseline model for comparison.  
   - Achieved moderate accuracy (~77%).  
   - Straightforward and interpretable.  

2. **Random Forest**  
   - Best-performing model overall.  
   - Fine-tuned number of trees (optimal at 200).  
   - Avoided max depth restriction, as it created disproportionate performance on certain routes.  
   - Accuracy improved significantly over baseline.  

3. **k-NN Modeling**  
   - Explored different `k` values (3, 5, 7).  
   - Found that `k=5` balanced generalization and accuracy.

4. **Feedforward Neural Network**  
   - Implemented using `nn.Sequential()` with 2 hidden layers of 32 neurons each and ReLU activation.  
   - Provided flexibility in learning non-linear relationships.  
   - Performed slightly below Random Forest but showed potential with further tuning.
