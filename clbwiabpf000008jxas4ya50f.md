# Setup a Python environment in Linux

To start working on Machine Learning you need tools, and those tools need to be installed in an environment. Think of an environment as a kind of workshop, except instead of a hammer or a screwdriver, you have Python and Keras.

We will go through how to set up a Python Data Science/ML environment. In this article, we will focus on Linux, if you want to do this setup on Windows please [follow this tutorial](https://mlpills.hashnode.dev/setup-environment-in-windows). We will also show how to install the main Data Science/ML libraries such as TensorFlow, Keras, Numpy and Pandas within our environment.

## Check Python

First, make sure you have Python3 installed, it should be installed by default on any new Linux distribution, to do this open a terminal (Ctrl + Alt + T) and type `python3`:

```bash
python3
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671553920343/wVOsgpEg1.png align="center")

In this case, we have Python 3.8.10 installed if you don't, install Python3 on your system with the following commands:

```bash
$ sudo apt-get install software-properties-common
$ sudo add-apt-repository ppa:deadsnakes/ppa
$ sudo apt-get update
$ sudo apt-get install python3.8
```

## Create your environment

Now we will create a virtual environment for our libraries, first we need to make sure we have the Python package manager (pip) and venv installed:

```bash
sudo apt-get install -y python3-pip python3-venv
```

Then we can just create our virtual environment:

```bash
# Go to your home directory
cd

# Create a directory for your environments 
mkdir virtual_envs
cd virtual_envs

# Create the virtual environment
python3 -m venv mlpills

# Activate the environment
source mlpills/bin/activate
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671554689031/q5LQGoDgZ.png align="center")

You will see that the environment is correctly activated when the name of the environment appears between parenthesis before your username.

## Install your libraries

The last thing we need is to install the rest of the libraries, for that we use the following command:

```bash
pip3 install tensorflow keras numpy pandas
```

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671554805353/r-ad0924h.png align="center")

Once done, you will have all the Data Science/ML environment tools that will be covered in this blog. In future tutorials, we will make use of these tools to build different ML solutions to real-life problems.