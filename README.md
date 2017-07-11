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
* TensorFlow 1.0+ (choose a GPU version, if you have GPU)
* [Arcade-Learning-Environment](https://github.com/mgbellemare/Arcade-Learning-Environment)
* cython (pip3 package)
* scikit-image (pip3 package)
* python3-tk

## Training the agent
To train an agent to play, for example, pong run
* ```python3 train.py -g pong -df logs/```

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
python3 test.py -f pretrained/breakout/ -gn breakout
```
This may take a few minutes.