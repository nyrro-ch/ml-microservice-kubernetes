[![nyrro-ch](https://circleci.com/gh/nyrro-ch/ml-microservice-kubernetes.svg?style=svg)](<LINK>)

## Project Overview

In this project, you will apply the skills you have acquired in this course to operationalize a Machine Learning Microservice API. 

You are given a pre-trained, `sklearn` model that has been trained to predict housing prices in Boston according to several features, such as average rooms in a home and data about highway access, teacher-to-pupil ratios, and so on. You can read more about the data, which was initially taken from Kaggle, on [the data source site](https://www.kaggle.com/c/boston-housing). This project tests your ability to operationalize a Python flask app—in a provided file, `app.py`—that serves out predictions (inference) about housing prices through API calls. This project could be extended to any pre-trained machine learning model, such as those for image recognition and data labeling.

---

## 1. Setup the Environment

* Review `Makefile`
* Create a virtualenv with Python 3.7 and activate it. Refer to this link for help on specifying the Python version in the virtualenv. 
```bash
python3 -m pip install --user virtualenv
# You should have Python 3.7 available in your host. 
# Check the Python path using `which python3`
# Use a command similar to this one:
python3 -m virtualenv --python=<path-to-Python3.7> .devops
source .devops/bin/activate
```
* Run `make install` to install the necessary dependencies

### Running `app.py`

1. Standalone:  `python app.py`
2. Run in Docker:  `./run_docker.sh`
3. Run in Kubernetes:  `./run_kubernetes.sh`

### Kubernetes Steps

* Setup and Configure Docker locally
* Setup and Configure Kubernetes locally
* Create Flask app in Container
* Run via kubectl

## Files overview

* `.circleci`: configuration for circleci CI/CD
* `model_data`
* `output_txt_files`: Example output from the app
* `Dockerfile`: To create docker container 
* `Makefile`: Instructions to install and run the app
* `app.py`: Main application file
* `make_predictions.sh`: Run after app is running to create a prediction
* `requirements.txt`: Python dependecies to install
* `run_docker.sh`: Build docker image and start a container
* `run_kubernetes.sh`: Create kubernetes and forward port
* `upload_docker.sh`: Upload builded docker image to docker hub.
