# flask-hello-world

A simple Flask hello world application.

## Requirements

- [Python3.8](https://www.python.org/downloads/release/python-380/)

## Create the project

Create a project folder and create a virtual environment and activate it.

```bash
mkdir flask-hello-world && cd $_
python -m venv .venv --python=python3.8
source .venv/bin/activate
```

## Install Flask

First create a file to save dependencies (only Flask dependency in this case).  
The must common name for this file is `requirements.txt`, so:

```bash
touch requirements.txt
```

Now you need to define your dependencies, and the file looks like this:

```txt
flask==1.1.2
```

You can check Flask releases in: [https://github.com/pallets/flask/releases](https://github.com/pallets/flask/releases).  
To install it, you just to need run:

```bash
pip install -r requirements.txt
```

Now, you can check installed dependencies (Flask and its dependencies).

```bash
pip freeze
```

And the output should be like this:

```bash
click==7.1.2
Flask==1.1.2
itsdangerous==1.1.0
Jinja2==2.11.2
MarkupSafe==1.1.1
Werkzeug==1.0.1
```

## Create a Hello World app

Create a main file call `main.py` (The name does not matter, it could be another).

```bash
touch main.py
```

And then put the next code:

```python
from flask import Flask

app = Flask(__name__)


@app.route('/')
def hello():
  return 'Hello world with Flask'
```

## Run your new app

To run your app, first you need to set a environment variable called `FLASK_APP`  
and its value is the name of your file where your app is (`main.py` in this case).

```bash
export FLASK_APP=main.py
```

Check the env var:

```bash
echo $FLASK_APP
$ main.py
```

And then you can run your app:

```bash
flask run
```

And it outputs something like:

```bash
* Serving Flask app "main.py"
* Environment: production
  WARNING: This is a development server. Do not use it in a production deployment.
  Use a production WSGI server instead.
* Debug mode: off
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```

Now you can send a request to your app:

```bash
curl http://127.0.0.1:5000/
```

The output should be like:

```bash
Hello world with Flask
```

To stop your new app, just press `CTRL + c`

## License

[MIT.](./LICENSE) Copyright (c)