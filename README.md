# LyricGenrePrediction
 This project uses machine learning to predict the genre of lyrics. The model is trained on a dataset of <30,000 songs. ### The dataset contains the lyrics and the genre of the songs. The model is trained on the lyrics and the genre is predicted. The model is finetuned version of 'distilbert-base-uncased'.

### Original Dataset
https://www.kaggle.com/datasets/joebeachcapital/30000-spotify-songs

### Data
The csv-files are not included in the repo due to the file size limit of GitHub.
If you want access to the files. Please send me an email: kretzschmar.rayk@gmail.com

### Architecture
I trained the model on an NVIDIA GeForce RTX 4070 Ti. The training took about 35 minutes per epoch. The model was trained for 12 epochs.
Training on Google Colab took about 1h 20min per epoch on their T4 GPU.

## Workflow to run the project
1. Clone the repository
```
git clone https://github.com/RaykKretzschmar/LyricGenrePrediction.git
```

2. Create a virtual environment with conda and activate it
```
conda create --name testenv python=3.10
conda activate testenv
```

3. Install the required packages
```
pip install -r requirements.txt
```