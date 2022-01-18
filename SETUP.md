# Setup Qt for Python development

# Python 3.10 installation

## Windows 10

```
winget install python3 -l C:\Python\Python3.10
```

## Ubuntu 20.04

Ensure you have python 3.10

```
sudo add-apt-repository ppa:deadsnakes/ppa -y
sudo apt-get update
sudo apt-get install python3.10-full python3.10-venv -y
```

If you are on WSL2 you will need to install the following

```
sudo apt-get install build-essential x11-apps x11-common libxkbcommon-x11-0 \
                     libgl1-mesa-dev libxcb1-dev -y

```


## Example Dev Setup

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

## PySide6 - Python for Qt

Normally we would manage the setup of PySide, i.e. Python for Qt through the dependency management system (either `requirements.txt` or the `install_requires` argument to `setup` in `setup.py`). For this example we will directly install it as follows.

It is important to ensure the virtual environment is activated.

```
which python3
```

The above command should output something like this

```
/home/basu/code/custom/qt-for-py-01/venv/bin/python3
```

where the path should be in the directory you created.

Let install PySide6

```
pip install pyside6
```

To check that PySide installed, run the following. It should output two lines with version information.

```
python3 -c "import PySide6.QtCore; print(PySide6.__version__); print(PySide6.QtCore.__version__)"
```
