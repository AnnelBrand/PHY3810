# PHY3810
import pandas as pd

gammaRaySimulation_file_path = '../home/annel/Documents/SimulationData/Gamma-RayData/0.0deg/gamma_0deg_180deg_run1283_3_112_phase1_desert.dst.root_CT1.csv'
gammaRaySimulation_data = pd.read_csv(gammaRaySimulation_file_path) 
gammaRaySimulation_data.columns
