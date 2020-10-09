# PHY3810
# Selecting the Data for Modeling
import pandas as pd

gammaRaySimulation_file_path = '../home/annel/Documents/SimulationData/Gamma-RayData/0.0deg/gamma_0deg_180deg_run1283_3_112_phase1_desert.dst.root_CT1.csv'
gammaRaySimulation_data = pd.read_csv(gammaRaySimulation_file_path) 
gammaRaySimulation_data.columns


# Selecting The Prediction Target
y = gammaRaySimulation_data.#HillasParameters_Hillas0510_1_Known


# Choosing "Features"
gammaRaySimulation_features = ['HillasParameters_Hillas0510_1_NPixels', 'HillasParameters_Hillas0510_1_NPixels', 'HillasParameters_Hillas0510_1_Length', 'HillasParameters_Hillas0510_1_Length', 'HillasParameters_Hillas0510_1_Skewness', 'HillasParameters_Hillas0510_1_Kurtosis', 'HillasParameters_Hillas0510_1_CoG_x', 'HillasParameters_Hillas0510_1_CoG_y', 'HillasParameters_Hillas0510_1_Phi']

X = gammaRaySimulation_data[gammaRaySimulation_features]

# Reviewing the data by using the describe method and the head method, which shows the top few rows.
X.describe()
X.head()


# Building the Model
from sklearn.tree import DecisionTreeClassifier

# Define model. Specify a number for random_state to ensure same results each run.
gammaRaySimulation_model = DecisionTreeClassifier(random_state=1)

# Fit model
gammaRaySimulation_model.fit(X, y)


# Make predictions for the first few rows of the training data to see how the predict function works.
print("Making predictions for the first 5 rows:")
print(X.head())
print("The predictions are")
print(gammaRaySimulation_model.predict(X.head()))

