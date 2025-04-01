# Student Performance Prediction using Supervised Learning

## Project Overview
This project initially utilized K-Means clustering to group students based on various performance indicators. However, after evaluating the scalability of the approach, we transitioned to supervised learning techniques, specifically **Random Forest** and **Regression Models**, to provide more accurate predictions and personalized feedback.

## Key Features
- **Data Preprocessing**: Handling missing values, encoding categorical data, and scaling numerical values.
- **Supervised Learning Approach**: Implementing **Random Forest Classification** for performance prediction and **Regression Models** for score estimation.
- **Personalized Feedback**: Based on predicted performance categories and estimated scores.
- **Model Evaluation**: Using accuracy, precision, and mean absolute error to assess model performance.
- **CSV and PDF Output**: Predictions are stored in **CSV format**, including performance marks and labels (High, Medium, Low), while **PDF reports** visualize performance using radar charts.

## Technologies Used
- Python
- Pandas
- NumPy
- Scikit-learn
- Matplotlib
- Joblib

## Dataset Features
The dataset includes the following features:
- `CGPA`: Student's academic performance.
- `Part of any club or society`: Categorical (0: None, 1: Club, 2: Society, 3: Both).
- `Position in club or society`: Categorical (0: Not a part, 1: Intern, 2: Co-executive, 3: Executive, 4: Director, 5: Treasurer, 6: Joint-secretary, 7: Secretary, 8: Student advisor).
- `Sports Participation`: Categorical (0: None, 1: Plays outdoor game, 2: Plays indoor game).
- `Internships`: Categorical (0: No, 1: Online, 2: Offline).
- `Number of Competitions Participated`
- `Participation in Hackathons`: Binary (0: No, 1: Yes).
- `Online and Offline Hackathon Count`
- `Final Performance Label`: (Used for training supervised models)

## Project Workflow
1. **Data Preprocessing:**
    - Convert non-numeric values to numeric using encoding techniques.
    - Handle missing values by filling or imputing.
    - Scale numerical features using `StandardScaler`.

2. **Model Training:**
    - Train a **Random Forest Classifier** to categorize students into performance groups.
    - Use **Regression Models** to predict specific performance scores.
    - Save the trained scaler and models using `joblib`.

3. **Prediction and Feedback Generation:**
    - Input new student data.
    - Scale and preprocess input using the trained scaler.
    - Predict the performance category and estimated score.
    - Save predictions in **CSV format** and generate a **PDF report** with radar charts.

## Running the Project
### Install Required Libraries
```bash
pip install pandas numpy scikit-learn matplotlib joblib
```

### Train the Model
```bash
python train_model.py
```

### Predict and Provide Feedback
```bash
python predict_student_performance.py
```

## Performance Categories and Feedback
- **Category 0 (Average Performer):** Encouraged to improve participation in extracurriculars and internships.
- **Category 1 (High Performer):** Advised to take on leadership roles and competitive projects.
- **Category 2 (Needs Improvement):** Strong recommendations for increasing involvement in practical learning experiences.

## Visualization
- **Feature Importance Analysis** using Random Forest.
- **Accuracy vs. Number of Trees** Graph for model evaluation.
- **Predicted vs. Actual Scores** using Regression techniques.
- **Radar Charts** in PDF format to visualize performance.

## Model Saving and Deployment
- The trained **Random Forest Classifier** and **Regression Model** are saved using `joblib.dump()`.
- The models are loaded for predictions using `joblib.load()`.

## Example Output for K-means
```
Predicted Performance Category: 2
Performance Feedback:
You need improvement. Consider focusing on:
- Participating in competitions and hackathons.
- Joining clubs and societies to enhance teamwork skills.
- Applying for internships to gain industry experience.
```
## Example output for Random Forest and Regression based model Predicted_Performance_Marks  
             Name         Uid Predicted_Performance_Label  \                            
0       Meenakshy  22BAI71194                         Low                                20  
1  SAMRIDHI SINGH  22BAI70775                      Medium                                60  
2  Aditya Niphade  22BAI70091                        High                                88  
3          Shreya  22BAI70099                         Low                                 2
4      Mohd Rahil  22BAI70212                      Medium                                50
                          100  
## Author
Rohan Raghav
