# AP_Final

Welcome to my Advanced Programming project. This repository contains a .ipynb file which runs a GUI using Gradio (Final_GUI.ipynb). This GUI has two primary functionalities:<br><br>
First, the user can input text and run a BERT sentiment analysis prediction on it. They can choose which classifier to use (Neural Net, Random Forest, or XGBoost), which dataset they want their prediction to have been trained on, and finally the task (Emotion Detection, Positive/Neutral/Negative, or Star Rating). <br><br>
Second, the user can choose to train their own model by uploading a datafile of their choosing. Once training is complete, the program saves their model as a pickle file in the folder Your_Pickle. If they want, the user can then use this trained model to predict sentiment as explained above. <br><br>
The pre-trained models are found in the Pickle folder, originating from the ADA project.<br><br>
For each one of the classification methods, there is a prediction .py file, where the required code to run predictions for the associated classifier is present (NN_prediction.py, XGBoost_prediction.py, RF_prediction.py). These files are essential for the first half of the GUI. One can also find the .py files for each classification method that contain the script for training one's own model (BERT_NN_GUI.py, BERT_XGBOOST_GUI.py, and BERT_RF_GUI.py). These files vary slightly from those found in the ADA repository.<br><br>
Unfortunately due to an oversight during development of this GUI, the original .py scripts that were used to train the pickle files will also need to be present in the environment when running the GUI for predicitions. This also includes cleaning.py.
Finally, one can find the cleaning_for_GUI.py file, which contains the code for cleaning datasets into a useable format as well as some other useful functionalities.<br><br>


Warning: as of current release, you are able to use any trained model for any task when using the prediction functionality. However, for accurate results, use twitter for emotion prediction, imdb for positive/negative, reddit for positive/negative/neutral, and yelp for star ratings. I have not yet found how to make "greyed-out" options, so that it is impossible to predict star ratings on a model that was trained on twitter data, for example.<br><br>

Warning: To train a model on your own dataset, please have two columns named 'text' and 'label' in order for the program to function as intended. Possible file extensions are .csv .tsv .parquet <br><br>

Warning: Do NOT train more than 1 dataset for a given classification method. As of current release, if you want to run predictions on your own dataset, the program will only read the first datafile uploaded for a given classification method. If you wish to use a new datafile, you will have to go into the 'Your_Pickle' folder and delete the previous datafile uploaded<br><br>

Note: You will notice that for the second task, the output box for an evaluation graph unfortunately is not present. Due to limited time I was unable to figure out how to include that in the GUI code. As such, it is recommended to run the GUI for training where some kind of terminal is visible, as the classification report is still being printed out there. <br><br>

Note: File locations will need to be changed in many of the scripts