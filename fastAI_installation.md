# Installing fastAI work environment

Quick summary on how to setup the work environment for local development with machine learning.

## Installing miniconda (LINUX)

Download the relevent [miniconda installation here](https://docs.conda.io/en/latest/miniconda.html#linux-installers) for your specified OS.

NOTE: If you are developing on windows then Anaconda might be a better option.

You should be able to install the rest with the [conda.io instructions](https://conda.io/projects/conda/en/latest/user-guide/install/linux.html).

## Installing the fastAI Python Environment
NOTE: this will take a while since there are some large dependencies within this environment.

Miniconda install command.

```bash
conda install -c fastai -c pytorch fastai
```

Anaconda install command.

```bash
conda install -c fastai -c pytorch -c anaconda fastai gh anaconda
```

Then clone the fastAI github repository. MAke sure to run this command in the directory you wish to work in.

```bash
git clone https://github.com/fastai/fastai
```

It is recommended to look at this [free course on fastAI](https://course.fast.ai/) to explore how to use the tool and machine learning concepts. The [github repository](https://github.com/fastai/fastai) is also a great way to find out more about the tool.

## Testing

You should be able to validate the installation of the environment by running the unit tests in the fastAI repository with the following options:

```bash
cd /path/to/fastai
make test
```

Additional dependencies may need to be installed with pip for all the tests to pass.

```bash
pip install "sentencepiece<0.1.90" wandb tensorboard albumentations pydicom opencv-python scikit-image pyarrow kornia \
    catalyst captum neptune-cli
```

If everything is passing, then the installation is complete.
