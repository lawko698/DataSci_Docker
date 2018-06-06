FROM lawko698/docker/base

#pip install
RUN pip install pandas scikit-learn numpy scipy jupyter seaborn

# exporing port 8888
EXPOSE 8888

RUN mkdir /notebook/
WORKDIR /notebook/
#Share folder to host computer
VOLUME /notebook

# Running jupyter notebook
# --NotebookApp.token='mynotebook' is the password
#CMD jupyter notebook --no-browser --ip 0.0.0.0 --port 8888 /notebooks
CMD ["jupyter","notebook","--no-browser","--ip=0.0.0.0","--allow-root","--port 8888", "--notebook-dir=/notebooks","--NotebookApp.token='mynotebook'"]
