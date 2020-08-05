# Descending into ML

## Example

Image you have:

House price - y
House square footage - x

y = wx + b
y = w1b1 + b

Loss is how far each data point from the line of best fit.
Positive loss, is the point is below the line, i.e. £300 when the line says £500.
Negative loss is the point above the line, i.e. says £700 when the line says £500.

## Loss Function for Regression

L2Loss for a given example is also called squared error.

= Square of the difference between prediction and label
= (observerd - prediction)^2
= (y - y')^2

L2Loss = SUM(x,y)->D(y - prediction(x))^2

