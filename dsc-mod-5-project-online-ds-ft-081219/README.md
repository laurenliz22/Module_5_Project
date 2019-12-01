
# Predicting Tree Types

Aronson Consulting is looking into predicting tree types in the Roosevelt National Forest in Colorado for purposes of understanding the landscape.  The dataset used contains tree observations from four areas of the Roosevelt National Forest.  This dataset includes information on tree type, shadow coverage, distance to nearby landmarks (roads etcetera), soil type, and local topography.  Based on these characteristics Aronson Consulting will develop a model to predict the type of trees that is growing. 

### Background on Data: 

#### Features: Name / Data Type / Measurement / Description
- Elevation / quantitative /meters / Elevation in meters
- Aspect / quantitative / azimuth / Aspect in degrees azimuth
- Slope / quantitative / degrees / Slope in degrees
- Horizontal_Distance_To_Hydrology / quantitative / meters / Horz Dist to nearest surface water features
- Vertical_Distance_To_Hydrology / quantitative / meters / Vert Dist to nearest surface water features
- Horizontal_Distance_To_Roadways / quantitative / meters / Horz Dist to nearest roadway
- Hillshade_9am / quantitative / 0 to 255 index / Hillshade index at 9am, summer solstice
- Hillshade_Noon / quantitative / 0 to 255 index / Hillshade index at noon, summer soltice
- Hillshade_3pm / quantitative / 0 to 255 index / Hillshade index at 3pm, summer solstice
- Horizontal_Distance_To_Fire_Points / quantitative / meters / Horz Dist to nearest wildfire ignition points
- Soil_Type (40 binary columns) / qualitative / 0 (absence) or 1 (presence) / Soil Type designation
- Wilderness_Area(#):
 - Wilderness_Area2 = Neota) has the highest mean elevational value 
 - Wilderness_Area1 (Rawah) & Wilderness Area3 (Comanche Peak) have lower mean elevation value 
 - Wilderness_Area4 = Cache la Poudre has the lowest mean elevational value 

#### Target: Cover_Type:
- 1 = "Spruce/Fir", 2 = "Lodgepole Pine", 3 = "Ponderosa Pine", 4 = "Cottonwood/WIllow", 5 = "Aspen", 6 = "Douglas-fir", and 7 = "Krummholz" according to Kaggle 

### The final model 
The final model used to predict tree cover type is a Random Forest Classifier with n_estimators=1000 and max_depth=30.  Also MinMaxScaler was performed on the data. This gives an overall accuracy score of 90.4%

The overall accuracy of the random forest classifier can also be quantified by the AUC values of the ROC Curve looking at each tree cover type.  For each tree cover type we see a range of 97.5% to 99.9%, providing almost perfect predictions with our model!