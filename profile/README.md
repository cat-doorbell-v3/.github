## Overview 
This is my attempt to fit the Cat Doorbell onto a single microcontroller, namely the [ESP32-S3-EYE (v2.2)](https://github.com/espressif/esp-who/blob/master/docs/en/get-started/ESP32-S3-EYE_Getting_Started_Guide.md). My efforts so far have been largely based on Tensorflow.  But it is proving to be a steep learning curve for microcontroller implementations.  I've started looking at [EMLearn](https://github.com/emlearn/emlearn) as an alternative.

### Repos
There are 2 repos currently in this organization

#### 1. cat-doorbell-v3-cat-sound-model-creation
[This](https://github.com/cat-doorbell-v3/cat-doorbell-v3-cat-sound-model-creation) repo consists of attempts by me to create a `meow` model.  It is largely a bust. The models, when loaded, didn't work. I'll probably archive the repo eventually.

#### 2. cat-doorbell-v3-esp32-s3-eye-audio-test
[This](https://github.com/cat-doorbell-v3/cat-doorbell-v3-esp32-s3-eye-audio-test) repo is really a copy of [this](https://github.com/espressif/esp-tflite-micro/tree/master/examples/micro_speech) micro speech sample code.  It does compile, but does not correctly identify a `meow` yet.  Lately, I incorporated EMLearn-generated C code into it. It doesn't work yet. 


### Other Repos
Because of issues mentioned above with model creation, and on the advice of someone at Espressif, I turned to another approach for model creation using the [TFLite-Micro repo](https://github.com/tensorflow/tflite-micro).

[This](https://github.com/gamename/tflite-micro-fork) is my fork of tflite-micro repository. The main file of interest is [here](https://github.com/gamename/tflite-micro-fork/blob/main/tensorflow/lite/micro/examples/micro_speech/train/meow_train.py). It is an extract of the Google Colab notebook found [here](https://github.com/gamename/tflite-micro-fork/blob/main/tensorflow/lite/micro/examples/micro_speech/train/train_micro_speech_model.ipynb). Rather than use a notebook, I decided to just create a stand-alone python script. The models created by this process are small, but they don't work when added to the `cat-doorbell-v3-esp32-s3-eye-audio-test` test (see above).

