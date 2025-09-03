📈 Linear Regression Project — Car MPG \& Diamond Price



This repository demonstrates an end-to-end, beginner-friendly but thorough workflow for linear regression using two classic datasets:



Auto MPG — predict miles-per-gallon (MPG) from vehicle attributes



Diamonds — predict price from diamond characteristics



The notebook walks through data loading → exploratory plots → feature selection → model training → evaluation → prediction.

All exploratory scatter plots are pre-exported and stored in the assets/ folder for use in reports or slides.





🎯 Objectives



Build simple linear regression models for tabular prediction tasks



Practice feature selection and interpret exploratory plots



Evaluate models with R² score and make point predictions



Reuse plots (already exported to assets/) for presentations



🗂 Datasets



Loaded directly from IBM Skills Network public buckets (as used in the notebook):



Auto MPG

https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0231EN-SkillsNetwork/datasets/mpg.csv



Diamonds

https://cf-courses-data.s3.us.cloud-object-storage.appdomain.cloud/IBM-BD0231EN-SkillsNetwork/datasets/diamonds.csv



🔍 Exploratory Data Analysis (EDA)

A) Auto MPG — Relationships to MPG



The notebook visualizes how engine/vehicle attributes relate to MPG:



Horsepower vs MPG





Cylinders vs MPG





Engine Displacement vs MPG





Weight vs MPG





Intuition from plots (typical patterns):



Higher horsepower, cylinders, displacement, and weight generally correlate with lower MPG.



B) Diamonds — Relationships to Price



The notebook explores how physical characteristics relate to price:



Carat vs Price





“s” vs Price (as used in the notebook’s column selection)





Depth vs Price





Table vs Price





Intuition from plots (typical patterns):



Carat has a strong positive relationship with price.



Depth and table often show weaker or more nuanced relationships.



🧠 Feature Sets \& Targets

Auto MPG



Target: MPG



Features: Horsepower, Weight



Diamonds



Target: price



Features: carat, depth (as per the model in the notebook)



🧪 Modeling \& Evaluation



Both tasks use sklearn.linear\_model.LinearRegression trained on the full dataset (no split in the lab).

Evaluation uses the R² score (model.score(X, y)), where higher is better.



Results

1\) Auto MPG — Linear Regression



Model: MPG ~ Horsepower + Weight



R² (on full data): 0.7063752737298348



Example prediction:

Input Horsepower = 100, Weight = 2000 ⇒ MPG ≈ 29.3216



Interpretation:

A simple two-feature linear model captures a substantial share of variance in MPG (≈70%). Plots indicate the expected negative relationships between power/weight and fuel economy.



2\) Diamonds — Linear Regression



Model: price ~ carat + depth



R² (on full data): 0.8506754571636563



Example prediction:

Input carat = 0.3, depth = 60 ⇒ price ≈ 244.956



Interpretation:

With just carat and depth, the model explains ~85% of price variance—carat is highly predictive; depth adds a smaller adjustment.



🧭 Step-by-Step (Notebook Flow)



Load data via pandas.read\_csv from the given URLs



Visual EDA with DataFrame.plot.scatter to inspect relationships



Select features/target per task



Instantiate \& fit LinearRegression()



Evaluate with model.score(X, y) (R²)



Predict sample values to sanity-check the model



🛠️ Tech Stack



Python 3.10+, Jupyter Notebook/Lab



Libraries: pandas, numpy, matplotlib, scikit-learn



▶️ How to Run

\# 1) Clone

git clone https://github.com/<your-username>/linear\_regression\_project.git

cd linear\_regression\_project



\# 2) (Optional) Create \& activate a venv

python -m venv venv

\# Windows: .\\venv\\Scripts\\activate

\# macOS/Linux:

source venv/bin/activate



\# 3) Install deps

pip install -r requirements.txt



\# 4) Launch

jupyter lab

\# Open "Building\_and\_training\_a\_model\_using\_Linear\_Regression.ipynb" and run cells



✅ Key Takeaways



Simple linear models can be strong baselines:



Auto MPG with only Horsepower and Weight already achieves R² ≈ 0.71.



Diamonds with just carat and depth achieves R² ≈ 0.85.



EDA guides feature choices: Visual trends in scatter plots help prioritize variables.



Predictions are interpretable: The model outputs make intuitive sense when cross-checked with domain intuition.



💡 Suggestions / Next Steps



Train/Test Split or Cross-Validation

Evaluate generalization (e.g., train\_test\_split or KFold) and report test R².



Residual Diagnostics

Plot residuals vs fitted, check normality of residuals, and look for heteroscedasticity.



Add/Compare Models

Try Ridge/Lasso/ElasticNet (regularization), PolynomialFeatures, and tree-based models; compare metrics.



Feature Engineering

For Auto MPG, include acceleration, model year, origin, or encoded categorical variables if available.

For Diamonds, consider cut, color, clarity, or dimensions (x, y, z) if present.



Scaling

Standardize features if you expand to models sensitive to scale.



Persist Models

Export trained models with joblib and add a small CLI or notebook cell to load \& predict.



👤 Author



Shyam Sundar Vijayakumar



📜 License



MIT — feel free to use and adapt with attribution.



📎 Notes on Assets



All exploratory plots used in the notebook are provided in assets/ and referenced above:



scatterplot\_horsepower\_vs\_MPG.png



scatterplot\_cylinders\_vs\_MPG.png



scatterplot\_engine\_disp\_vs\_MPG.png



scatterplot\_weight\_vs\_MPG.png



scatterplot\_carat\_vs\_price.png



scatterplot\_s\_vs\_price.png



scatterplot\_depth\_vs\_price.png



scatterplot\_table\_price.png

