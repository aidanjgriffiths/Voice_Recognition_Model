# Installing fastAI work environment with linux

Quick summary on how to setup the fastai work environment for local linux development with machine learning. For python development I highly recommend using linux.
If you must use windows then you will need to seek out different steps with the miniconda and environment installation.

## Installing miniconda

Download the relevent [miniconda installation here](https://docs.conda.io/en/latest/miniconda.html#linux-installers) for your specified OS.

NOTE: If you are developing on windows then Anaconda might be a better option.

You should be able to install the rest with the [conda.io instructions](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html).

## Installing the fastAI Python Environment

NOTE: this will take a while since there are some large dependencies within this environment.

First clone the fastAI github repository. Make sure to run this command in the directory you wish to work in.

```bash
git clone git@github.com:fastai/fastai.git
cd fastai/
```

Install the python dependencies in a virtual environment named fastai and use the fastai yaml file to point to the required dependencies.

```bash
conda env create -n fastai -f environment.yml
conda activate fastai
```

There are some additional dependencies needed for your environment, make sure your environment is activated before running the following commands:

```bash
# linux only, install jupyter for running notebooks locally
conda install jupyter

# this is a fastai tool that allows developers to develop libraries within jupyter.
pip install nbdev

# install repo paths for environment.
cd /path/to/fastai
pip install -e .
```

It is recommended to look at this [free course on fastAI](https://course.fast.ai/) to explore how to use the tool and machine learning concepts. The [github repository](https://github.com/fastai/fastai) is also a great way to find out more about the tool.

## Testing

You should be able to validate the installation of the environment by running the unit tests in the fastAI repository with the following options:

```bash
cd /path/to/fastai
make test
```

Additional dependencies may need to be installed with pip for all the tests to pass. Make sure your environment is activated before running the following command:

```bash
pip install "sentencepiece<0.1.90" wandb tensorboard albumentations pydicom opencv-python scikit-image pyarrow kornia \
    catalyst captum neptune-cli
```

If everything is passing, then the installation is complete.

## Running fastai Notebooks with Jupyter

Since we have installed jupyter in the previous steps we should be able to enter `jupyter notebook` into the command line to open our local jupyter instance. Jupyter will open in your default browser. If not then Jupyter supplies the following commands to manually enter into a web browser:
```bash
To access the notebook, open this file in a browser:
        file:///home/aidan/.local/share/jupyter/runtime/nbserver-35451-open.html
    Or copy and paste one of these URLs:
        http://localhost:8888/?token=ca4e70a259c8a10355cd628ef9f928a4d345ebc97b304b2a
     or http://127.0.0.1:8888/?token=ca4e70a259c8a10355cd628ef9f928a4d345ebc97b304b2a
```

If the following URL's still don't work please refer to this [troubleshooting guide](https://jupyter-notebook.readthedocs.io/en/stable/troubleshooting.html) if this isn't the case.
