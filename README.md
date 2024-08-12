## Requirements
It is recommended to run this project on a GPU.

Before running the project, ensure you have the following packages installed:
PlantTraitPrediction.ipynb has a cell which installs the packages for you

- Python 3.10.14 or later
- [PyTorch](https://pytorch.org/get-started/locally/)
- [Lightning](https://lightning.ai/docs/fabric/stable/installation.html)
- [NumPy](https://numpy.org/install/)
- [Pandas](https://pandas.pydata.org/docs/getting_started/install.html)
- [Matplotlib](https://matplotlib.org/stable/users/installing/index.html)
- [Seaborn](https://seaborn.pydata.org/installing.html)
- [Pillow](https://python-pillow.org/)
- [scikit-learn](https://scikit-learn.org/stable/install.html)
- [torchvision](https://pytorch.org/vision/stable/index.html)
- [tqdm](https://tqdm.github.io/)
- [argparse](https://docs.python.org/3/library/argparse.html) (standard library)
- [urllib](https://docs.python.org/3/library/urllib.html) (standard library)

# Steps to Run the Project

**PlantTraitPrediction.ipynb** contains all the necessary scripts to run the project.

**Note:** 
You will need to download a `kaggle.json` file and upload it when prompted.
This is necessary to download the training data from kaggle.

As an alternative, you can also paste in a folder called 'data' which contains all the data needed for the project. The first 7 cells can be skipped in this case

## Instructions

1. **Upload `kaggle.json`** when prompted in the Jupyter file.
2. **Run scripts** to download data from Kaggle.
3. **Run the rest of the cells** to perform the regression task.

## Expected Runtimes (Assuming this is run on a L4 GPU)

- **Generating DINO Embeddings:** 8 minutes
- **Training Autogluon Models:** 30-40 minutes (400 seconds limit set per trait)

## Hardware Information

The following code was developed and tested on Vertex AI provided by the Google Cloud Platform.

- **GPU Type:** NVIDIA L4
- **Machine Type:** g2-standard-8 (8 vCPU, 4 core, 32 GB Memory)


## Note

The runtime is highly dependent on the type of machine the code is run on, Autogluon auto detects GPUs and optimizes runtime.

I noticed that the quality of DINO embeddings also depends on the type of machine, so this may affect the final R2 Score.

Testing with high time limit on Autogluon produces better results. My top result on kaggle was produced after 5 hours of total runtime!
The limit is set to 400 seconds in this notebook to produce a similar result (≈ 0.46) with a more bearable runtime.
