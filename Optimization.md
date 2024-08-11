![image](https://github.com/user-attachments/assets/336b3903-6dc9-4fd6-a993-285c3118e8a3)

![image](https://github.com/user-attachments/assets/cfe1150b-30cd-4f97-babb-2f8ac0350b3e)

config = {'units': 150, 'dropout': 0.2, 'learning_rate': 0.001}- BA
- Best Configuration - Years: 50, Batch Size: 32, Epochs: 40 - MAE: 0.03242554741382376

#### Sample output
![image](https://github.com/user-attachments/assets/97d40e75-4a51-488d-822d-7e4855c8964a)

## Overfitting measurement

We included a parameter to check for overfitting in the code by monitoring the training and validation losses during the model training process. Overfitting occurs when the model performs well on the training data but poorly on the validation data, indicating that it has learned the training data too well (including noise) and is not generalizing to unseen data.

Steps :

- Split the Training Data: Split the training data into training and validation sets.
- Track Training and Validation Losses: Use these sets to track the training and validation losses during the model fitting.
- Early Stopping (Optional): Implement early stopping if the validation loss stops decreasing.


Question : Should we use callbacks=[early_stopping]
