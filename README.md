# Introduction
## Background

# Research objective and Hypothesis

# Data set and Exploration
## Data acquisition
## Data preprocessing
## Exploratory data analysis (EDA)

# Kmeans clustering implementation (methodology)

# Results

# Conclusion


# Welcome to Moosic

Moosic is a little start up that creates curated playlists done by music experts and specialists in old and new trends. Users can subscribe to their website and listen to these playlists through their preferred Music App (be it Spotify, Apple Music, Youtube Music…). They love the fact that their playlists have a personal touch, and that each playlist encapsulates a certain “mood” or “style”.

But business is scaling up fast and the music experts are slow in creating new playlists. Our mission is to use Data Science to add a degree of automatisation to the creation of playlists.
We use a dataset that has been collected from the Spotify API and contains the audio features (tempo, energy, danceability…) for a few thousand songs, and use a basic clustering algorithm such as K-Means to divide the dataset into a few clusters (which will become playlists).

Some of the members of the team are skeptical about these audio features being able to capture the actual “mood” of a song: they feel this is something very subjective that only a human can judge. Others are hopeful that a solution that incorporates Data Science can be even better and create connections between songs that might feel unexpected at first glance, but that ultimately make sense.

First we will have an initial prototype. The playlists don’t have to be perfect, because we are in the beginning of a lengthy process and a couple of assessments will have to be made:

* Are Spotify’s audio features able to identify “similar songs”, as defined by humanly detectable criteria? When you listen to two rock ballads, two operas or two drum & bass songs, you identify them as similar songs. Are these similarities detectable using the audio features from Spotify?
* Is K-Means a good method to create playlists? Would you stick with this algorithm moving forward, or explore other methods to create playlists?

# The data

The data that will be used in order to group songs are Spotify’s audio features. The playlists that will emerge from the clustering algorithm that we will apply are going to be completely determined by whatever information these audio features capture from a song.

There are some features which are measures that are well established musical properties (key, mode, tempo…) while others have been created by Spotify’s team of Data Science and Sound Engineering (danceability, energy, valence…). Below are the descriptions provided by Spotify about their audio features.

It is important to understand the data that is available and get a feeling for what it is measuring. Because if we were to measure something absurd like the length of the song’s name and include it into the algorithm, it would group songs with short names together, and it is highly likely this similarity would make no sense to a human listening to those short-named songs.

**acousticness** (float):
A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic. >= 0, <= 1.

**danceability** (float):
Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable.

**energy** (float):
Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy.

**instrumentalness** (float):
Predicts whether a track contains no vocals. "Ooh" and "aah" sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly "vocal". The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0.

**key** (integer):
The key the track is in. Integers map to pitches using standard [Nesta CMS](https://en.wikipedia.org/wiki/Pitch_class "Pitch Class notation"). E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on.

**liveness** (float):
Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live.

**loudness** (float):
The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typically range between -60 and 0 db.

**mode** (integer)
Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.

**speechiness** (float)
Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.

**tempo** (float):
The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration.

**time_signature** (integer):
An estimated time signature. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure). The time signature ranges from 3 to 7 indicating time signatures of "3/4", to "7/4". >= 3, <= 7.
track_href

**valence** (float):
A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry). >= 0, <= 1.

# How a computer differentiates songs from one another.

It is is calculated using linear algebra. That is simply calculating the distances between songs. It’s the same as plotting the songs on a graph and measuring how far apart they are.


# Data acquisition and methodology

# Exploratory Data Analysis (EDA)

