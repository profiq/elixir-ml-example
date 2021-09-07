# Convolutional Neural Net in Elixir

In this repository we demonstrate the use of various machine learning tools 
offered by the Elixir ecosystem. Using these tools, we build, train and test a simple
convolutional neural network for detecting pneumonia in x-ray chest scans.

Following Elixir libraries and projects are used:

- [Livebook](https://github.com/livebook-dev/livebook): Elixir equivalent of Jupyter Notebook
- [Nx](https://github.com/elixir-nx/nx): Multidimensional arrays for Elixir (similar to Python's NumPy)
- [EXLA](https://github.com/elixir-nx/nx/tree/main/exla): Client library for Google's XLA compiler
- [Axon](https://github.com/elixir-nx/axon): Neural networks for Elixir

## Installation

*This guide assumes you already have Elixir installed on your machine. 
You also need Bazel 3.7.2 to build Tensorflow from source. We recommend installing this specific version
with [asdf](https://asdf-vm.com/).*

1. Clone Livebook repo:

```
$ git clone https://github.com/livebook-dev/livebook.git
$ cd livebook
```

2. Add following dependencies to the `mix.exs` file:

```
{:exla, "~> 0.1.0-dev", github: "elixir-nx/nx", sparse: "exla"},
{:nx, "~> 0.1.0-dev", github: "elixir-nx/nx", sparse: "nx", override: true},
{:axon, "~> 0.1.0-dev", github: "elixir-nx/axon"}
```

3. Install and compile the dependencies with mix:

```
$ mix deps.get
$ mix deps.compile
```

## Accessing the livebook notebooks

1. Clone this repo inside the livebook directory

```
$ git clone git@github.com:profiq/elixir-ml-example.git
```

2. Start the livebook server

```
$ mix phx.server
```

By default, the server will listen on port 4000. You can access it in your browser on [http://localhost:4000].
There you can open the `elixir-ml-example/train.livemd` notebook. Executing all elixir cells results in 
training and storing the model in a file. To test the model you can then 
open the `elixir-ml-example/test.livemd` notebook.

## Dataset

We use the [Chest X-Ray Images (Pneumonia)](https://www.kaggle.com/paultimothymooney/chest-xray-pneumonia) 
dataset from Kaggle. This repository contains its preprocessed version in a binary format.