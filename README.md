# GESTDB_3

## Create environment
```bash
python -m venv venv
venv\Scripts\activate
```

## Install requirements
```bash
python.exe -m pip install --upgrade pip
pip install -r requirements.txt
```

## Compile requirements
```bash
pip install pip-tools==7.4.1
pip-compile requirements.in
```