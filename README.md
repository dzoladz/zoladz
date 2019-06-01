OLD -> using PIPENV for COOL
===========================

Some preliminary documentation on setting up reports for the Consortium of Ohio Libraries

#### Setting Up COOL Automated Reporting
- Python3 will be used for scripting
- Utility server IP needs to be added for Sequoia DB access

#### Requests
- Add all cron jobs to `/etc/cron.d`

#### Using Virtual Environments
- Virtual Environments [virtualenv docs](http://docs.python-guide.org/en/latest/dev/virtualenvs/)

1. To create a virtual environment
```
virtualenv -p /usr/bin/python3 project_name
```

2. To activate the virtual environment, navigate to the `/project_name` directory and type 
```
source bin/activate
```

3. Install any packages required for the project while in the virtual environment
```
pip install psycopg2
```

4. To deactivate the environment, type
```
deactivate
```

#### Freezing the Virtual Environment

1. To see a list of packages in the environment, type:
```
pip list --format=columns
```

2. To create a list of required packages, along with the required version of the package, for the project in the standard requirements.txt file, type:
```
pip freeze > requirements.txt
```

3. If you need to recreate an environment using a requirements.txt file, type:
```
pip install -r requirements.txt
```

#### Bug with pyvenv3

1. Virtual environment must be created without Pip
```
pyvenv3 --without-pip project_name
```

2. Activate the virtual environment, navigate to the `/project_name` directory and type 
```
source bin/activate
```

3. Grab Pip manually and install
```
wget https://bootstrap.pypa.io/get-pip.py
python get-pip.py
```
