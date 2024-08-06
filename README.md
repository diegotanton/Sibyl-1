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


# Strategy

Historical event detection through semantic clusterings of past headlines for company
    Stock price in relation to past events -> indicator of significance
    New updates on past events should be judged as positive or negative by GPT in relation to event information
        Can even look for supplemental information on significant events
    Relevance of new headlines to significant past events
    Ex: Event in the past triggered negative stock price reaction. Negative development on the event (as judged by GPT) should result in
    similar negative stock price reaction, and might be weighted differently than regular headlines
    Coverage of event as number of headlines
    Indicators of event as distribution of publishers (small first, then big)
Perform price analysis of embeddings vs. GPTs vs. non-OpenAI chatbots
Get rid of these: "S&amp;P"
Did stock change happen before the headline?
    Feature for this
Publisher "relevance": number of times appearing across all stock headlines
Publisher "impact": publishers with most impact on stock prices
Publisher "actionability": the speed at which RSS feed picks up on publisher (useful for implementation)
Type of headline coding through semantic clustering -> model feature
10K form assessment of risk factors -> generation of dependency RSS feeds
Market cap
Financial metrics on company
Analyst ratings on company
Macroeconomic events as monitored by RSS feeds
Company sector (judged by semantic clustering of company descriptions and labeling)
Significant movements in competitor stock prices
Significant movements in other sector stock prices
Singificant movements in other indices
Time series features like seasonality and autocorrelation
Volatility of stock within the hour
Volume of stock within the hour
Other external data sources
Starting time of interval (9:30 - 10:30am vs. 2:30 - 3:30pm will have different trading volumes / volatility)