# A Minimalist Dataset for Systematic Generalization of Perception, Syntax, and Semantics
Pytorch implementation for the baselines in [A Minimalist Dataset for Systematic Generalization of Perception, Syntax, and Semantics](https://hint-iclr.github.io/HINT/)

## Prerequisites
* Ubuntu 20.04
* Python 3.8
* NVIDIA TITAN RTX + CUDA 10.0
* PyTorch 1.7.0

## Getting started
1. Clone this repository and unzip the dataset:
```
git clone https://github.com/hint-iclr/HINT.git
cd HINT/data
tar -xvf dataset.tar.xz
```
2. Create an environment with all packages from `requirements.txt` installed (Note: please double check the CUDA version on your machine and install pytorch accordingly):
```
pip install -r requirements.txt
```

3. Create a Weights & Biases account and login 
```bash
wandb login
```

More information on setting up Weights & Biases can be found on
https://docs.wandb.com/quickstart.

## Usage
The code makes use of Weights &  Biases for experiment tracking. In the [sweeps](./sweeps/) directory, we provide sweep configurations for all experiments we have performed. The sweeps are officially meant for hyperparameter optimization, but we use them to run multiple configurations and seeds.

To reproduce our results, start a sweep for each of the YAML files in the [sweeps](./sweeps/) directory.


For example,run Transformer experiments with symbol inputs: 
```
./run_sweep.py sweeps/transformer.yaml --n_agent 3 --gpus=0,1,2
```

You can change the number of sweep agents and GPUs used, according to your computing resource.

More details on how to run W&B sweeps can be found at https://docs.wandb.com/sweeps/quickstart.

## Experiments
All experiments are shared via [Weights & Biases](https://wandb.ai/qli/HINT/reports/HINT-experimental-report--VmlldzoyMDgyOTM2)