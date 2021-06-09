FROM pangeo/base-image:master

ENV NB_USER=jovyan \
    CONDA_ENV=notebook
ENV NB_PYTHON_PREFIX=${CONDA_DIR}/envs/${CONDA_ENV}

USER ${NB_USER}

RUN ${NB_PYTHON_PREFIX}/bin/jupyter labextension install @jupyterlab/geojson-extension; \
    ${NB_PYTHON_PREFIX}/bin/jupyter labextension install keplergl-jupyter; \
    ${NB_PYTHON_PREFIX}/bin/jupyter labextension install @jupyterlab/git; \
    ${NB_PYTHON_PREFIX}/bin/jupyter server extension enable --py jupyterlab_s3_browser --sys-prefix; \
    ${NB_PYTHON_PREFIX}/bin/jupyter server extension enable --py jupyterlab_git --sys-prefix;
