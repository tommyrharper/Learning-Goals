# Framing

## Supervised ML

ML systems learn how to combine input to produce useful predictions on never-before-seen data.

### Labels and features

- Labels e.g. spam/not-spam for emails. -> y
- Features - the way we represent the data e.g. words in the email/sender. -> x1, x2 ... xn

### Examples and models

- Example - is one peice of data e.g. an email. x
- Labeled example - has {features,label}: (x,y)
  - -> Used to train the model
- Unlabeled example - has {feature, ?}: (x, ?)
  - -> Used for making predictions on new data/testing/real world/inference.
- Model - maps examples to predicted labels: y'
  - -> Defined by internal learned parameters.
  - Training menas learning or creating the model.
  - Inference means applying the trained model to unlabeled examples.

## Regression vs. classification

A regression model predicts continuous values e.g.
- What is the value of a house in California?
- What is the probability a user will click this add?

A classification model predicts discrete values, e.g.
- Is a given email message spam or not spam?
- Is this an image of a dog, a cat or a hamster?


