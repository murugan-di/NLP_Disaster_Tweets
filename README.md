# NLP_Disaster_Tweets

Description

This project is part of the Kaggle competition: Real or Not? NLP with Disaster Tweets. The goal is to predict whether a tweet is disaster-related (1) or not (0) based on its content.
Dataset

The dataset contains two main files:

    train.csv: Contains tweets and their corresponding labels (1 for disaster-related, 0 for not).
    test.csv: Contains tweets without labels for which predictions are generated.

Steps
1. Data Exploration

    Dataset Overview:
        Examined the structure, summary statistics, and potential issues like missing values or duplicates.
        Visualized the target distribution (pie chart and bar plot) to understand class imbalance.
        Analyzed the distribution of tweet lengths.

2. Data Preprocessing

    Cleaning:
        Removed duplicates in the text column.
        Converted text to lowercase, removed special characters, and filtered stopwords.
    Tokenization and Padding:
        Tokenized the text using Keras's Tokenizer to convert words into sequences.
        Padded sequences to ensure uniform length for model input.

3. Model Development

The deep learning model is built using TensorFlow/Keras:

    Architecture:
        Embedding Layer: Maps words to dense vectors of fixed size.
        Bidirectional LSTM Layers: Three layers with 256 units each to capture both forward and backward dependencies in the text.
        Dropout: Regularization applied after each LSTM layer to reduce overfitting.
        Dense Layers: Includes a fully connected layer with ReLU activation and an output layer with sigmoid activation for binary classification.

    Compilation:
        Loss function: Binary Cross-Entropy.
        Optimizer: Adam with a learning rate of 0.001.
        Metric: Accuracy.

4. Training

    Data Splits:
        Training set: 70% of the data.
        Validation set: 15% of the data.
        Test set: 15% of the data.
    Model trained for 10 epochs with a batch size of 64.

5. Evaluation

    Metrics:
        Training accuracy: 99.79%
        Validation accuracy: 73.07%
        Test accuracy: to be determined based on the test data.
    Visualizations:
        Training and validation accuracy plotted to observe model performance.
        Confusion matrix generated for detailed evaluation of test set predictions.

6. Submission

    Predictions for the test dataset are saved in a submission.csv file in the required Kaggle format:

    id,target
    0,0
    1,1
    2,0

Results

    Training Performance:
        The model achieves an exceptionally high training accuracy of 99.79%, indicating the ability to fit the training data well.
        The validation accuracy is 73.07%, reflecting generalization challenges due to potential overfitting.

    Key Observations:
        The gap between training and validation accuracy indicates that the model may be overfitting, suggesting improvements like additional regularization or simpler architectures.
        The high complexity of the Bidirectional LSTM layers captures sequential patterns but might require fine-tuning for better validation results.

Learnings

    Deep Learning for NLP:
        Embedding layers and LSTM-based architectures are powerful for sequence modeling tasks like text classification.
        Bidirectional LSTMs effectively capture contextual information, improving performance on challenging datasets.

    Challenges in Generalization:
        A significant training-validation accuracy gap suggests the need for techniques like dropout, early stopping, or reducing model complexity to mitigate overfitting.

    Preprocessing Impacts:
        Text cleaning (stopword removal, lowercasing, etc.) significantly improves input quality for the model.

    Kaggle Workflow:
        Submitting predictions in the correct format is essential for participation in competitions.

Feel free to enhance the README further based on additional insights! Let me know if you'd like help with further modifications or improvements.
