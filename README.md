Tensorpack is a neural network training interface based on TensorFlow.

## Documentation link:
[Object Oriented Reinforcement Learning DOCUMENTATION](https://github.com/sajalgoyal113/tensorpack/blob/master/Documentation.pdf)

[Presentation](https://drive.google.com/open?id=11Bfo5fHkLcv6_BwWmd1Qr9Oz8u6O0ItCpde-2YCHqkk)

## How to do a local setup on UBUNTU:
First Activate the virtual environment using [this link](https://www.tensorflow.org/install/pip)
Then, 
```
$ pip3 install tensorflow==1.15.0
```

```
$ git clone https://github.com/sajalgoyal113/tensorpack
$ cd tensorpack/examples/DeepQNetwork
$ pip install 'gym[atari]'
$ wget https://github.com/openai/atari-py/raw/gdb/atari_py/atari_roms/breakout.bin
```

```
pip install --upgrade git+https://github.com/tensorpack/tensorpack.git
```
# Train the model
```
$ ./DQN.py --env breakout.bin --algo DQN
```
# Play the trained model ( here model-2000000 is pretrained model for 80 epochs)
```
$ ./DQN.py --env breakout.bin --task play --load ./train_log/DQN-breakout/model-2000000
```

Dependencies:

+ Python 3.3+.
+ Python bindings for OpenCV. (Optional, but required by a lot of features)
+ TensorFlow ≥ 1.5, < 2. (Not required if you only want to use `tensorpack.dataflow` alone as a data processing library)
