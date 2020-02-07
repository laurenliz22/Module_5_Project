# Predicting Forest Cover Type in the Roosevelt National Forest 
The purpose of this project is to predict the forest cover type based on the predominant kind of tree cover in the Roosevelt National Forest of Colorado to gain an understanding of the ecosystem. The dataset that is used contains tree observations from four wilderness areas of the Roosevelt National Forest. This dataset includes information on tree cover type, shadow coverage, wilderness areas, soil type, and local topography. Based on the data I will develop a model to best predict the forest cover type reflecting the predominant tree coverage in each area as determined by the US Forest Service.

## Background on Data:
The study area includes four wilderness areas located in the Roosevelt National Forest of Colorado. Each tree cover type reflects a 30m x 30m patch.

### Target: Forest Cover Type (Cover_Type)
1 - Spruce/Fir
2 - Lodgepole Pine
3 - Ponderosa Pine
4 - Cottonwood/Willow
5 - Aspen
6 - Douglas-fir
7 - Krummholz

### Features:
Elevation - Elevation in meters
Aspect - Aspect in degrees azimuth
Slope - Slope in degrees
Horizontal_Distance_To_Hydrology - Horz Dist to nearest surface water features
Vertical_Distance_To_Hydrology - Vert Dist to nearest surface water features
Horizontal_Distance_To_Roadways - Horz Dist to nearest roadway
Hillshade_9am (0 to 255 index) - Hillshade index at 9am, summer solstice
Hillshade_Noon (0 to 255 index) - Hillshade index at noon, summer solstice
Hillshade_3pm (0 to 255 index) - Hillshade index at 3pm, summer solstice
Horizontal_Distance_To_Fire_Points - Horz Dist to nearest wildfire ignition points
Wilderness_Area (4 binary columns, 0 = absence or 1 = presence) - Wilderness area designation
Soil_Type (40 binary columns, 0 = absence or 1 = presence) - Soil Type designation

## Conclusion
In Conclusion, The XGBoost model performs the best on the data, followed by the Random Forest Model. It is interesting that both models have similar misclassification when looking at the confusion matrices, but the important features used to classify the Cover_Type is different. The XGBoost model primarily uses Soil_Type features, while the Random Forest model uses Elevation. This is because the XGBoost model is boosting up weaker learners. If the model continued to be tuned, it would eventually have equal importance for all features. This is the reason XGBoost is a better model, it doesn't rely heavily on one feature where the Random Forest does. The XGBoost therefore may perform well on other sets of forest data. In the end, we see 91.5% accuracy with the XGBoost model on the test data!

Future work could include additional grid searches on the model to increase accuracy and performance on other sets of forest data, if available.
