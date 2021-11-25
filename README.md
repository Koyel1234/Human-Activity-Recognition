# Human-Activity-Recognition
About the project:<br>
Project  Title: Human Activity Recognition<br>
Language Used: Python 3<br>
Dependencies: numpy, pandas, matplotlib.pyplot,seaborn, sklearn,scipy<br>
Data Source: https://www.utwente.nl/en/eemcs/ps/research/dataset/<br>

1. The whole data used for this project is provided in the folder Raw_Initial_Datasets. It contains 10 files from 10 participants. Each of these participants were equipped with five smartphones on five body positions. You can read more particulars of the dataset in the readme file provided inside Dataset folder. Each participant has 4 different sensor data out of which 3 sensor data  are used in this study. x-axis, y-axis, z-axis  values are available for all three sensors (Accelerometer, gyroscope, linear accelaration).

2. Primary EDA is done for the datasets to get an idea on how to proceed with the data. Codes for which are given in Diagrams_Human_Activity_Recognition.ipynb .

3. Each participant-i.csv file contains same sensor data from 5 different body positions. So we took the mean of all those 5 body positions for each x,y,z axis for 3 sensors (Accelerometer, Gyroscope and Linear Accelaration Sensor) and saved it in a csv named pi.csv for i-th participant, i= 1,2,3,.....,10. Each pi.csv contains 9 columns for the mean values and a column for activity label. Columns are: Mean of x-axis of accelerometr sensor from 5 body posictions(Acc_x), mean of y axis of accelerometr sensor from 5 body positions(Acc_y) and mean of z axis of accelerometr sensor from 5 body positions(Acc_z). Similarly for the other two sensors and they are named as Lin_x, Lin_y, Lin_z, Gyro_x, Gyro_y and Gyro_z respectively. 

4. These files are then used for feature creation. We created a 3 seconds time window i.e. time window of length 150 records per window with an overlap of 20% to  create new features (Statistical features over each window , performed Fast Fourier Transformation (FFT) over each window and create time domain features and frequency domain features of window) from this windows. These features for each participant is saved in a csv named pi_features.csv for the i-th participant, i=1,2,....,10.

5. The codes for pi.csv and pi_features.csv , i=1,2,3,....,10 are in raw_to_window_making.ipynb.

6. All the features created are provided in features.txt

7. So altogether we have 20 different output files (.csv) from the raw_towindow_making.ipynb  named p1.csv, p2.csv, p3.csv, p4.csv, p5.csv, p6.csv, p7.csv, p8.csv, p9.csv, p10.csv, p1_features.csv, p2_features.csv, p3_features.csv, p4_features.csv, p5_features.csv, p6_features.csv, p7_features.csv, p8_features.csv, p9 _features.csv and p10_features.csv.

8. These files are then used for model fitting and prediction.

9. p1_features.ipynb, p2_features.ipynb, p3_features.ipynb, p4_features.ipynb - these 4 jupyter notebooks contains the the codes to fit models seperately on p1_features.csv, p2_features.csv, p3_features.csv, p4_features.csv.

10. Validation.ipynb contains codes to do hyperparameter tuning from 4 fitted mpodels simultaneously using p5_features.csv, p6_features.csv, p7_features.csv, p8_features.csv.

11. The final model was saved in model.pkl.

12. We loaded this model in out_of_time_data.ipynb and applied on the test data to judge the performance of the model.

13. Out_of_time_data.ipynb tests the fitted model on features p9_features.csv and p10_features.csv.
