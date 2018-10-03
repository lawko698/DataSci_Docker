#base image
FROM python:3.6

# updating respoitory
RUN pip install pip --upgrade
# install packages
RUN pip install pandas scikit-learn numpy scipy jupyter seaborn lightgbm matplotlib xgboost

RUN mkdir /notebook
WORKDIR /notebook/

#exposing port 8888
EXPOSE 8888

CMD ["jupyter", "notebook", "--port=8888", "--no-browser", "--ip=0.0.0.0", "--allow-root"]
