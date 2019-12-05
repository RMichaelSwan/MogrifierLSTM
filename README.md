# Mogrifier LSTM

This repository implements an LSTM from scratch in PyTorch (allowing PyTorch to handle the backpropagation step) and then attempts to replicate the [Mogrifier LSTM paper](https://arxiv.org/abs/1909.01792). The code can be run locally or in Google Colaboratory.

*Note on Mogrifier results: I was not able to replicate the Mogrifier LSTM results cited in the paper or even get notably better performance compared to a regular LSTM. Perhaps with a larger dataset, more training time, better network architecture, or better hyperparameter tuning this could be achieved. My own code is slower than optimized versions of LSTMs, so one improvement that could be made is to bolt the Mogrifier implementation onto an existing optimized implementation of the LSTM cell. The Mogrifier LSTM paper claimed they would release their own code, but this has yet to happen (paper was released in September 2019). When that code is available, it should be at https://github.com/deepmind/lamb .*

## Local Install

Recommended you use Python `3.7`.
You will need to make sure that your virtualenv setup is of the correct version of python.
We will be using *PyTorch*.

Please see below for executing a virtual environment.

```shell
cd MogrifierLSTM
pip3 install virtualenv # If you didn't install it
virtualenv -p $(which python3) ./venv_lstm
source ./venv_lstm/bin/activate

# Install dependencies
pip3 install -r requirements.txt

# View the notebook

# Deactivate the virtual environment when you are done
deactivate
```

### Working with IPython Notebook

To view the notebook, simply run the following command to start an ipython kernel.

```shell
# add your virtual environment to jupyter notebook
python -m ipykernel install --user --name=venv_lstm

# port is only needed if you want to work on more than one notebook
jupyter notebook --port=<your_port>

```

and then work on the `MogrifierLSTM.ipynb` notebook.
Check the python environment you are using on the top right corner.
If the name of environment doesn't match, change it to your virtual environment in "Kernel>Change kernel".

## Cloud Install (Google Colaboratory)

1. Head over to [Google Colab](https://colab.research.google.com/). It is recommended that you switch to a GPU notebook as things will usually run a little faster that way. There are instructions for this on the colaboratory site.
2. Download the .ipynb file in this repository
3. Upload that file to Google Colabatory and run from there!

**Note: Google Colaboratory has time limits for their systems, so you may not be able to fully train the Mogrifier LSTM on their system without some special effort.**
