FROM jupyter/minimal-notebook

ENV DATA_HOME /usr/src/data
WORKDIR /$DATA_HOME 

ADD requirements.txt ./
RUN pip install -r requirements.txt


