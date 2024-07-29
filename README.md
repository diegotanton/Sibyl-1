Setup:

Anaconda path: ~/Users/diegotanton/opt/anaconda3
Project path: ~/Users/diegotanton/Documents/Python

mkdir Sibyl-1
cd Sibyl-1
conda create --name sibyl-1 python=3.12.4
conda activate sibyl-1
conda install ipykernel
python -m ipykernel install --user --name=sibyl-1 --display-name="Python (sibyl-1)"
conda install pip
pip install <packages>
conda list