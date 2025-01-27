# VeraDemo - Blab-a-Gag (Django-Python)

### Notice

This project is intentionally vulnerable! It contains known vulnerabilities and security errors in its code and is meant as an example project for software security scanning tools such as Veracode. Please do not report vulnerabilities in this project; the odds are they’re there on purpose :) .

## About

Blab-a-Gag is a fairly simple forum type application which allows:

- Users can post a one-liner joke.
- Users can follow the jokes of other users or not (listen or ignore).
- Users can comment on other users messages (heckle).

### URLs

- `/feed` shows the jokes/heckles that are relevant to the current user.
- `/blabbers` shows a list of all other users and allows the current user to listen or ignore.
- `/profile` allows the current user to modify their profile.
- `/login` allows you to log in to your account
- `/register` allows you to create a new user account
- `/tools` shows a tools page that shows a fortune or lets you ping a host.
- `/reset` allows the user to reset the database

## Run Docker image (Easiest Method)

If you don't already have Docker this is a prerequisite.

### Download Docker

Visit [docker desktop](https://www.docker.com/products/docker-desktop/) and download your compatible version.  Follow installation instructions.  Open the Docker app.

### Use pre-built Docker image

Run in a Terminal:

    docker run --rm -p 8000:8000 --name verademo-python ssessions/verademo-python

Navigate to: [http://127.0.0.1:8000](http://127.0.0.1:8000).

Then register as a new user and add some feeds!

### Build your own Docker image

Follow the instructions below for cloning and running locally, `cd` into the verademo-python directory and run in a Terminal:

	docker build -t verademo-python .
	docker run --rm -p 8000:8000 --name verademo-python verademo-python
	
Navigate to: [http://127.0.0.1:8000](http://127.0.0.1:8000).

Then register as a new user and add some feeds!

## Run locally without Docker (Linux/Mac)

To run the program locally without using docker:

Prerequisite: Python 3.12.3

To check Python version: `python --version` or `python3 --version`

Clone the repository in terminal:

    git clone https://github.com/veracode-demo-labs/verademo-python.git
    cd verademo-python
Download dependencies and start the server!

    python -m venv env
    source env/bin/activate
    pip install -r requirements.txt
    python manage.py runserver
Navigate to: [http://127.0.0.1:8000](http://127.0.0.1:8000).

To be able to use the fortune feature in tools (Linux exclusive), run this before running the server:

    apt-get install -y fortune-mod

## Run locally without Docker (Windows)

To run the program locally without using docker:

Prerequisite: Python 3.12.3

To check Python version: `python --version` or `python3 --version`

Open Windows PowerShell and clone the repository:

    git clone https://github.com/veracode-demo-labs/verademo-python.git
    cd verademo-python
Download dependencies and start the server! (Try running console commands with `python3` if `python` isn't found)

    python -m venv env
    env\Scripts\activate
    pip install -r requirements.txt
    python manage.py runserver
Navigate to: [http://127.0.0.1:8000](http://127.0.0.1:8000).

## Exploitation Demos

See the [DEMO_NOTES](DEMO_NOTES.md) file for information on using this application with the various Veracode scan types.

Also see the `docs` folder for in-depth explanations of the various exploits exposed in this application.


## Technologies Used

- Django (Version 4.2.13)
- sqlite3 (Supported by Django)
