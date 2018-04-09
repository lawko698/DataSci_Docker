
#base image
FROM ubuntu:latest

# updating respoitory
RUN apt-get update && apt-get -y upgrade
RUN apt-get install -y build-essential python-dev
RUN apt-get install -y python python-distribute python-pip
RUN pip install pip --upgrade

#pip install
RUN pip install pandas scikit-learn numpy scipy jupyter seaborn matplotlib

#xgboost
RUN git clone --depth 1 --recursive https://github.com/dmlc/xgboost.git && cd xgboost && \
	make && cd python-package && python setup.py install && \
	pip install lightgbm


# exporing port 8888
EXPOSE 8888

RUN mkdir /notebooks
WORKDIR /notebooks
#Share folder to host computer
VOLUME /notebooks


# Running jupyter notebook
# --NotebookApp.token='mynotebook' is the password
CMD ["jupyter","notebook","--no-browser","--ip=0.0.0.0","--allow-root","--port 8888", "--notebook-dir=/notebooks","--NotebookApp.token='mynotebook'"]
