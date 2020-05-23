![breakout](breakout.jpg)

[video demo](https://youtu.be/o21mddZtE5Y)

## Usage:

Install dependencies by `pip install 'gym[atari]'`.

### With ALE (paper's setting):

Download an [atari rom](https://github.com/openai/atari-py/tree/gdb/atari_py/atari_roms), e.g.:
```
wget https://github.com/openai/atari-py/raw/gdb/atari_py/atari_roms/breakout.bin
```

Start Training:
```
./DQN.py --env breakout.bin
# use `--algo` to select other DQN algorithms. See `-h` for more options.
```

Watch the agent play:
```
# Download pretrained models or use one you trained:
wget http://models.tensorpack.com/DeepQNetwork/DoubleDQN-breakout.bin.npz
./DQN.py --env breakout.bin --task play --load DoubleDQN-breakout.bin.npz
```

Evaluation of 50 episodes:
```
./DQN.py --env breakout.bin --task eval --load DoubleDQN-breakout.bin.npz
```

### With gym's Atari:

Install gym and atari_py. Use `--env BreakoutDeterministic-v4` instead of the ROM file.

## Performance
Claimed performance in the paper can be reproduced, on several games I've tested with.

![DQN](curve-breakout.png)

| Environment    | Avg Score | Download                                                                               |
|:---------------|:---------:|:--------------------------------------------------------------------------------------:|
| breakout.bin   | 465       | [:arrow_down:](http://models.tensorpack.com/DeepQNetwork/DoubleDQN-breakout.bin.npz)   |
| seaquest.bin   | 8686      | [:arrow_down:](http://models.tensorpack.com/DeepQNetwork/DoubleDQN-seaquest.bin.npz)   |
| ms_pacman.bin  | 3323      | [:arrow_down:](http://models.tensorpack.com/DeepQNetwork/DoubleDQN-ms_pacman.bin.npz)  |
| beam_rider.bin | 15835     | [:arrow_down:](http://models.tensorpack.com/DeepQNetwork/DoubleDQN-beam_rider.bin.npz) |

## Speed
On one GTX 1080Ti,
the ALE version took
__~2 hours__ of training to reach 21 (maximum) score on Pong,
__~10 hours__ of training to reach 400 score on Breakout.
It runs at 100 batches (6.4k trained frames, 400 seen frames, 1.6k game frames) per second on GTX 1080Ti.
This is likely the fastest open source TF implementation of DQN.

A3C code and models for Atari games in OpenAI Gym are released in [examples/A3C-Gym](../A3C-Gym)
