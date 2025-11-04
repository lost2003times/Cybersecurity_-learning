___
```
pip install virtualenv
# or
sudo apt install python3-virtualenv

mkdir virtual-demo
cd virtual-demo
python3 -m venv env
source env/bin/activate

#working with python
pip install pwntools
pip freeze | less  #to check the python installs and use "q" to exit the list

deactivate # to exit the virtual environment
```