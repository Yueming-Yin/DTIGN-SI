# DTIGN-SI
Supporting Information of paper entitiled "Advancing Bioactivity Prediction through Molecular Docking and Self-Attention: The Drug-Target Interaction Graph Neural Network (DTIGN)" under review in the IEEE Journal of Biomedical and Health Informatics.

- This work is under consideration for a Singapore patent under Singapore provisional patent application number 10202400124Q. All rights reserved by Kong Wai-Kin Adams (adamskong@ntu.edu.sg), Yin Yueming (yueming.yin@ntu.edu.sg), Mu Yuguang (ygmu@ntu.edu.sg) and Li Hoi Yeung (hyli@ntu.edu.sg).

- Results and auxiliary codes are provided in the corresponding folders and annotated in the notebooks. The main codes of our invention are reserved.

# Requirements
- Anaconda
- Pytorch
- Jupyter
- GPU with CUDA

# Get Started With A New Conda Virtual Environment
## Anaconda Installation
For installing anaconda on your OS, please refer to [Anaconda Installation](https://docs.anaconda.com/free/anaconda/install/).

Once the anaconda is properly installed, one can create a new virtual environment by entering the following command in terminal:
```bash
conda create rdkit python=3.6 -c rdkit -n rdkit
conda activate rdkit
```
- Note that `python=3.6` is adopted due to its good compatibility with a wide range of packages in our projects. One can try other versions if no compatibility issues occur.

## Pytorch Installation
For installing pytorch to a certain version, please refer to [Pytorch Installation](https://pytorch.org/get-started/locally/) or [Early Versions](https://pytorch.org/get-started/previous-versions/).

Here, we provide our command of install `pytorch-cuda=11.6` with anaconda in terminal:
```bash
conda install pytorch torchvision torchaudio pytorch-cuda=11.6 -c pytorch -c nvidia
```
- Note that the version of `pytorch-cuda=11.6` should be consistent with your CUDA version, choose suitable commond according to your CUDA version from [here](https://pytorch.org/get-started/previous-versions/).

## Jupyter Installation
For installing and configuring jupyter, please refer to [Jupyter Installation](https://jupyter.org/install) and [Jupyter Configuration](https://jupyter-server.readthedocs.io/en/latest/users/configuration.html).

Here, we provide our commands of installing and configuring jupyter with conda:
```bash
conda install jupyter notebook
jupyter notebook --generate-config
ipython
>>> from notebook.auth import passwd
>>> passwd()
(enter your passwords)
(conform your passwords)
Output: [your password key]
```

Then, open your generated jupyter_notebook_config.py file (usually in the '/home/.jupyter' directory) to add the following commands:
```python
c.NotebookApp.ip = '*'
c.NotebookApp.port = [port id]
c.NotebookApp.open_browser = False
c.NotebookApp.allow_remote_access = True
c.NotebookApp.password = [your password key]
c.NotebookApp.notebook_dir = [your default workdir]
```

To start jupyter notebook, please enter this commond in the terminal:
```bash
jupyter notebook
```
Then, one can access jupyter notebook at [your server's ip]:[port id].

## Package Installation
One can install environmental packages as the following commands in terminal:
```bash
conda install matplotlib tensorboardx tensorboard seaborn
conda install -c anaconda scikit-learn
pip install hyperopt
conda install pyg -c pyg
conda install -c conda-forge multicore-tsne
pip install retry
conda install -c schrodinger pymol
conda install -c conda-forge openbabel
pip install torch-geometric, torch-sparse, torch-scatter
```
For the installation of additional deep graph learning (dgl) package, please refer to [DGL Installation](https://www.dgl.ai/pages/start.html).
In our case, the installation command in terminal is:
```bash
pip install dgl-cu116 dglgo -f https://data.dgl.ai/wheels/repo.html
```