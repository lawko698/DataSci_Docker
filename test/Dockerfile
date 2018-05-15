
#base image
FROM ubuntu:latest

# updating respoitory
RUN apt-get update && apt-get -y upgrade

RUN mkdir -p /tensorflow/models
RUN apt-get install -y git python-pip
RUN pip install pip --upgrade
RUN apt-get install -y build-essential python-dev
RUN apt-get install -y python python-distribute python-pip

#pip install
RUN pip install tensorflow
RUN pip install pandas scikit-learn numpy scipy jupyter seaborn matplotlib

RUN git clone https://github.com/tensorflow/models.git /tensorflow/models

RUN export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim

# expoing port 8888
EXPOSE 8888

RUN mkdir /notebooks
WORKDIR /notebooks
#Share folder to host computer
VOLUME /notebooks

# Running jupyter notebook
# --NotebookApp.token='mynotebook' is the password
CMD ["jupyter","notebook","--no-browser","--ip=0.0.0.0","--allow-root","--port 8888", "--notebook-dir=/notebooks","--NotebookApp.token='mynotebook'"]

