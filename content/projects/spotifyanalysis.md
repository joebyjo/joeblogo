---
title: Spotify Analysis
date: 2025-07-22
description: Turning Spotify data into insights and analyzing music trends through code
tags:
  - python
  - jupyter
  - data
github: https://github.com/joebyjo/Spotify-Audio-Feature-Analysis
cover: /images/projects/spotifyanalysis/26449239E29FB4812964D76806984D54.png
draft: false
---
# Exploring Music Through Data: Spotify Audio Feature Analysis

## Introduction

Music is often described as emotional and subjective, but beneath that subjectivity lies a rich layer of measurable data. Platforms like **Spotify** analyze tracks using detailed audio features such as _danceability_, _energy_, and _valence_, offering a unique opportunity to study music from a data-driven perspective.

This project, _Spotify Audio Feature Analysis_, was designed to explore how these characteristics vary across genres, popularity levels, and time. By combining publicly available datasets from **Kaggle** with additional metadata retrieved via the Spotify Web API, the goal was to uncover patterns in how music evolves and what defines different styles of sound.

Built entirely in **Python** using tools like **pandas**, **matplotlib**, and **seaborn**, the project demonstrates how data analysis can transform raw music data into meaningful insights.

---

## Core Features

### Large-Scale Music Dataset Analysis

The project analyzes over **21,000 tracks**, combining:

- Track metadata (artist, genre, popularity, duration)
- Audio features (danceability, energy, valence, tempo, etc.)

This scale enables more reliable insights into trends across genres and time.

---

### Enriched Data via Spotify API

To enhance the dataset, a custom script using the Spotify Web API (via **Spotipy**) was developed to fetch **release dates**.

This addition made it possible to:
- Track how music characteristics evolve over time
- Compare older vs modern music trends

---

### Interactive Exploratory Data Analysis

Using a **Jupyter Notebook**, the project provides:

- Visualizations of feature distributions
- Genre-based comparisons
- Correlation analysis between audio features

This interactive setup allows for **iterative exploration and deeper insights**.

---

### Genre & Feature Insights

The analysis focuses on questions like:

- What makes a genre “high energy” or “danceable”?
- How does _valence_ (musical positivity) vary across genres?
- Do more popular songs share common characteristics?

These insights bridge the gap between **technical metrics and human perception of music**.

---

### Trend Analysis Over Time

With release date data integrated, the project explores:

- Shifts in musical energy and tempo across years
- Changes in genre popularity
- Evolution of emotional tone in music

---

## Datasets

Two primary datasets form the foundation:

- `spotify_track_metadata.csv` - track-level metadata
- `spotify_track_audio_features.csv` - detailed audio metrics

These datasets are merged and cleaned using **pandas** for consistency and usability.

---

### Data Enrichment Pipeline

A custom Python script integrates with the Spotify Web API:

- Authenticated using API credentials
- Fetches missing release date data
- Appends enriched data back into the dataset

This step ensures the dataset is both **complete and analysis-ready**.

---

### Analysis

The core analysis is performed in a **Jupyter Notebook**, enabling:
- Step-by-step exploration
- Inline visualizations
- Rapid iteration on hypotheses

---

### Visualization
Data is visualized using:

- **matplotlib** for foundational plots
- **seaborn** for enhanced statistical graphics

These tools help transform numerical data into **intuitive visual insights**.

---
## Pictures

![D2C4B2A825B07D19D7F2DECBAD5BCB11.png](/images/projects/spotifyanalysis/D2C4B2A825B07D19D7F2DECBAD5BCB11.png)
![6B2D07C920E415C50D9C7CF1E97B4F41.png](/images/projects/spotifyanalysis/6B2D07C920E415C50D9C7CF1E97B4F41.png)
![3924860C63EF01BDBB979C984227DAC2.png](/images/projects/spotifyanalysis/3924860C63EF01BDBB979C984227DAC2.png)

---

Spotify Audio Feature Analysis highlights how data can uncover patterns in something as subjective as music.

By combining structured datasets with API enrichment and exploratory analysis, the project demonstrates:

- How musical characteristics evolve over time
- What defines different genres at a quantitative level
- The relationship between audio features and popularity
