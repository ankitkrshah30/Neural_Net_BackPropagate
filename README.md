# Neural Network From Scratch (Learning Project)

This repository is a learning-focused implementation of a small **Multi-Layer Perceptron (MLP)** built from scratch in Python, inspired by how modern deep-learning libraries work internally.
The purpose of this project is **conceptual understanding**, not performance.
---

## What This Project Covers
This project helped me understand:
- how neurons work  
- how layers are formed  
- how multi-layer networks are built  
- how loss functions work  
- how gradients are computed  
- how parameters are updated  
- how decision boundaries are learned  
---
## Core Idea
Each neuron computes:
```
output = tanh(w·x + b)
```
Where:
- `w` = weights  
- `x` = inputs  
- `b` = bias  
---
## Architecture
A network is defined like:
```python
MLP(3, [4, 4, 1])
```
Meaning:
```
3 inputs
→ 4 neurons
→ 4 neurons
→ 1 output
```
---
## Parameters
Parameters are the values the model learns:
- all weights
- all biases
Calling:
```python
mlp.parameters()
```
returns every trainable value.
For the above architecture, the network contains **41 parameters**.
---
## Forward Pass
During the forward pass:
- inputs flow through the layers
- each neuron computes an activation
- the final output is produced
This is the model’s prediction.
---
## Loss Function
To measure error, we compute a loss such as:
```
loss = Σ (prediction - target)²
```
Higher loss means worse predictions.
---
## Backpropagation
Calling:
```python
loss.backward()
```
computes gradients for all parameters.
Each gradient answers:
> “If this value increases slightly, how does the loss change?”
---
## Gradient Descent (Learning / Nudging)
Parameters are updated using:
```python
p.data -= learning_rate * p.grad
```
This is gradient descent:
- gradients point uphill
- subtracting moves downhill
- downhill = lower loss
Repeated many times, this slowly improves predictions.
---
## Binary Classification
Targets are typically:
```
-1 or 1
```
So:
- positive output → one class
- negative output → other class
---
## Synthetic Datasets
Toy datasets like `make_moons` are used to:
- test nonlinear models
- visualize decision boundaries
- understand why hidden layers matter
---
