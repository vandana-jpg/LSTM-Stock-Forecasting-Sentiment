Step 1: Install Git (if not already)
Download from 
git-scm.com
 and verify:

bash
Collapse
Wrap
Copy
git --version
Step 2: Create the Repository on GitHub
Go to 
github.com
 → click "+" → New repository
Name it exactly:
LSTM-Stock-Forecasting-Sentiment
Set to Public
Do NOT check "Add README" (you'll create it locally)
Click Create repository
Copy the URL shown - e.g.
https://github.com/YOUR_USERNAME/LSTM-Stock-Forecasting-Sentiment.git
Step 3: Create the Folder Structure Locally
Open your terminal/command prompt and run:

bash
Collapse
Wrap
Copy
mkdir LSTM-Stock-Forecasting-Sentiment
cd LSTM-Stock-Forecasting-Sentiment

# Create all folders
mkdir -p data/sentiment_raw
mkdir -p models/aapl_savedmodel
mkdir -p models/googl_savedmodel
mkdir -p models/msft_savedmodel
mkdir -p models/nifty50_savedmodel
mkdir notebooks
mkdir -p src
mkdir -p results/plots
mkdir -p results/tables
Step 4: Create Placeholder Files
GitHub does not upload empty folders, so add a
.gitkeep
file inside each empty one:

bash
Collapse
Wrap
Copy
touch data/sentiment_raw/.gitkeep
touch models/aapl_savedmodel/.gitkeep
touch models/googl_savedmodel/.gitkeep
touch models/msft_savedmodel/.gitkeep
touch models/nifty50_savedmodel/.gitkeep
touch results/plots/.gitkeep
touch results/tables/.gitkeep
Then create your main files:

bash
Collapse
Wrap
Copy
touch data/download_data.py
touch notebooks/EDA_and_visualisation.ipynb
touch src/preprocess.py
touch src/sentiment.py
touch src/features.py
touch src/train.py
touch src/evaluate.py
touch src/app.py
touch requirements.txt
touch Dockerfile
touch README.md
Step 5: Create the .gitignore File
bash
Collapse
Wrap
Copy
touch .gitignore
Paste this inside
.gitignore
:

text
Collapse
Wrap
Copy
__pycache__/
*.pyc
.env
.DS_Store
data/*.csv
results/plots/*.png
*.h5
*.pkl
This prevents large/sensitive files from being uploaded.

Step 6: Create requirements.txt
Paste this inside
requirements.txt
- all libraries from your paper 1.1
+2 more
:

txt
Collapse
Wrap
Copy
tensorflow==2.12
numpy
pandas
scikit-learn
statsmodels
vaderSentiment
yfinance
scipy
matplotlib
seaborn
plotly
flask
Step 7: Initialize Git and Push to GitHub
bash
Collapse
Wrap
Copy
# Initialize git
git init

# Add all files
git add .

# First commit
git commit -m "Initial commit: Project structure, source code, and requirements"

# Set main branch
git branch -M main

# Connect to your GitHub repo (paste your URL here)
git remote add origin https://github.com/YOUR_USERNAME/LSTM-Stock-Forecasting-Sentiment.git

# Push everything
git push -u origin main
Step 8: Handle Large Model Files (Important)
Your
models/
folder contains TensorFlow SavedModels which may exceed GitHub's 100MB limit 1.4. Two options:

Option A - Git LFS (recommended):

bash
Collapse
Wrap
Copy
git lfs install
git lfs track "models/**"
git add .gitattributes
git commit -m "Track model weights with Git LFS"
git push
Option B - Google Drive link in README:
Add this line to your README:

Pre-trained model weights: [Download from Google Drive](YOUR_DRIVE_LINK)
Step 9: Verify Your Final Structure on GitHub
After pushing, your GitHub repo should look exactly like this:

text
Collapse
Wrap
Copy
text
Collapse
Wrap
Copy
LSTM-Stock-Forecasting-Sentiment/
├── data/
│   ├── download_data.py
│   └── sentiment_raw/
├── models/
│   ├── aapl_savedmodel/
│   ├── googl_savedmodel/
│   ├── msft_savedmodel/
│   └── nifty50_savedmodel/
├── notebooks/
│   └── EDA_and_visualisation.ipynb
├── src/
│   ├── preprocess.py
│   ├── sentiment.py
│   ├── features.py
│   ├── train.py
│   ├── evaluate.py
│   └── app.py
├── results/
│   ├── plots/
│   └── tables/
├── .gitignore
├── requirements.txt
├── Dockerfile
└── README.md
