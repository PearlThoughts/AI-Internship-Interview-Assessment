Dear Candidate,
As part of the evaluation process, we have provided four assessments. You are required to select one assessment, complete the coding task, and explain your solution using a Loom video.

## Submission Process:

- Choose one assessment from the provided options.
- Write the code and ensure it meets the given requirements and the code should be less than 25 lines. 

Sample code
```bash
import pandas as pd

import numpy as np

from sklearn.ensemble import RandomForestRegressor
 
# Load and preprocess data

def load_data():

    return pd.read_csv("appointment_data.csv")
 
def train_model(data):

    X, y = data[['doctor_id', 'scheduled_hour', 'actual_duration']], data['wait_time']

    model = RandomForestRegressor(n_estimators=100).fit(X, y)

    return model
 
def predict_wait_time(model, input_data):

    return model.predict(input_data)
 
def manage_early_arrivals(arrival, scheduled):

    return "Accommodate early" if (scheduled - arrival).seconds / 60 <= 20 else "Wait for slot"
 
def main():

    data = load_data()

    model = train_model(data)

    sample_input = np.array([[3, 18, 15]])

    print("Predicted Wait Time:", predict_wait_time(model, sample_input))

    print(manage_early_arrivals(pd.Timestamp('2024-03-25 17:40:00'), pd.Timestamp('2024-03-25 18:00:00')))
 
if __name__ == "__main__":

    main()
 
```
- Record a Loom video explaining your solution and approach.
- Raise a pull request (PR) with your completed code.
- Attach the Loom video link in both the PR description and the provided form.
- Please ensure your submission follows these steps for proper evaluation