# Install pip in Python < 3.6 on Big Sur
how to install pip in Python < 3.6 on macOS Big Sur and solve bagit issues
_____
I constantly run into issues with [bagit](https://github.com/LibraryOfCongress/bagit-python) on Python 3.9, where bagging runs in perpetuity and no checksum manifest files could be generated. In most cases, I need to force quit and kill the running commands. 

According to this [post](https://stackoverflow.com/questions/65869296/installing-pip-is-not-working-in-python-3-6/65871131#65871131), pip is no longer supported in Python < 3.6. Python 2.7 reached the end of its life on January 1st, 2020, and pip 21.0 also dropped support for Python 2.7 in January 2021.

To use pip install for bagit in older Python versions, run the following commands to first check python versions:

    python -V
    python3 -V
    
Use the following command to check whether pip is installed:

    python -m pip --version
    python3 -m pip --version

If pip is installed, it will says "pip X.Y.Z from .../site-packages/pip (python X.Y)". In Python > 3.6, pip can be installed with the following commands:  

    python get-pip.py   

pip is no longer supported in Python < 3.6. The following command install pip in Python 2.7 from https://bootstrap.pypa.io/pip/2.7/.

    curl -O https://bootstrap.pypa.io/pip/2.7/get-pip.py
    python get-pip.py  
    python -m pip install --upgrade "pip < 21.0"

For Python 2.6, install from https://bootstrap.pypa.io/pip/2.6/ <br>
For Python 3.2, install from https://bootstrap.pypa.io/pip/3.2/ <br>
For Python 3.3, install from https://bootstrap.pypa.io/pip/3.3/ <br>
For Python 3.4, install from https://bootstrap.pypa.io/pip/3.4/ <br>
For Python 3.5, install from https://bootstrap.pypa.io/pip/3.5/ <br>

Upgrade command for Python 3.4 is:

    python -m pip install --upgrade "pip < 21.1.2"

After install, run these two commands to check pip version and install bagit.

    python -m pip --version 
    python -m pip install bagit
