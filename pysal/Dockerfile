FROM jupyter/scipy-notebook:307ad2bb5fce

LABEL maintainer="Serge Rey <sjsrey@gmail.com>"

RUN conda config --add channels conda-forge --force
RUN conda config --set channel_priority strict
RUN conda config --set safety_checks disabled
RUN conda install pysal=2.1 scikit-learn>=0.22

#---- Jupyter config ----

RUN echo "c.NotebookApp.default_url = '/lab'" \
 >> /home/$NB_USER/.jupyter/jupyter_notebook_config.py

# Switch back to jovyan to avoid accidental container runs as root
USER $NB_UID
