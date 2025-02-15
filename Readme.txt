# Student Performance Clustering using K-Means

## Project Overview
This project uses the K-Means clustering algorithm to group students based on various performance indicators. It aims to analyze students' academic and extracurricular performance and provide personalized feedback based on their cluster.

## Key Features
- Data preprocessing and scaling using `StandardScaler`.
- K-Means clustering to group students into performance categories.
- Predictive model allowing new student data to be classified into a cluster.
- Personalized feedback based on the predicted cluster, highlighting areas for improvement.

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
- `Sports`: Categorical (0: None, 1: Plays outdoor game, 2: Plays indoor game).
- `Any internship yet`: Categorical (0: No, 1: Online, 2: Offline).
- `How many Competitions participated?`
- `Participated in hackathon?`: Binary (0: No, 1: Yes).
- `How many Online hackathons?`
- `How many Offline hackathons?`

## Project Workflow
1. **Data Preprocessing:**
    - Convert non-numeric values to numeric using `pd.to_numeric()`.
    - Handle missing values by dropping or imputing.
    - Scale the data using `StandardScaler`.

2. **Model Training:**
    - Apply K-Means clustering with an optimal number of clusters (determined using the elbow method).
    - Save the trained scaler and K-Means model using `joblib`.

3. **User Input & Prediction:**
    - Collect new student data.
    - Scale input data using the saved scaler.
    - Predict the cluster using the trained K-Means model.
    - Provide personalized feedback based on the predicted cluster.

## Running the Project
1. **Install Required Libraries:**
```bash
pip install pandas numpy scikit-learn matplotlib
```
2. **Train the Model:**
```python
python train_model.py
```
3. **Predict and Provide Feedback:**
```python
python predict_student_performance.py
```

## Personalized Feedback
- **Cluster 0 (Average Performance):** Suggestions to improve participation in competitions, clubs, and internships.
- **Cluster 1 (Excellent Performance):** Positive feedback with encouragement to take leadership roles.
- **Cluster 2 (Needs Improvement):** Strong suggestions to increase involvement in extracurriculars, hackathons, and internships.

## Visualization
- Use Matplotlib to plot the elbow curve for selecting optimal K.
- Visualize clusters if needed using scatter plots.

## Saving and Loading Model
- Use `joblib.dump()` to save `StandardScaler` and `KMeans` model.
- Use `joblib.load()` to load the scaler and model during prediction.

## Example Output
```
Predicted Cluster: 2
Performance Feedback:
You need some improvement. Consider focusing on the following areas:
- Boost your participation in competitions and hackathons.
- Engage in a club or society to develop leadership and teamwork skills.
- Look for internship opportunities to gain practical industry experience.
```

## Author
Rohan Raghav

## License
This project is licensed under the MIT License.
