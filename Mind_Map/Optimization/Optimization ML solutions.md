---
tags: i/ 
GA: G-SFK3F1H705
main: [[010_Guide]]
link: 
created: 2022-08-11T12:56:14+02:00
updated: 2022-08-11T13:21:16+02:00
---

Recommended ML Optimization and ML solutions and Project Workflow

A) 
	1. specify the use case
	2. specify model interface
	3. how would we monitor performance after deployment?
	4. how can we approximate post-deployment monitoring before deployment?
	5. build a model and iteratively improve it
	6. deploy the model
	7. monitor performance


B) 
	- input/output -> write down
	- always answered these two question:
		- what is your are metric?
		- How do you split your data?
			- imbalance
			- exercise
			- precision(specificity, sensitivity{recall}, imbalance)
		- what is use case?
		- what is your one metric? Auto ML use this one

C)
- Training
	- build a baseline
	- do automated hyper-parameters
	- never randomly data-set split

D)
	1. how to program training
	2. train and not work know how to
		1. debug it and how to fix it
		2. experience trick
		3. data since
	3. train and work but not in developed -> split data
		1. post deployment
			1. monitoring before deployment
			2. where data come from, where will come from, how to collected, how change to time
			3. roc/ac = not sensitive with imbalance data
			4. persition / recall = sentience because persisting secretive to imbalance data

E)
- How to right way collect data?
	- kaggle
	- Ray

F)
- After Training deep learning model
	- Parameter pruning
		- model pruning: reducing redundant parameters which are not sensitive to the performance.
			- aim: remove all connections with absolute weights below a threshold
- Quantization
	- compresses by reducing the number of bits used to represent the weights
        quantization effectively constraints the number of different weights we can use inside our kernels
        per-channel quantization for weights, which improves performance by model compression and latency reduction.
    Low rank matrix factorization (LRMF)
        there exists latent structures in the data, by uncovering which we can obtain a compressed representation of the data
        LRMF factorizes the original matrix into lower rank matrices while preserving latent structures and addressing the issue of sparseness
    Compact convolutional filters (Video/CNN)
        designing special structural convolutional filters to save parameters
        replace over parametric filters with compact filters to achieve overall speedup while maintaining comparable accuracy
    Knowledge distillation
        training a compact neural network with distilled knowledge of a large model
        distillation (knowledge transfer) from an ensemble of big networks into a much smaller network which learns directly from the cumbersome model's outputs, that is lighter to deploy
    Binarized Neural Networks (BNNs)
    Apache TVM (incubating) is a compiler stack for deep learning systems
    Neural Networks Compression Framework (NNCF)
Deep learning model in production
    security: controls access to model(s) through secure packaging and execution Test
    auto training 
    using parallel processing and library such as GStreamer

G)
[https://www.tiziran.com/topics/events/ai-hardware](https://www.tiziran.com/topics/events/ai-hardware) [https://www.tiziran.com/topics/events/openvino-deep-learning](https://www.tiziran.com/topics/events/openvino-deep-learning) [https://www.tiziran.com/topics/hardware](https://www.tiziran.com/topics/hardware) 
