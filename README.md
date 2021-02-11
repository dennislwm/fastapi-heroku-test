# fastapi-heroku-test

![Heroku Status](https://heroku-badge.herokuapp.com/?app=fastapi-heroku-test)

fastapi-heroku-test starter project.

---
## Table of Contents
- [fastapi-heroku-test](#fastapi-heroku-test)
  - [Table of Contents](#table-of-contents)
  - [Project](#project)
    - [Project Structure](#project-structure)
  - [Usage](#usage)
    - [TL;DR](#tldr)
    - [Download and Install Heroku CLI](#download-and-install-heroku-cli)
    - [Create Heroku App](#create-heroku-app)
    - [Create Procfile](#create-procfile)
    - [Deploy App](#deploy-app)
    - [Live App](#live-app)
    - [Python Version](#python-version)
  - [Heroku Service Plan](#heroku-service-plan)
    - [References](#references)
    - [Reach Out!](#reach-out)

---
## Project
**fastapi-heroku-test** was a personal project to:

* host a Python FastAPI web server on Heroku

---
### Project Structure
```
root/
  |- .gitignore
  |- app.json
  |- Procfile
  |- README.md
  |- requirements.txt
  +- src/
     |- __init__.py
     |- main.py
```

---
## Usage

### TL;DR

Deploy app to Heroku easily.

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy/?template=https://github.com/dennislwm/fastapi-heroku-test)

### Download and Install Heroku CLI

The first step is [downloading and installing the Heroku CLI](https://devcenter.heroku.com/articles/heroku-cli). Then we can login into Heroku from the command line with:

```
$ heroku login
```

### Create Heroku App

Once we're logged in, we can create a new app on Heroku by running: ```Heroku create {app-name}```. Heroku apps are in a global namespace, therefore you need to choose a unique name for your application.

```
$ heroku create fastapi-heroku-test
```

Note: You can specify the optional parameter ```--buildpack heroku/python```. However, by default Heroku detects the language automatically.

### Create Procfile

Create a ```Procfile``` in our project directory. The file is used to declare the commands run by the app on Heroku.

The ```Procfile``` defines processes using the following format ```{process-type}: {command}```. Since our application contains a web server, the process type is web.

```
web: uvicorn src.main:app --host=0.0.0.0 --port=${PORT:-5000}
```

### Deploy App

Make sure you commit and push your source code first. Then run this from the top level of the tree.

```
$ heroku git:remote -a fastapi-heroku-test
$ git push heroku master
```

Note: If deploying your app from a subfolder, use the command:

```
$ git subtree push --prefix {subfolder} heroku master
```

### Live App

Your app is now live at [https://fastapi-heroku-test.herokuapp.com](https://fastapi-heroku-test.herokuapp.com).

### Python Version

If you're running a Python application that requires a specific runtime, you can add a ```runtime.txt``` file to your root directory that declares the exact version number to use.

```
python-3.7.5
```

---
## Heroku Service Plan

Heroku has different [service plans](https://devcenter.heroku.com/articles/heroku-postgres-plans). In this project, we will use the hobby-dev plan, which is free and serves the purpose we need it for.

---
### References
- None

---
### Reach Out!

Please consider giving this repository a star on GitHub.
