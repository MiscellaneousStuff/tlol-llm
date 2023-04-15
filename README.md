# TLoL - Large Language Model Integration

## About

TLoL (Large Language Model) - League of Legends LLM Module (Integrates LLMs for Game Analysis and Game Playing)

## Directory Breakdown

- `llm.ipynb`: Initial LLM experiments on data

## Dataset

A brief description of datasets used for this project are listed below:

- `ESPORTSTMNT02-3080905(old).db`
  - context: League of Legends - Worlds 2022 Final (Game 5)
  - total files: 1
  - approx size: 403MB
  - map: Summoner's Rift
  - frames: 16,858 (~4.5 obs/sec * 2528.97 secs + many duplicate frames)
  - source: Bayes Esports (\*.rofl) + [TLoL-Scraper](https://github.com/MiscellaneousStuff/tlol-scrapera) (\*.db)
  - download: [Google Drive](https://drive.google.com/file/d/1kZchHUksTCOvpN_hJZ5iVvESF6Be5FPt/view?usp=sharing)

## Structure of .db files (Observations)

Each file is an SQLite3 database generated using TLoL-Scraper, which has scraped
the game objects from a live running Leauge of Legends replay. Each database contains
the following 4 tables:
- games (first table)
  - game_id  (Internal Riot Game ID, ignore this for Bayes Esports replays)
  - duration (Game Duration in seconds)
- champs/missiles/objects (remaining three tables)
  - game_id  (Internal Riot Game ID, ignore this for Bayes Esports replays)
  - time     (Game time in seconds)
  - obj_type ()
  - etc.     (Refer to [this](https://github.com/MiscellaneousStuff/tlol-py/blob/d7650dc6ff4c9f943a5da727698a21998d6e87e1/tlol/datasets/convertor.py)) for full specification