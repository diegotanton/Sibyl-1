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
pip list
pip freeze > requirements.txt
touch README.md
brew install git
git init
touch .gitignore

Create repo on Github and download PAT
open -e ~/.bash_profile
export GITHUB_TOKEN=<PAT>
source ~/.bash_profile
git config --global http.https://github.com/.extraheader "AUTHORIZATION: bearer $GITHUB_TOKEN"

git remote add origin https://github.com/diegotanton/Sibyl-1.git
git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main

