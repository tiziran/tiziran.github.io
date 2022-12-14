---
created: 2022-09-17T10:19:36+02:00
updated: 2022-09-17T10:19:36+02:00
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
- Huggin
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