# Beating Montezuma's Revenge
This repository is a fork of the PAAC algorithm presented in [Efficient Parallel Methods for Deep Reinforcement Learning](https://arxiv.org/abs/1705.04862).

## Todos
- [ ] July 5th Wed, 6:10-7:10pm:
	* [ ] [play Montezuma's Revenge yourself](http://www.free80sarcade.com/2600_Montezumas_Revenge.php) 
	* [ ] train any algorithm of your choice on Montezuma's Revenge and share results (testing environment shared here)
	* [ ] (optional) read [NLP-based solution to MZ](https://arxiv.org/pdf/1704.05539v1.pdf)
	* [ ] (optional) read [why MZ is hard](https://arxiv.org/pdf/1604.00289.pdf)
- [ ] By July 15th Sat, 2-4pm:
	* [ ] Hoyeop Kim: [Count-Based Exploration 2017](http://arxiv.org/abs/1703.01310v2)
	* [ ] Sangjin Park: [Hierarchical RL](https://arxiv.org/abs/1604.06057v2)
	* [ ] DH: [FeUdal Networks](https://arxiv.org/abs/1703.01161v1)
	* [ ] HG: [UNREAL](https://arxiv.org/pdf/1611.05397.pdf)
- By July 20th:
	* [ ] (optional) [Feature Control as Intrinsic Motivation](https://arxiv.org/abs/1705.06769v1) 
	* [ ] (optional) [Evolution Strategies](https://arxiv.org/pdf/1703.03864.pdf) 	
	* [ ] (optional) [Count-Based Exploration 2016](https://arxiv.org/pdf/1606.01868v2.pdf)
	* [ ] (optional) [Micro-Objective Learning](https://arxiv.org/pdf/1703.03864.pdf) 
	* [ ] (optional) [Human Checkpoint Replay](https://arxiv.org/abs/1607.05077v1) 
- By July 27th:

- By Aug 3rd: 
- By Aug 10th
	* [ ] publish results (play video, blogpost)

## Goals
- number of rooms/level explored:
	* [ ] level 2+, 20+ rooms
	* state-of-the-art: [19 rooms & 1 level](https://www.youtube.com/watch?v=jMDhb-Toii8)
- score:
	* [ ] 3500+
	* state-of-the-art#1: [3500](https://gym.openai.com/envs/MontezumaRevenge-v0)

## Models

## Resources
### RL algorithms practice
- https://github.com/dennybritz/reinforcement-learning

### slides
- https://www.slideshare.net/sotetsukoyamada/montezumas-revenge-nips2016
- https://www.slideshare.net/ItsukaraIitsuka/drl-challenge-on-montezumas-revenge

### [papers](http://www.arxiv-sanity.com/search?q=montezuma%27s+revenge)
- Intrinsic Motivation: https://arxiv.org/pdf/1606.01868.pdf
- Hierarchical RL: https://arxiv.org/pdf/1611.05397.pdf
- Reinforcement learning with unsupervised auxiliary tasks(unreal): https://arxiv.org/pdf/1611.05397.pdf
- FeUdal Networks for Hierarchical Reinforcement Learning: https://arxiv.org/abs/1703.01161v1
- attention
- ES Evolution strategies: https://arxiv.org/pdf/1703.03864.pdf 
- option critic...

### other readings
- https://www.reddit.com/r/MachineLearning/comments/45fa9o/why_montezuma_revenge_doesnt_work_in_deepmind/
- https://news.ycombinator.com/item?id=11862027

### implementation
- https://gist.github.com/Itsukara/5d9e3bc6163ee8202d33b7bc48ec6da1
- https://github.com/EthanMacdonald/h-DQN
- https://github.com/steveKapturowski/tensorflow-rl

## Runing via docker (recommended)
1. Follow the instructions to install [nvidia-docker](https://github.com/NVIDIA/nvidia-docker/)
2. Clone this repository
3. Run the container with ```nvidia-docker run -it -v <absolute-path>/paac:/root/paac -p 6006:6006 alfredvc/tf1-ale```.

A CPU version of the docker container is also provided and can be run with ```docker run -it -v <absolute-path>/paac:/root/paac -p 6006:6006 alfredvc/tf1-ale:cpu```.
When running on the CPU pass the device flag ```-d '/cpu:0'``` to the training script.

## Runing locally
Requirements
* Python 3.4+
* TensorFlow 1.0+
* [Arcade-Learning-Environment](https://github.com/mgbellemare/Arcade-Learning-Environment)
* cython (pip3 package)
* scikit-image (pip3 package)
* python3-tk

## Training the agent
To train an agent to play, for example, pong run
* ```python3 train.py -g pong -df logs/```

For pong, the agent will begin to learn after about 5 million frames, and will learn an optimal policy after about 15 million frames.

Training can be stopped, for example by using Ctrl+c, and then resumed again by running ```python3 train.py -g pong -df logs/```.

On a setup with an [Intel i7-4790k](http://ark.intel.com/products/80807/Intel-Core-i7-4790K-Processor-8M-Cache-up-to-4_40-GHz) CPU and an [Nvidia GTX 980 Ti](http://www.geforce.com/hardware/desktop-gpus/geforce-gtx-980-ti) GPU with default settings, you can expect around 3000 timesteps (global steps) per second.
Training for 80 million timesteps requires under 8 hours.

Qbert

![qbert learning graph](readme_files/qbert_learning_graph.png "Qbert")

### Visualizing training
1. Open a new terminal
2. Attach to the running docker container with ```docker exec -it CONTAINER_NAME bash```
3. Run ```tensorboard --logdir=<absolute-path>/paac/logs/tf```.
4. In your browser navigate to localhost:6006/

If running locally, skip step 2.

## Testing the agent
To test the performance of a trained agent run ```python3 test.py -f logs/ -tc 5```
Output:
```
Performed 5 tests for seaquest.
Mean: 1704.00
Min: 1680.00
Max: 1720.00
Std: 14.97
```

### Generating gifs
Gifs can be generated from stored network weights, for example a gif of the agent playing breakout can be generated with
```
python3 test.py -f pretrained/breakout/ -gn breakout
```
This may take a few minutes.

## Pretrained models
Pretrained models for some games can be found [here](pretrained).
These models can be used as starting points for training on the same game, other games, or to generate gifs.

## Adapting the code
This codebase was designed to be easily modified to new environments and new neural network architectures.

### Adapting to a new environment
The codebase currently contains a single environment, namely ```atari_emulator.py```. To train on a new environment, simply 
create a new class that inherits from ```BaseEnvironment``` and modify ```environment_creator.py``` to create an instance of your new environment.

### Adapting to new neural network architectures
The codebase contains currently two neural network architectures, the architecture used in [Playing Atari with Deep Reinforcement Learning](https://arxiv.org/abs/1312.5602), and the architecture from [Human-level control through deep reinforcement learning](https://www.nature.com/nature/journal/v518/n7540/full/nature14236.html). Both adapted to an actor-critic algorithm.
To create a new architecture follow the pattern demonstrated in ```NatureNetwork``` and ```NIPSNetwork```.
Then create a new class that inherits from both the ```PolicyVNetwork``` and```YourNetwork```. For example:  ```NewArchitecturePolicyVNetwork(PolicyVNetwork, YourNetwork)```. Then use this class in ```train.py```.

## Disclaimer
The code in this repository is _not_ the code used to generate the results from the paper, but should give similar results.
Some changes have been made:
* Gradient clipping default value changed from 40.0 to 3.0.
* Entropy regularization constant default changed from 0.01 to 0.02.
* Using OpenAI Gym results in an increase in training time of 33%. This is because converting the image from RGB to Grayscale in python is slow.


