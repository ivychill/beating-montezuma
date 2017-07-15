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
	* [ ] HG: [UNREAL](https://arxiv.org/abs/1611.05397]
- By July 20th:
	* [ ] (optional) [Feature Control as Intrinsic Motivation](https://arxiv.org/abs/1705.06769v1) 
	* [ ] (optional) [Evolution Strategies](https://arxiv.org/pdf/1703.03864.pdf) 	
	* [ ] (optional) [Count-Based Exploration 2016](https://arxiv.org/pdf/1606.01868v2.pdf)
	* [ ] (optional) [Micro-Objective Learning](https://arxiv.org/pdf/1703.03864.pdf) 
	* [ ] (optional) [Human Checkpoint Replay](https://arxiv.org/abs/1607.05077v1) 
	* [ ] (optional) [Surprised-based Intrinsic Motivation](https://arxiv.org/pdf/1703.01732.pdf)
	* [ ] (optional) [VIME: Variational Information Maximizing Exploration](https://arxiv.org/abs/1605.09674)
	* [ ] (optional) [Incentivizing Exploration With Deep Predictive Models](https://arxiv.org/abs/1507.00814)
	* [ ] (optional) [Q-Prop: Sample-Efficient Policy Gradient with An Off-Policy Critic](https://arxiv.org/abs/1611.02247)
	* [ ] (optional) [The Reactor: A Sample-Efficient Actor-Critic Architecture](https://arxiv.org/pdf/1704.04651.pdf)


- By July 27th:

- By Aug 3rd: 
- By Aug 10th
	* [ ] publish results (play video, blogpost)

## Goals
- number of rooms/level explored:
	* [ ] level 2+, 20+ rooms
	* current record#1: [19 rooms & 1 level](https://www.youtube.com/watch?v=jMDhb-Toii8)
- score:
	* [ ] 3500+
	* current record#1: [3500](https://gym.openai.com/envs/MontezumaRevenge-v0)
	* current record#2: The paper suggests this is probably the best trial and the agent wasn't able to reproduce this level of result easily. [6600](https://www.youtube.com/watch?v=EzQwCmGtEHs&feature=youtu.be) 

## Montezuma's Revenge
Montezuma's Revenge is an early example of the Metroidvania genre.[1] The player controls a character called Panama Joe (a.k.a. Pedro), moving him from room to room in the labyrinthine underground pyramid of the 16th century Aztec temple of emperor Montezuma II, filled with enemies, obstacles, traps, and dangers. The objective is to score points by gathering jewels and killing enemies along the way. Panama Joe must find keys to open doors, collect and use equipment such as torches, swords, amulets, etc., and avoid or defeat the challenges in his path. Obstacles are laser gates, conveyor belts, disappearing floors and fire pits.[2][3][4]

Movement is achieved by jumping, running, sliding down poles, and climbing chains and ladders. Enemies are skulls, snakes, and spiders. A further complication arises in the bottom-most floors of each pyramid, which must be played in total darkness unless a torch is found.

The pyramid is nine floors deep, not counting the topmost entry room that the player drops into at the start of each level, and has 99 rooms to explore. The goal is to reach the Treasure Chamber, whose entrance is in the center room of the lowest level. After jumping in here, the player has a short time to jump from one chain to another and pick up as many jewels as possible. However, jumping onto a fireman's pole will immediately take the player to the next level; when time runs out, the player is automatically thrown onto the pole.

There are nine difficulty levels in all. Though the basic layout of the pyramid remains the same from one level to the next, small changes in details force the player to rethink strategy. These changes include:

Blocking or opening up certain paths (by adding/removing walls or ladders)
Adding enemies and obstacles
Rearrangement of items
More dark rooms and fewer torches (in level 9, the entire pyramid is dark and there are no torches)
Enemies that do not disappear after they kill Panama Joe (starting with level 5)
The player can reach only the left half of the pyramid in level 1, and only the right half in level 2. Starting with level 3, the entire pyramid is open for exploration.

[source](https://en.wikipedia.org/wiki/Montezuma%27s_Revenge_(video_game))

### Items
- Hammer: If Joe touches a hammer, the killer creatures get harmless for a short time and are displayed in grey.
- Jewel: Joe gets 1000 points for each jewel collected.
- Key: Only the key with the same colour fits into each door. Their colours are red, dark blue and bright blue.
- Sword: If Joe has a sword, he can eliminate a killer creature when touching it.
- Torch: The torch lights the dark rooms.


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
- https://arxiv.org/abs/1703.01732

### other readings
- exploration: https://medium.com/emergent-future/simple-reinforcement-learning-with-tensorflow-part-7-action-selection-strategies-for-exploration-d3a97b7cceaf
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
If you use Anaconda, you can try ```conda env create -f environment.yml```.

Requirements
* Python 3.4+
* TensorFlow 1.0+ (choose a GPU version, if you have GPU)
* [Arcade-Learning-Environment](https://github.com/mgbellemare/Arcade-Learning-Environment)
* cython (pip3 package)
* scikit-image (pip3 package)
* python3-tk


## Training the agent
To train an agent to play, for example, pong run
* ```python3 train.py -g <game-name> -df logs/<game-name>/```

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
```
python3 test.py -f logs/<game-name>/ -gn breakout
```
This may take a few minutes.


### ideas
- segmentation -> objects detection
- attention model
- transfer learning
- life -> give larger penalty for losing a life