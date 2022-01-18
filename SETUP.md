# Setup Qt for Python development

# Python 3.10 installation

## Windows 10

Make sure you install [Python 3.10](https://www.python.org/downloads/).

Ensure you do a custom install, and have it added to the PATH, installing it for 
all users on your machine.


### Create Project

Open PowerShell and clone this project from GitHub to your machine.

```commandline
cd C:\code
git clone https://github.com/bmanc2000/qt-for-py-01.git
```

Now `cd` into the project directory
```commandline
cd C:\code\qt-for-py-01
```

### Virtual Environment

Now create the virtual environment. For python projects you should always work in a 
virtual environment for Python projects. It ensures that the system python remains 
untouched and uncorrupted. We can always recreate the virtual env and install the 
necessary tools and dependencies as needed.

You only need to this if you haven't already created the environment.

```commandline
python3.10 -m venv venv
```

**Activate**

To work in the repo and install dependencies, or run you scripts, you need to activate 
the repo virtual environment. You **need to do this everytime** you start the shell and start working.

```
.\venv\Scripts\activate
```


## Ubuntu 20.04 (WSL2 on Windows?)
TODO. Unfortunately we cannot do the Qt for Python GUI apps without WSL2 on Windows 11 yet.

<!--
Ensure you have python 3.10

```
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt-get update
sudo apt-get install python3.10-full python3.10-venv -y
```



### Example Dev Setup

Let's first create the directory for the project `qt-for-py-01`.

```
mkdir -p ~/code/qt-for-py-01
```

Now `cd` into the directory, and create the virtual environment. It's always better to work in a virtual environment for Python projects. This ensures that the system remains untouched and uncorruped. We can always recreate the virtual env and install the necessary tools and dependencies as needed.

```
cd ~/code/qt-for-py-01
python3.10 -m venv venv

# I create a symlink to make it simpler to activate
# the virtual env as needed.
ln -s venv/bin/activate
```

Before you work on your project, ALWAYS activate the virtual environment

```
cd ~/code/qt-for-py-01
source ./activate
```
-->

## PySide6 - Python for Qt

Normally we would manage the setup of PySide, i.e. Python for Qt through 
the dependency management system (either `requirements.txt` or the `install_requires` 
argument to `setup` in `setup.py`). For this example we will directly install it as follows.

First ensure the virtual environment is activated.
```
python -c "import sys; print(sys.executable)"
```

The above command should output something like this

```
C:\code\qt-for-py-01\venv\Scripts\python.exe
```
assuming you cloned the repo under `C:\code`.

Now let's install PySide6

```
pip install pyside6
```

To check that PySide installed, run the following. It should output two lines with version information.

```
python3 -c "import PySide6.QtCore; print(PySide6.__version__); print(PySide6.QtCore.__version__)"
```

Now we're ready to cook.