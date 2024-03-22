# ML-Project-Team-9-MetaLearning

Team members: Ilia Zherebtsov, Rinat Prochii, Makar Korchagin, Nikita Burtsev, Folu Obidare

This repository contains the datasets and code needed to reproduce experiments from our project "Meta-learning for time series forecasting in application to ATM load time series".

# Project goal

The goal of the project was to use the meta-learning algorithm to predict the best suited model to predict time series. Picking a suitable model is time consuming and computationally expensive - especially with many choices of models and large number of time series to predict. So, our approach can save plenty of time.

## Requirements
In order to launch the project, you need to install or update the following packs:
- numpy (1.24.3 or newer);
- pandas (2.0.1 or newer);
- seaborn (0.13.2 or newer)
- tsfeatures (0.4.5 or newer)
- sklearn (1.4.0 or newer)
- catboost (1.2.3 or newer)

... or you can just copy and paste the following command to your terminal:
```
pip install numpy pandas seaborn tsfeatures scikit-learn catboost -U
```
## Results reproduction

The following project is separated into 5 files:
- `concatenate.ipynb`
- `preprocess.ipynb`
- `manual_feature_selection.ipynb`
- `train_test.ipynb`
- `expirements.ipynb`

In order to reproduce result, you should download the files, listed above and the `/data/` folder with the files: `local_global_res_13_12.csv` and `time_series.zip`. Make sure,  that both files are located in the `/data/` on your local machine.

The `.ipynb` files must be launched in the way, they listed above. In the following section theirs functions will be briefly described

### Preprocessing
Firstly, you need to launch `concatenate.ipynb` file. This file concatenate time series from `time_series.zip` archive into three data frames: `nn5.csv`, `danish_atm_daily.csv` and `mipt_alpha.csv`.

Secondly, you launch the  `preprocessing.ipynb` file. The following file remove outliers from the initial dataset, excludes correlated metrics and choose the best model for each time series, splitting the best dataset into `preprocessed_train.csv` and `preprocessed_test.csv` folds, the initial dataset is saved in `preprocessed_full.csv` file. 
Several figures from the paper report will be saved in the `/output/` folder.


### Feature extraction
After preprocessing finished, you run the `manual_feature_selction.ipynb` file, which extracts features from all the time series. The data frames with features for each time series are saved in the `/manual_features/` folder.

The next step is to combine the features with the preprocessed target values. For this, you need to run `train_test.ipynb`. This file concatenate the target values with the features for each time series. The final files are saved in the `/data/` folder with the following names: `ready_train.csv` and `ready_test.csv`

### Experiments reproduction
After preparing all the required files, you need to launch the `experiments.ipynb` file, which will provide you with the results, stated both in the presentation and the final report.

*Good luck and have a fun!*

