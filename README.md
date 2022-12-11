## CIFAR10 hyperlightspeedbench
Welcome to the hyperlightspeedbench CIFAR-10 (HLB-CIFAR10) repo.


### How to Run


`git clone https://github.com/tysam-code/hlb-CIFAR10 && cd hlb-CIFAR10 && python -m pip install -r requirements.txt && python main.py`


If you're curious, this code is generally Colab friendly and is built to appropriately reset state without having to reload the instance (in fact -- most of this was developed in Colab!)


### Main

Goals: 

* minimalistic 
* beginner-friendly 
* torch- and python-idiomatic 
* hackable 
* near world-record single-GPU training time (~<18.1 seconds on an A100) . 
* <2 seconds training time in <2 years 

This is a neural network implementation that recreates and reproduces from nearly the ground-up in a painstakingly accurate manner a hacking-friendly version of [David Page's original ultra-fast CIFAR-10 implementation on a single GPU](https://myrtle.ai/learn/how-to-train-your-resnet/) -- 94% accuracy in ~<18.1 seconds on an A100 GPU. There is only one primary functional difference that I am aware of. The code has been rewritten practically from scratch in an annotated, hackable flat structure that for me has been extremely fast to prototype ideas in. This code took about 120-130 hours of work from start to finish, and about about 80-90+ of those hours were mind-numbingly tedious debugging of the minutia between my implementation and David's implementation. It turns out that there are so many little things to consider to actually achieve and hold the accuracy David achieved, I find it an interesting balance of tons of wiggle room in places and none at all in others.


I built this because I loved David's work but for for my personal experimentation, his nearly-purely-functional style made implementing radical idea sketches nearly impossible. As a complement to his work, this code is in a single file and extremely flat, but is not as durable for long-term production-level bug maintenance. You're meant to check out a fresh repo whenever you have a new idea. The upside is that since making this repository, I've already gone from idea-to-new-single-GPU-world-record in under 10 minutes for one idea, and maybe under an hourish for doing the same thing a second, different idea as well. I personally find this code a delight to use, and hope you do too! :D Please let me know, whichever way it ends up going for you. I hope to publish those updates in the future, but for now, this is a (relatively) accurate baseline.


Your support helps a lot -- even if it's a dollar as month. I have several more projects I'm in various stages on, and you can help me have the money and time to get them to the finish line! If you like what I'm doing, or this project has brought you some value, please consider subscribing on my [Patreon](https://www.patreon.com/user/posts?u=83632131). There's not too many extra rewards besides better software more frequently. Alternatively, if you want me to work up to a part-time amount of hours with you, feel free to reach out to me at hire.tysam@gmail.com. I'd love to hear from you.


### Known Bugs

The Colab-specific code is commented out at the top, and the timing/performance table reprints the entire table instead of appropriately updating in-place each epoch.

### Why a ConvNet Still? Why CIFAR10? Aren't Transformers the New Thing Now?


Transformers are indeed the new thing, but I personally believe that the way information condenses from a training set into a neural network will still practically always follow the same underlying set of mathematical principles. The goal for this codebase is to get training in under two (2) seconds within a year or two (2), and under one (1) seconds within 4-5 years. This should allow for some very interesting scaled experiments for different techniques on a different kind of level. I have a rough path planned down to about 2-3 seconds of training or so, all things working out as they should. It will likely get very, very difficult beyond that point.

Basically -- the information gained from experimenting with a technique here should translate in some kind of a way. No need to scale up size arbitrarily when looking to suss out the basics of certain applied mathematical concepts for a problem.


### Submissions

Currently, submissions to this codebase as a benchmark are closed as we figure out the level of interest, how to track disparate entries, etc. Feel free to open an issue if you have thoughts on this!

#### Bugs & Etc.

If you find a bug, open an issue! L:D If you have a success story, let me know! It helps me understand what works and doesn't more than you might expect -- if I know how this is specifically helping people, that can help me further improve as a developer, as I can keep that in mind when developing other software for people in the future. :D :)