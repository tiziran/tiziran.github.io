---
creation date: 2022-08-08 21:38
tags: i/FSDL, FSDL2022 , notes, tiziran, Farshid, Farshid_Pirahansiah, farshidPirahansiah, mindMap, Full_Stack_Deep_Learning_Course_2022
source: Full Stack Deep Learning Course 2022
Status: Full Stack Deep Learning Course 2022
title: Full Stack Deep Learning Course 2022
type: Full Stack Deep Learning Course 2022
description: Full Stack Deep Learning - Course 2022
site: https://www.tiziran.com 
project: Tiziran, Farshid
GA: G-SFK3F1H705
created: 2022-08-11T11:58:16+02:00
updated: 2022-08-28T14:15:04+02:00
---


# Lecture 01 
- When to Use ML and Course Vision
	- Intro
		- more ML product
		- commoditization of model training 
		- translation research to real-world products
		- ML production engineering
		- [[MLOps]]
	- When to use machine learning
		- lots of ML projects fail 
			- ML is still research
			- technically infeasible or poorly scoped
			- unclear success criteria
			- #paper: ML: The high-interest credit card of technical debt
		- #book: The economics of AI
		- #paper: Three Principles for designing ML-powered products		
	- How to pick problems to solve with ML 
		- TL/DR: high impact, low-cost
	- Life-cycle of a ML project
		- planning & project setup
		- data collection & labeling
		- training & debugging
		- deploying & testing 
- Labs 1-3: CNNs, Transformers, PyTorch Lightning
	- Lab 00: Overview
		- https://github.com/full-stack-deep-learning/fsdl-text-recognizer-2022-labs 
		- code, markdown, site, mirro, youtube, ... all in one jupyter notebook 
			- from IPython.display import IFrame
			- IFrame(app_url, width=1024, height=896)			- 
	- Lab 01: Deep Neural Networks in PyTorch       
		- ??		- 
	- Lab 02a: PyTorch Lightning		- 
	- Lab 02b: Training a CNN on Synthetic Handwriting Data		- 
	- Lab 03: Transformers and Paragraphs *          
		- ResnetTransformer
		- teacher_forward
		- --precision 16
		- --limit_train_batches 10	 


# Lecture 02
Lecture 02: Development Infrastructure & Tooling (FSDL 2022)
- PyTorch Lightning + VS Code + Python
- data parallelism
	- distributeddataparallel 
	- Horovod 
	- sharded data parallelism
	- ZeRO-3
- pipelined model parallelism
- tensor parallelism
- MosaicML 
- FFCV
- compute
	- only NVIDIA
	- use most expensive per-hour machines
- resource management
	- kubernetes + kubeflow
	- AWS SageMaker
	- Anyscale
	- Grid.ai
	- determined.ai
- experiment management
	- tensorboard
	- mlflow tracking
	- Weights & Biases
- All in One
	- AWS SageMaker
	- Gradient
	- Domino
# Lecture 03
- testing
	- help ship faster
	- 
- 
---

![[Pasted image 20220809121756.png]]
![[Pasted image 20220809123400.png]]

![[Pasted image 20220809125511.png]]
Lecture 02
![[Pasted image 20220820102243.png]]

![[Pasted image 20220820102320.png]]






