# Setup:

# Anaconda path: ~/Users/diegotanton/opt/anaconda3
# Project path: ~/Users/diegotanton/Documents/Python

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

# Generate SSH keys
ssh-keygen -t ed25519 -C "diegotanton@gmail.com"
# Save in default file
eval "$(ssh-agent -s)"
touch ~/.ssh/config
open -e ~/.ssh/config
# Paste the following:
Host *
  AddKeysToAgent yes
  UseKeychain yes
  IdentityFile ~/.ssh/id_ed25519
#
ssh-add -K ~/.ssh/id_ed25519
pbcopy < ~/.ssh/id_ed25519.pub
# Paste publish SSH key to GitHub
git remote set-url origin git@github.com:diegotanton/Sibyl-1.git
ssh -T git@github.com

# Setup git repo
git branch -M main
git add .
git commit -m "Initial commit"
git push -u origin main

# Update git repo
git add .
git commit -m "Updates"
git push