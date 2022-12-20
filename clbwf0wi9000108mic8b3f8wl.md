# How to setup your Data Science/ML environment in Windows

In this post, we will go through how to set up a Python Data Science/ML environment. We will be covering both Windows and Linux. We will be installing TensorFlow, Keras, Numpy and Pandas, as well as creating a virtual environment for it.

## Windows

The first thing we need to do is install Python. For that, you have to go to https://www.python.org/downloads/windows/ and download Python 3.10.X (by X I mean any version of Python that starts with 3.10, such as 3.10.9, 3.10.11), we won't be installing the latest version as tensorflow has no support for Python 3.11:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671552357928/xJMxUDzcy.png align="center")

Once you click on that, it will bring you to a new screen where you will have to scroll down to the bottom and select the correct installer.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671397617443/9wTOSqdGd.PNG align="center")

We will always select the Windows installer (64-bit) marked as recommended, the download should be less than 30MB.

Once downloaded, double-click on it to start the installation.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671552728317/gzEGav0VC.png align="center")

**Note:** Please make sure that you check the bottom left box that says "Add python.exe to PATH", this way Python will be accessible from any console and will make your life easier.

Then just click on install to complete the installation.

In order to check if the installation has been successful, open a terminal (I recommend PowerShell but the normal console will work just fine) by searching either PowerShell or cmd into the Windows search bar:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671396889173/FabCyCNrH.PNG align="center")

Then, once on the terminal write python and press enter, you should be see something similar to the next image:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671397897661/bD0Yvb5uk.PNG align="center")

That is the Python command line, we will go in deeper in the following lessons. If you forgot to check the "Add python.exe to PATH" checkbox on the installer you will see an error. Just relaunch the installer checking the box this time around :)

Now, we need to install a couple of python libraries, first of all, exit the Python command line by writing "exit()" (with no quotes) and pressing enter, then write the command "pip install virtualenv":

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671398205523/lDy9-dY1x.PNG align="center")

Now we will create our virtual environment. This environment will hold all the installed Python packages, make sure you are in a directory you want to be in (by default the terminal opens on your user's folder) and type "virtualenv mlpills":

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671398277800/ipYDC6zih.PNG align="center")

**Note:** Here "mlpills" is used as the name of the environment, we will be using that environment for the rest of the tutorials, feel free to use any other name for your environment if you want, but I will be referring it as "mlpills" on all tutorials.

Then you need to actually activate the environment with the command ".\\mlpills\\Scripts\\activate":

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671398599473/QUHgwo5KU.PNG align="center")

You will see that on the left of the command line, the name of the environment will be between parenthesis, which means that any Python package that we install will only be available on that environment.

Now we just need to install the rest of the libraries with "pip3 install tensorflow keras numpy pandas":

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1671398770359/LhbqbF_a5.PNG align="center")

This will download and install all the libraries that we will be using in the following tutorials :D