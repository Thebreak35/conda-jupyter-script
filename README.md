# Conda

## Installation

Run these following commands on remote machine

`conda create -n my-env-1`

Activate conda environment

`conda activate my-env-1`

Install Jupyter notebook

`conda install -c conda-forge notebook`

Check package after installation

`conda list`

---

## Running a Jupyter notebook from remote server

#### - Step 1: Run this following command from remote machine

`jupyter notebook --no-browser --port=8888`

#### - Step 2: Forward port

The Jupyter notebook is running at port `8888`. You'll forward this to port `8889` *of your local machine* so you can listen it and run it from your browser.

Run this following command on your local machine.

`ssh -N -L localhost:8889:localhost:8888 your-remote-user@10.204.162.42`

#### - Step 3: Open Jupyter notebook

Open your web browser with this url `localhost:8889`

You'll need token from your remote machine to fill the blank form.

## Exit

Press `Ctrl + C` in command line to terminates.