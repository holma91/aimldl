For every header, there's an accompanying notebook.

## Tensors


## Data

Dataset: stores samples and corresponding labels.
A custom Dataset class must implement three functions: __init__, __len__, and __getitem__

DataLoader: wraps an iterable around a Dataset.
While training a model, we typically want to pass samples in “minibatches”, reshuffle the data at every epoch to reduce model overfitting, and use Python’s multiprocessing to speed up data retrieval.

DataLoader is an iterable that abstracts this complexity for us in an easy API.


## Transforms

Data does not always come in its final processed form that is required for training machine learning algorithms. We use transforms to perform some manipulation of the data and make it suitable for training.


## Neural Networks

The torch.nn namespace provides all the building blocks you need to build your own neural network. Every module in PyTorch subclasses the nn.Module. A neural network is a module itself that consists of other modules (layers). This nested structure allows for building and managing complex architectures easily.