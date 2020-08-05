# Reducing loss

- Hyperparameters are the configuration settings used to tune how the model is trained.
- Derivative of (y - y')^2 with respect to the weights and biases tells us how loss changes for a given example.
  - -> Simple to compute and convex.
- So we repeated ly take small steps in the direction that minimizes loss
  - -> We call these Gradient Steps (But they're really negative Gradiet Steps)
  - This stratedgy is called Gradient Descent

How big a step should you take in the gradient steps?

This is the Learning Rate - how big the step is. You can tweak this setting yourself.

Big steps and the model adjusts faster.
Small steps and the model adjusts slower.

You must choose a Learning rate that is large enough so gradient descent converges efficiently, but no so large it never converges =.

## Weight Initialization

This is where you start your gradient descent.

- For convex problems, weights can start anywhere (say, all 0s)
  - Convex -> bowl shaped, one minimum.
- Foreshadowing: not true for nerual nets.
  - Non convex -> think of an egg crate, more than 1 minimum.
  - Strong dependency on initial values.

## SGD and Mini-Batch Gradient descent.

