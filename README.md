# AEA Ocean-End-To-End

## Intro

This agent is responsible for doing a full demo of the main Ocean functionalities.
The heavy lifting for this use-case is done by the `eightballer/ocean:0.1.0` skill, protocol and connection. 

Once the agent is up & running, it creates the pool & deploys algorithm that will be
available for submitting a Compute-to-Data job. In the end, the results from 
the algorithm will be downloaded using Ocean stack.


## Dependencies
- make
- python & pip
- pipenv

To run this project you need to go through the following steps:

1. Clone and head to repo

```
git clone git@gitlab.com:8ball030/oceanend2end.git
cd oceanend2end || exit
```

2. Make a new pipenv and install the necessary python dependencies
```
make new_env
make install_env
```

3. Checkout the new environment 
```
pipenv shell
```

4. Run the AEA

Manually
```
cd src/ocean_end_2_end || exit
aea -s run
```
or through make

```
make run_app
```

### Example running docs

1. clone repo
2. setup a new environment
   - make new_env
   - make 
3. in project directory:
```bash
 pipenv shell # if you haven't already
 mkdocs serve
```
Visit http://127.0.0.1:8000/


### Components

- gitlab ci
    - The ci contains the basic configuration required to launch a launch a gitlab ci

- Dockerfile
    - Basic Dockerfile which installs deps and launchs the app

- makefile
    - lints
        - isort
        - black
        - code clean
- pre-commit hooks for the build process

- scripts
    - app.py launcher for debugging and launching docker process

- Pipfile

- gitignore
- docker ignore
- .env file
- docs

### Dev Tools
setup pre-commit hooks
```
make install_hooks
```

lint, format, and sense check code
```
make lint
```

run tests

```
make tests
```

