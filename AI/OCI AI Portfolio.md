#ai #notes

# AI Services Overview
## Language

Allows you to perform sophisticated text analysis at scale.

Pre-trained models include language detection, sentiment analysis, key phrase extraction, text classification, named entity recognition, and personal identifiable information detection.

Custom models can be trained for named entity recognition and text classification with domain-specific data sets.

In text translation, neural machine translation is used to translate text across numerous languages.

## Vision

Allows you to upload images to detect and classify objects in them.

Pre-trained models perform object detection, image classification, and optical character recognition.

Custom models can perform custom object detection by detecting the location of custom objects in an image and providing a bounding box. The custom image classification builds a model to identify objects and scene-based features in an image.

## Speech

The OCI Speech service is used to convert media files to readable texts that's stored in JSON and SRT format.

## Document Understanding

Allows you to upload documents to detect and classify text and objects in them.

Tools within document understanding are as follows:-

- OCR -> Detect and recognize text in a document.
- Text extraction -> Word level and line level text and the bounding box coordinates of where the text is found.
- Key Value Extraction -> Extracts a predefined list of key value pairs of information from documents like receipts
- Table Extraction -> Extracts content and tabular format, maintaining the row and column relationship of cells
- Document Classification -> Classifies documents into different types.
## Digital Assistant

Oracle Digital Assistant is a platform that allows you to create and deploy digital assistants, which are AI-driven interfaces that help users accomplish a variety of tasks with natural language conversations.

# ML Services Overview

OCI AI services contains ways to run AI training for data scientists without need of managing infrastructure.

It contains deployment of Jupyter notebook in the cloud, with Conda to manage dependencies. The Jupyter notebooks are created inside a namespace called project.

It also contains a model catalog that can help data scientists to share their model with their team and work collaboratively.

There is also model deployments that allow you to deploy models stored in the Model Catalog as HTTP endpoints on managed infrastructure, deploying machine learning models as web applications.

Another feature is Data Science jobs which enable you to define and run a repeatable machine learning tasks on fully managed infrastructure.

# AI Infrastructure

## NVidia chips


| Chip Name | Architecture      |
| --------- | ----------------- |
| A100      | Ampere            |
| H100      | Hopper            |
| H200      | Hopper            |
| B200      | Blackwell         |
| GB200     | Grace + Blackwell |



![[nvidia-gpu-comparison.png]]

# GPU Supercluster

## RDMA

Remote Data Memory Access allows for data transfer or network communication that bypasses CPU, goes from one machine to another without any CPU interference. This can allow GPUs to communicate with each other over network without CPU, thus reducing latency.

This technology can help in creating GPU clusters which are all connected with each other, called supercluster.

## NVLink

Used to connect NVidia GPUs together.

## Network Fabric

A network that provides non-blocking bi-directional connection between GPU nodes.

## Clos Network

Clos Network is a kind of multi-stage network that allows connecting large number of GPUs together. It consists of 3 smaller switches that allow entry to network, transfer within the network and out of the network. This enables us to not connect all GPUs together directly (as that requires `n * n` connections), but still allows all GPUs to talk to each other.

A buffer is added to all the switches in network to account for network latency so that there is no loss of data.

There are multiple GPUs in a single block and these blocks are connected with multiple other blocks.

Latency is about 6-7 microseconds within a block and about 20 microseconds across multiple blocks.

There are network locality hints in the cluster which means the users can choose GPUs within the same rack while deploying. This allows the user to have most of their workflow within the same rack, thus having less latency for most use cases. This has an added benefit of avoiding flow collisions, when multiple connections are flowing data from the same switch, thus leading to delays.
