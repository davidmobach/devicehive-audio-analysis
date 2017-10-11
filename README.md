# Devicehive Audio Analysis
Audio classification feature demo

## Disclaimer
This project was written and tested on python 3.5\
It should work on any python 3.\*\
No guaranties for python 2.\*

## Installation
* Get a copy of this repo
* Install system packages
```bash
sudo apt-get install libportaudio2 portaudio19-dev libpulse-dev
```
* Install python requirements
```bash
pip install -r requirements.txt
```
_Note 'libpulse-dev' should be installed only for PulseAudio based devices. 'pyaduio', 'libportaudio2' and 'portaudio19-dev' should be installed on other devices, for example alsa capable._

* Download and extract saved models to source directory
```bash
wget https://s3.amazonaws.com/audioanalysis/models.tar.gz
tar -xzf models.tar.gz
```

## Running
To process prerecorded wav file run
```bash
python parse_file.py path_to_your_file.wav
```
_Note file should have 16000 rate_

To capture and process audio from mic run
```bash
python capture.py
```
It will capture and process 5 seconds long samples in cycle.\
To get info about parameters run
```bash
python capture.py --help
```

## Useful info
To train classification model next resources have been used:
* [Google AudioSet](https://research.google.com/audioset/)
* [YouTube-8M model](https://github.com/google/youtube-8m)
* [Tensorflow vggish model](https://github.com/tensorflow/models/tree/master/research/audioset)

You can try to train YouTube-8m model with more steps/samples to get more accuracy.