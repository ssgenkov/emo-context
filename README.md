# emo-context

This project was created as part of a participation in the "EmoContext A Shared Task on Contextual Emotion Detection in Text"  (https://www.humanizing-ai.com/emocontext.html). The task was to build a model to predict the emotion in the last message in a chat conversation. Each chat conversation contained 3 chat messages between two persons (User1 write something, User2 answers something back and User1 send a last message back). The provided dataset format was as follows:

A Training dataset containing 5 columns :

    ID - Contains a unique number to identify each training sample
    Turn 1 - Contains the first turn in the three turn conversation, written by User 1
    Turn 2 - Contains the second turn, which is a reply to the first turn in conversation and is written by User 2
    Turn 3 - Contains the third turn, which is a reply to the second turn in the conversation, which is written by User 1
    Label - Contains the human judged label of Emotion of Turn 3 based on the conversation for the given training sample. It is always one of the four values - 'happy', 'sad, 'angry' and 'others'

# Feature Engineering

As features was used:
 - word N-grams
 - emojis based features
 - emoticons based features
 - POS tags features
 - Depeche Mood (DM) emotion lexicon based features
 - NRC Emotion Lexicon based features
 - Characters/Stop words/Upper letters/ Punctuation count
 - Average words length

# Feature selection

For features selection was tried:
- Chi_2 
- LDA
- Logistic Regression
- LightGBM

# Model Seletion

For model selection was used Bayesian Optimization on LightGBM

# Deep Learning

LSTM and GRU based network with Glove embedding was tried, but LightGBM  model gave far better results.

# Final best result on the test set:
F1-Score - 0.6876

