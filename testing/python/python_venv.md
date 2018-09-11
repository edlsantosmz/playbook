#
* By default all python packages are installes to a single directory on the system
* Virtual environments solve this by creating isolated python environment stha can be customized per project 
* Virtual environments are directories contianing links to the systems pythnon install and providng sub-directories afor installing aditionals python packages in that particular virtual environment
* The PATH envirnoment variable is updated to point to the virutal environment when that virutal environment si activated

# Python 2.7
* install virutalenv utility via `pip install virtualenv`
* Create a new virtual environment with the command `virtualenv <NameOfVirtualEnv`
* Activate your virtual envrioment bys ourcing the activate script  in the virtual environments bin directory (i.e. source ./<NameOfVirtualEnv>/binactivate
* Deactivate your virtual environment with the "deactivate" command
* Delete your virtual environemnt by deleting its directory



```
pip install virtualenv
virtualenv pytest_27_venv
source ./pytest_27_venv/bin/activate
pip install pytest
pytest
deactivate
pytest
```

# Setting up a pthon virtual environment in Python 3
* Python 3 comes wit a virtual environment module built-in called venv
* Virtualenv can also be used with the python 3 but venv is what's recommended by the python community as it is built-in to python3, creates smaller virtual environemnts an is extendable
* The only difference is the creation command
* To create a virtual environemnt with venv you run the command `python3 -m venv <VirtualEnvironment_Name>`

```
python3 -m venv pytest_3_venv
source pytest_3_venv/bin/activate
pip3 install pytest
pytest
deactivate
pytest
```

# Set up pytest in PyCharm


