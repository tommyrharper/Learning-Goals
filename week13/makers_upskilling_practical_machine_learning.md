# Makers Upskilling, Practical Machine Learning

ZackAkil

## links
Hey Makers, for those of you who attended :makers: Makers Upskilling Practical Machine Learning Literacy ft. Zack from Google :makers: last night, Zack has very kindly shared his whole slide deck (which includes the links to all the Colab notebooks, examples and demos) attached. Thanks to all of you who came, I hope you found it interesting!
For those who couldn’t make it, here is the Zoom recording of the webinar:
https://us02web.zoom.us/rec/share/-fxkLp_gxD5LZdLD5hzjZbYHGpbEeaa8g3Qa-PFYmknTLl6ShGCbzgSewTFOZSJ5 Password: 2i%8jOH&
Follow Zack - GitHub: https://github.com/ZackAkil Twitter: https://twitter.com/ZackAkil
Zack’s back with another remote workshop on Thursday 25th June 6pm with Makers Upskilling: How to make a splash in your workplace with ML. Find out more and get your tickets here: https://www.eventbrite.co.uk/e/makers-upskilling-how-to-make-a-splash-in-your-workplace-with-ml-tickets-108875603862?aff=studentslack

------------

On Alumni slack there is a blogging competition. There is a £2500 hiring bonus if you hook up Makers with a job.

Traditional programming -> input data + the rules --- bleep bloop ----> answers
ML -> Input data + Answers ---- bleep bloop ---> Rules (found through training)

## Common ML Workflow

Image -> Normal

Image -> Pneumonia

input = image, output = normal/pneumonia

Input data | Output data
Input data | Output data
Input data | Output data -----> Training examples/training dataset
Input data | Output data
Input data | Output data
Input data | Output data
---------------------------
Input data | Output data
Input data | Output data
Input data | Output data ----> Test examples/test dataset
Input data | Output data


ML learns the pattern between input and output on training examples

Using the test examples:

Input data -- Model --> Model prediction vs Output data WRONG
Input data -- Model --> Model prediction vs Output data CORRECT
Input data -- Model --> Model prediction vs Output data CORRECT
Input data -- Model --> Model prediction vs Output data CORRECT ---> therefore 75% accuracy

## Types of ML
supervised --> input and answers --> very common and useful
unsupervised ---> just input
reinforcement learning --> making multiple predictions of actions to take -- for playing games and cool stuff --> niche

### Supervised

1. Classificaiton --> given some input, predict the class e.g. cat
2. Regression --> given some input, predict the value e.g. 23

## Input data

If it can be converted into data it can be used

1. Tabular/structured
2. Text/Natural Language/NLP -> unstructured
3. Image -> unstructured

These are the most common 3.

kaggle.com ---> for data sets

### Linear Regression

Line of best fit.

y = mx + c

http://bit.ly/zack-line

### Do it yourself

sklearn is a popular library you can use

## Classification

Decision tree algorithm.

http://bit.ly/zack-tree

Decision tree is very transaparent, you can see how it makes the decisisons.

## Handling text

http://bit.ly/zack-text-tree

### Overfitting

When your model learns the noise rather than the underlying pattern.

## AutoML

