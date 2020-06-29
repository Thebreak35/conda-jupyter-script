# Conda

## For first installation

*Remote machine*

Run these following commands.

- `mkdir notebook-root`
- `cd notebook-root`
- Create a conda environment `conda create -n my-env-1`
- Activate the conda environment `conda activate my-env-1`
- Install Jupyter notebook `conda install -c conda-forge notebook`
- Setup password for notebook `jupyter notebook password`
- run Jupyter notebook `nohup jupyter notebook --no-browser --port=8888 & > nohup.out`

*Local machine*
- Run this following command `ssh -N -L localhost:8889:localhost:8888 your-remote-user@your-remote-machine`
- Open your web browser and type a URL `localhost:8889`
You need the password you created from previous step to login.

## Install other libraries

You need to ssh into remote machine.

`ssh your-remote-user@your-remote-machine`

*Remote machine*

- Activate the conda environment `conda activate my-env-1`
- Check for packages `conda list` or `pip list`
- You can install libraries via [conda](https://anaconda.org/anaconda/repo) `conda install lib-name` or [pip](https://pypi.org/) `pip install lib-name`
- You can install a specific version of library `conda install lib-name==1.0.1` or `pip install lib-name==1.0.1`
- You can install libraries from a specific channel `conda install -c conda-forge lib-name` (see [Conda channels](https://docs.conda.io/projects/conda/en/latest/user-guide/concepts/channels.html), [conda-forge](https://anaconda.org/conda-forge/repo) )

## Running a Jupyter notebook from remote server

If you completed the instructions from ## For the first installation. Jupyter notebook process should be running in backgroud. You can skip into ### Step 2

#### - Step 1: Run this following command from remote machine

ssh into remote machine then run Jupyter notebook `nohup jupyter notebook --no-browser --port=8888 & > nohup.out`

#### - Step 2: Forward port

The Jupyter notebook is running at port `8888`. You'll forward this to port `8889` *of your local machine* so you can listen it and run it from your browser.

Run this following command on your local machine.

`ssh -N -L localhost:8889:localhost:8888 your-remote-user@10.204.162.42`

#### - Step 3: Open Jupyter notebook

Open your web browser with this url `localhost:8889`

You'll need token from your remote machine to fill the blank form.

## Exit

Press `Ctrl + C` in command line to terminates.