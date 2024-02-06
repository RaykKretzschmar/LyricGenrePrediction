# LyricGenrePrediction
This project uses machine learning to predict the genre of lyrics. The model is trained on a dataset of <30,000 songs. Downsampling was used to balance the classes. The model is a finetuned version of 'distilbert-base-uncased' trained on the lyrics and the genre is predicted. The dataset contains the lyrics and the genre of the songs.

### Original Dataset
https://www.kaggle.com/datasets/joebeachcapital/30000-spotify-songs

### Data
The csv-files are not included in the repo due to the file size limit of GitHub.
If you want access to the files. Please send me an email: `kretzschmar.rayk@gmail.com`

### Architecture
I trained the model on an NVIDIA GeForce RTX 4070 Ti. The training took about 35 minutes per epoch. The model was trained for 12 epochs.
Training on Google Colab took about 1h 20min per epoch on their T4 GPU.

## Run the project
1. You need to have a Python environment able to run Jupyter notebooks. I recommend Python 3.10 since the project was developed and tested with this version. Newer versions can cause compatibility issues with PyTorch or other libraries.

2. You can install the required packages by running the first cell in each notebook or by running the following command in your terminal:
```
pip install -r requirements.txt
```

3. You'll need an API-Key from [Genius.com](https://docs.genius.com/) to download the lyrics. You can get one by signing up on their website. The API-Key should be stored in a file called `.env` in the root directory of the project like this:
```env
GENIUS_TOKEN=<your_api_key>
```

4. To do the data preprocessing, run the notebook [`01_DataPreprocessing.ipynb`](./01_DataPreprocessing.ipynb). This will create the `data.csv` file needed to train the model.

5. You can also load your own dataset and do the training directly without preprocessing the data. Just make sure that the dataset has the same structure as the `data.csv` file.
Structure of data.csv: 
```csv
playlist_genre,lyrics
```

6. To train the model, run the notebook [`02_TrainEval.ipynb`](./02_TrainEval.ipynb). The device used for training should be set automatically depending on the availability of a GPU or Apple Silicon. If you want to use a specific device, you can change the device. The model will be saved in the directory `genre_model`. Checkpoints will be saved in the directory `results`.

7. To analyze the model, run the notebook [`03_ModelAnalysis.ipynb`](./03_ModelAnalysis.ipynb). This will show the confusion matrix, confident scores and some additional analysis of the model and checkpoints.