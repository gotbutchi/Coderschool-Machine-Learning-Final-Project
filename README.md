# Coderschool-Machine-Learning-Final-Project
Final Project about Tempo-aware Music Recommendation System

**RUN TO THE BEATS**
![](https://github.com/gotbutchi/Coderschool-Machine-Learning-Final-Project/blob/master/pic/theme.png)

# Tempo-aware Music Recommendation System

## Introduction: Domain Background

![](https://i.imgur.com/ZrS9pqM.png)

During workouts, many trainers try to match their runs and exercises to the beat of their music. The use of music and specifically tempo-matched music has been shown to affect running performance. Researches have shown that exercising at different intensities leads to different heart rates, which are proportional to a particular exercise intensity and sets off different processes in the muscles. Matching steady consistent beats for long endurance runs is therefore important because the different changes in tempo can affect a person’s rhythm.

[](https://i.imgur.com/IeummDd.png)

Modern song recommendation systems often make use of information retrieval methods, leveraging user listening patterns to make better recommendations. However, such systems are often greatly affected by biases in large-scale listening patterns, and fail to recognize the similarity between songs to help generate a synschronized playlist while considering the short-term user interests (matching the current beats per minute).

Recent developments in deep neural network and recurrent neural network architectures provide a means to train end-to-end models that can determine the ideal feature vector for the next song based on the previous sequence of songs, and thus recommending the playlist of songs with not just similar tempo, but also a good flow.

Research on this topic (my inspiration): https://www.frontiersin.org/articles/10.3389/fpsyg.2014.01361/full

## Problem Statement: Concept

![](https://i.imgur.com/SXuXRpY.png)

In the context of next-track music recommendation, one can try to determine a playlist continuation where all elements are generally a good fit for the current listening session . In contrast, one could however also try to make sure that also the transitions between the tracks are smooth or that the resulting playlist has certain characteristics, e.g., a continuous increase of the tempo.
A good playlist is more than a sequence of similar songs. Therefore, in this project, we are focusing on the second scenario, where the smooth transition between tracks is our main goal. In order to achieve this goal, it is important to pick the best next song, and 3 parameters will be used: Distance to the RNN output vector, Key similarity (using the Circle of Fifth), and Tempo similarity (Getting the user's HR by calling Fitbit API).

The system gets the bpm(beats per minute) of every song on your playlist and then detects your running/walking tempo from an API (fitbit) and suggests a playlist of smooth transition between each song with similar tempo (in your chosen range) for you. Ultimately, this system is structured in a way as to deliver **harmonic sequences of tunes** that meld into an hour of blissful listening.

## Solution Statement

To tackle this problem, the project needed to perform the following tasks:

1. Extract metadata about trendy/featured music playlists from Spotify to date.
2. Transform track metadata.
3. Train a sequence estimator that learns the traits and relationships of each playlist.
4. Get the heart rate of the user through Fitbit API
5. Create a playlist with similar tempo and key using the estimator and Spotify's recommendation API.
6. Post a playlist to Spotify.

## Final Application
Fitbit watch & the online application (web demo):
![](https://github.com/gotbutchi/Coderschool-Machine-Learning-Final-Project/blob/master/pic/demo.png)

Main page to get the user's HR:
![](https://github.com/gotbutchi/Coderschool-Machine-Learning-Final-Project/blob/master/pic/main.png)

Prediction page to find next tempo-similar song and create a playlist on Spotify:
![](https://github.com/gotbutchi/Coderschool-Machine-Learning-Final-Project/blob/master/pic/predic.png)

*Note: For the website I use the pre-designed theme by Creative Tim (https://github.com/creativetimofficial)*

## Helpful links
:::spoiler Links
Link to research papers:
1. https://arxiv.org/pdf/1802.08452.pdf
2. https://arxiv.org/pdf/1906.03870.pdf
3. https://cs224d.stanford.edu/reports/BalakrishnanDixit.pdf

4. http://www.apsipa.org/proceedings/2018/pdfs/0001010.pdf
5. https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0208702
6. https://www.audiolabs-erlangen.de/content/05-fau/professor/00-mueller/03-publications/2018_SchreiberMueller_TempoCNN_ISMIR_ePrint.pdf
7. https://www.audiolabs-erlangen.de/fau/professor/mueller/bookFMP
8. https://www.frontiersin.org/articles/10.3389/fams.2019.00044/full
9. http://ismir2009.ismir.net/proceedings/OS4-2.pdf
10. https://evazangerle.at/publication/somera-15/somera-15.pdf
11. https://web.stanford.edu/~jlmcc/papers/PDP/Chapter3.pdf
12. https://www.kdd.org/kdd2018/files/deep-learning-day/DLDay18_paper_27.pdf
13. https://machinelearningmastery.com/time-series-prediction-lstm-recurrent-neural-networks-python-keras/
14. https://www.stat.umn.edu/arc/yjpower.pdf
15. http://ismir2002.ismir.net/proceedings/03-SP02-1.pdf
16. https://mtosmt.org/issues/mto.07.13.3/mto.07.13.3.benadon.html

Useful links for understanding the concept:
1. http://mac.citi.sinica.edu.tw/~yang/teaching/lecture12_tempo_beat_rhythm.pdf
2. https://medium.com/@silvercloud438/how-i-taught-a-neural-network-to-understand-similarities-in-music-audio-d4fca54c1aed
3. http://arno.uvt.nl/show.cgi?fid=136352
4. https://nlml.github.io/neural-networks/detecting-bpm-neural-networks/
5. https://www.audiolabs-erlangen.de/resources/MIR/FMP/C7/C7S2_CENS.html
6. https://getsongbpm.com/tools/audio
7. http://karpathy.github.io/2015/05/21/rnn-effectiveness/
