# Install pip in Python older than 3.6 on Big Sur
how to install pip in Python < 3.6 on macOS Big Sur and how to solve bagit issues
_____
I constantly run into issues with [bagit](https://github.com/LibraryOfCongress/bagit-python) in Python 3.9, where bagging runs in perpetuity and no checksum manifest files could be generated. In most cases, I need to force quit and kill the running commands. I haven't recorded at which Python 3 version, this became an issue. I start going back to use Python 2.7 for [bagit](https://github.com/LibraryOfCongress/bagit-python).

For people who already have [bagit](https://github.com/LibraryOfCongress/bagit-python) installed for older Python versions, this might not be an issue. But if you are preparing a new computer, you might encounter the same situation where pip can't be installed. According to this [post](https://stackoverflow.com/questions/65869296/installing-pip-is-not-working-in-python-3-6/65871131#65871131), pip is no longer supported in Python < 3.6. Python 2.7 reached the end of its life on January 1st, 2020, and pip 21.0 also dropped support for Python 2.7 in January 2021.

To use pip install for bagit in older Python versions, run the following commands to first check python versions:

    python -V
    python3 -V
    
Use the following commands to check whether pip is installed:

    python -m pip --version
    python3 -m pip --version

If pip is installed, it will say "pip X.Y.Z from .../site-packages/pip (python X.Y)". In Python > 3.6, pip can be installed with the following command:  

    python get-pip.py   

pip is no longer supported in Python < 3.6. The following commands install pip in Python 2.7 from https://bootstrap.pypa.io/pip/2.7/.

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
