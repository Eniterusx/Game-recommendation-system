# Game recommendation system

## Table of contents
1. [Introduction](#introduction)
2. [Sources](#sources)
3. [Requirements](#requirements)
    - [General](#general)
    - [Data collection](#data-collection)
    - [Recommendation methods](#recommendation-methods)
4. [Installation](#installation)
5. [Usage](#usage)
    - [Data collection](#data-collection-1)
    - [Recommendation methods](#recommendation-methods-1)
<!-- 6. [Dataset](#dataset)
7. [Methodology](#methodology)
8. [Results](#results)
9. [Conclusion](#conclusion) -->

## Introduction
The aim of this work was to develop a computer game recommendation system that generates personalized recommendations based on user’s Steam data. For this purpose, a proprietary dataset was created using the public Steam API and techniques for parsing the source code of game websites to obtain additional information such as tags and ratings. Four recommendation methods were implemented, including approaches based on user similarity and game content, and then compared in terms of their effectiveness in providing correct recommendations. A [simple web application](https://game-recommendation-web.vercel.app/) ([source code](https://github.com/Eniterusx/Game-recommendation-website)) was also developed that allows users to obtain recommendations by providing a link to their Steam profile.

## Sources
- [Steam API](https://developer.valvesoftware.com/wiki/Steam_Web_API)
- [ALS algorithm](http://yifanhu.net/PUB/cf.pdf)

## Requirements

### General
- Python 3.10.13
- conda
- pandas
- tqdm

### Data collection
- dotenv
- requests
- pandas
- beautifulsoup4

### Recommendation methods
- matplotlib
- seaborn
- numpy
- sklearn
- scipy
- keras
- tensorflow
- implicit

## Installation

1. Clone the repository:
```shell
git clone https://github.com/Eniterusx/Game-recommendation-system
cd Game-recommendation-system
```

2. Create a conda environment and install the required packages:
```shell
conda env create -f requirements.yaml
conda activate game-rec
```

## Usage

### Data collection

<!-- actually the .env file is created, you just have to add the items -->
1. Go to the `data_collection` directory and create a `.env` file with the following content:
```shell
API_KEY=your_steam_api_key
STEAM_ID=your_steam_profile_id
```
The `API_KEY` is the Steam API key that you can get [here](https://steamcommunity.com/dev/apikey). The `STEAM_ID` is your steamID64, which can be found [here](https://steamid.io/lookup).

2. Run the `user_crawler.ipynb` for the desired amount of cycles to collect the data about users. The data will be saved in the `data` directory.

3. Run the `steam_tags_scraper.ipynb` to collect the tags of the games. The data will be saved in the `data` directory.

### Recommendation methods

Go into any of the recommendation methods jupyter notebooks and run the cells to see the results. Each notebook prepares the dataset, trains the model and evaluates it on every user in the dataset. Then it generates the recommendations for a random user and shows the results.