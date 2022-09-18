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
updated: 2022-09-18T23:19:42+02:00
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
	- pytest: separate suites, shared resources, parametrized
	- doctests
	- notebook: assert, nbformat
	- *codecov*: checked or covered
	- *black*: standard tool
	- *flake8*: for python style 
	- *shellcheck* :
	- github actions
	- pre-commit	 
- testing ML
	- smoke tests
		- expectations testing on data
			- tools: great_expectations
			- memorization test: faster machines, reduce dataset size, turn off regularization, reduce model size, remove expensive components
	- data flywheel
	- TDD: test-driven development is a paradigm for testing
		- 1. write test
		- 2. test fails
		- 3. write code
		- 4. test passes
		- 5. refactor
	- gradient descent is TDD
	- ML test score 
	- troubleshooting models
		- shape error
		- out of memory 
		- numerical errors
	- solve with scale
		- overfitting
			- scale up data
		- underfitting
			- scale up model
		- distribution shift
			- scale up both
		- can't afford scale
			- finetune a model trained at scale
# Lecture 03 Lab
# Lecture 04: Data Management (FSDL 2022)
- fixing/adding/augmenting data: keep it simple
- data sources
	- filesystem: local disk speeds: NVME M.2 SSD, latency: nice visualization - 
	- object storage: usually binary object can versioning, redundancy "S3", 
	- database: persistent, fast, scalable, in RAM, object-store URLs, - postgres, SQLite
		- data warehouse: OLAP, OLTP, ETL 
		- data lake: unstructured: ELT, 
- SQL and DataFrames
	- SQL: structured
	- Pandas is DataFrames: DASK parallelize pandas, RAPIDS pandas on GPUs
- Airflow: specify the DAG of tasks using python
	- Prefect
	- Dagster
- feature stores
	- tecton.ai
	- FEAST
	- Featureform
- Hu
- Activeloop
- Labeling 
	- self-supervised learning
	- image data augmentation
	- HIVE
	- scale.ai
	- labelbox
	- label studio **
	- diffgram
	- aquarium and scale nucleus
	- weak supervision : snorkel.ai - rubrix
- data versioning: level 1 - level 3: DVC 
- privacy 
# Lecture 04 Lab
# Lecture 05: Deployment (FSDL 2022)
- step 1
	- prototype: basic UI: Gradio & Streamlit - cloud URL
	- model-in-service
	- batch prediction: dagster, airflow, metaflow,...
	- model-as-service: ** 
	- REST APIs: GRPC, GraphQL 
- step 2
	- Dependency management: 
		- constrain the dependencies : ONNX, 
		- containers: Docker, 
			- spin up a container for each task
			- tools: Cog, BentoML, TRUSS
	- performance
		- concurrency: thread tuning
		- model distillation
		- quantization: tools: Optimum, built in functions, before training
		- caching: functools
			- ```  
			  @cache
			  def factorial(n):
				  return n * factorial(n-1) if n else 1 ```
		- batching
		- sharing the GPU: RAY SERVE, TF SERVING, 
		- Horizontal scaling
			- container orchestration
				- kubernetes 
					- seldon core
					- kubeflow serving
				- deploying code as serverless functions
					- AWS Lambda
					- Google cloud functions
					- azure functions
			- Rollouts
			- managed options
		- step 3
			- edge deployment
			- TensorRT, CoreML, ML kit, PyTorch mobile, TFLite, TF.js, Apache TVM
			- start up: MLIR, Tiny ML, Modular
			- Efficient
				- quantization
				- model distillation
				- mobile-friendly model
					- mobileNets
				- mindsets
					- choose for target device
					- tuning				
# Lecture 05 Lab
# # Lecture 06: Continual Learning (FSDL 2022)
- what metrics to monitor
	- Outcomes and feedback from users
	- Model performance metrics
	- Proxy metrics
	- Data quality testing
		- accuracy
		- completeness
		- consistency
		- timeliness
		- validity
		- integrity
	- Distribution drift
		- type
			- instantaneous drift like
			- gradual drift
			- periodic drifts
			- temporary drift
		- measure
			- reference window
		- metric
			- 1D : KL , KS
		- dealing with high-dimensional data
			- *projections*
	- system metrics 
- how to tell if those metrics are "bad"
	- KS-Test
	- good
		- 1 fixed rule
		- 2 specified range
		- 3 predicted range
		- 4 unsupervised detection		- 
- tools for monitoring
	- system monitoring tools
		- datadog
		- honeycomb.io
		- NewRelic
		- amazon cloudwatch
	- OSS ML monitoring: evidently AI, why logs
	- 1 logging
		- profiling
		- sampling
	- 2 curation
		- L1: just sample randomly
		- L2: stratified sampling
		- L3: curate "interesting" data
		- manually
			- similarity-based curation
			- projection-based curation
		- automatically curating data using active learning
			- scoring function
				- most uncertain
				- highest predicted loss
				- most different from labels
				- most representative
				- big impact on training
			- tools: scale nucleus, data-centric ML tools
	- 3 retraining triggers
		- based on performance 
		- online learning
	- 4 dataset formation
		- 1: train on all available data
		- 2: sliding window
		- 3: online batch selection
		- 4: continual fine-tuning
	- 5: offline testing
		- dynamic
		- expectation tests
	- 6: online testing
		- shadow mode, AB test, roll out gradually, roll back, ...
- trying it all 
# Lecture 06 Lab

# Lecture 07
# Lecture 07 Lab
# Lecture 08
# Lecture 08 Lab
# Lecture 09
# Lecture 09 Lab
# Lecture 10
# Lecture 10 Lab


---

![[Pasted image 20220809121756.png]]
![[Pasted image 20220809123400.png]]

![[Pasted image 20220809125511.png]]
Lecture 02
![[Pasted image 20220820102243.png]]

![[Pasted image 20220820102320.png]]
%% 
lecture 4
the | or -P4 is using for parallelism in linux
%% 
![[Pasted image 20220916231558.png]]
![[Pasted image 20220917091930.png]]

![[Pasted image 20220917111701.png]]

![[Pasted image 20220917161543.png]]

![[Pasted image 20220918231910.png]]









