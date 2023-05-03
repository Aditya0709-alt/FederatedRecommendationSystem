<p align="center">

![amazonscience-federatedlearning](https://user-images.githubusercontent.com/77115883/235994095-b8fd7889-8de9-439e-9839-b5fda1b6cea3.gif)

</p>


<h1 align="center">Federated Recommendation System </h3>


# Table of Contents

* [Background](#background)
* [Problem Statement](#ps)
* [Objective](#objective)
* [Scope](#scope)
* [Literature Survey](#literature-survey)
* [Project Design](#project-design)
* [System Architecture](#system-architecture)
* [Hardware/Software Requirements](#hardwaresoftware)
* [Implementation](#implementation)
* [Conclusion](#conclusion)


## Background

Traditional machine learning is a field of artificial intelligence (AI) that involves the use of algorithms and statistical models to enable machines to learn from data and make predictions or decisions. In traditional machine learning, the data is typically centralized in a single location for training, and the trained model is deployed to make predictions on new data.

One of the main challenges of traditional machine learning is the need to centralize the data in a single location for training. This can be difficult or impractical in scenarios where the data is distributed across multiple devices or servers, such as in the case of mobile devices, IoT devices, or healthcare data.

In addition, centralizing data for training can raise privacy and security concerns, particularly when the data is sensitive or personally identifiable. Centralizing the data in a single location can make it vulnerable to breaches and hacking attempts, which can have serious consequences for individuals and organizations.

Federated learning addresses these challenges by enabling the training of models across multiple devices or servers, without the need to centralize the data. Instead of transmitting the data to a central location, the model is trained locally on each device or server, and only the model updates are transmitted to a central location for aggregation.


## Problem Statement

At first sight, both federated learning and classical distributed learning share a similar goal of minimizing the empirical risk over distributed entities. However, there are fundamental challenges associated with solving the above objective in the federated settings, as we describe below.

- Expensive Communication
- Systems Heterogeneity
- Statistical Heterogeneity
- Privacy Concerns


## Objectives

1.	To address critical issues regarding data privacy and protection.
2.	To solve the challenges of statistical heterogeneity, systems heterogeneity, and privacy concerns in federated learning.
3.	To create a client-server cluster using hardware or software.
4.	To implement the FedScope architecture on a generalized dataset and on graph data.
5.	To develop a recommendation system based on the FedScope architecture.


## Scope

Our project was initiated to address the critical issues regarding data privacy and protection, which are of paramount importance with the ongoing proliferation of data. The scope of our project aims to solve the following challenges : 
- Statistical Heterogeneity 
- Systems Heterogeneity 
- Privacy Concerns 

Solving the *Expensive Communication* challenge is not a part of our project's scope 

We aim to implement the following during the course of our project:
- Create a Client-Server Cluster using Hardware or Software 
- Implement FedScope Architecture on generalised dataset 
- Implement FedScope Architecture on graph data 
- Develop a Recommendation System based on FedScope Architecture



## Literature Survey

The literature survey conducted for this project included a review of several papers related to Federated Learning (FL). FL is a machine learning technique that enables multiple clients to collaborate on training a shared model without having to share their raw data with each other or with a central server. This technique is particularly useful in situations where data privacy is a concern or where the data is distributed across different locations.

One paper that was reviewed as part of the literature survey was **FederatedScope: A Flexible Federated Learning Platform for Heterogeneity** by Xie et al. (2023). This paper proposed a novel FL platform called FederatedScope that uses an event-driven architecture to express the behaviors of servers and clients independently from a global perspective. The platform was designed to address the challenge of heterogeneity, which is a common issue in FL where clients have different data distributions or feature spaces. The paper demonstrated that FederatedScope achieved better performance than existing FL platforms in terms of accuracy and communication efficiency.

Another paper that was reviewed was **FedBN: Federated Learning on Non-IID Features via Local Batch Normalization** by Li (2021). This paper proposed an algorithm to deal with statistical heterogeneity in FL. The algorithm, called FedBN, uses local batch normalization to adjust for differences in feature distributions across clients. The paper showed that FedBN outperformed existing FL algorithms, such as FedAvg and FedProx, in terms of convergence speed and accuracy.

The literature survey also included a review of **FedGNN: Federated Graph Neural Network for Privacy-Preserving Recommendation** by Chuhan et al. (2021). This paper proposed a federated framework for privacy-preserving graph neural network (GNN) based recommendation. The framework allowed each user client to locally train their own GNN model while protecting their privacy through differential privacy techniques. The paper demonstrated that the proposed framework achieved comparable performance to existing centralized recommendation systems while maintaining privacy.

Another paper that was reviewed was **Personalized Federated Learning using Hypernetworks** by Shamsian (2021). This paper proposed a method for personalized federated learning using hypernetworks, which are small neural networks applied to a target network. The method allowed each client to learn a personalized model while minimizing the communication overhead. The paper demonstrated that the proposed method achieved better performance than existing FL algorithms in terms of both accuracy and communication efficiency.

Finally, the literature survey included a review of **Federated Social Recommendation with Graph Neural Network** by Liu et al. (2022). This paper proposed a novel framework for social recommendation using graph neural network (GNN) called FeSoG. The framework was designed to address three critical challenges in social recommendation, namely data sparsity, cold-start, and diversity. The paper showed that the proposed framework outperformed existing social recommendation algorithms in terms of accuracy and diversity.


## System Architecture

<p align="center">
<img width="372" alt="image" src="https://user-images.githubusercontent.com/77115883/235989091-9d44195e-e26d-4a9e-b034-8bfc0604881b.png">
</p>


## Project Design

<p align="center">
<img width="505" alt="image" src="https://user-images.githubusercontent.com/77115883/235989786-116ba191-549b-4ef2-8271-7e29fabcb566.png">
</p>

<p align="center">
<img width="497" alt="image" src="https://user-images.githubusercontent.com/77115883/235989728-2a513e41-4dc3-4048-88a3-4361c4c80349.png">
</p>


## Hardware/Software Requirements

- Language: Python with ML Libraries such as Tensorflow, 
        NLTK, rdkit, numpy, PyTorch and more 

- WanDB for logging results 

- PaperSpace and Cuda for Computation

- HTML, CSS, BootStrap and JavaScript for Website


## Implementation

The project was implemented in multiple phases viz. creating the client-server cluster for connecting the applications, understanding and building a recommendation system model on top of FederatedScope, a modular framework for creating personalised and state-of-the-art machine learning models.

For creating the cluster, we experimented with different approaches; using the physical systems in our laboratory as well as exploring virtual options like VirtualBox, VMWare, Proxmox, etc.

For simulating a cluster physically, the FederatedScope architecture provides the distributed mode.
The distributed mode in FederatedScope denotes running multiple procedures to build up an FL course, where each procedure plays as a participant (server or client) that instantiates its model and loads its data. The communication between participants is already provided by the communication module of FederatedScope.

```shell
# Firstly start the server that is waiting for clients to join in
python federatedscope/main.py --cfg scripts/distributed_scripts/distributed_configs/distributed_server.yaml distribute.data_file toy_data/server_data distribute.server_host 127.0.0.1 distribute.server_port 50051

# Start the client #1 (with another process)
python federatedscope/main.py --cfg scripts/distributed_scripts/distributed_configs/distributed_client_1.yaml distribute.data_file toy_data/client_1_data distribute.server_host 127.0.0.1 distribute.server_port 50051 distribute.client_host 127.0.0.1 distribute.client_port 50052
# Start the client #2 (with another process)
python federatedscope/main.py --cfg scripts/distributed_scripts/distributed_configs/distributed_client_2.yaml distribute.data_file toy_data/client_2_data distribute.server_host 127.0.0.1 distribute.server_port 50051 distribute.client_host 127.0.0.1 distribute.client_port 50053
# Start the client #3 (with another process)
python federatedscope/main.py --cfg scripts/distributed_scripts/distributed_configs/distributed_client_3.yaml distribute.data_file toy_data/client_3_data distribute.server_host 127.0.0.1 distribute.server_port 50051 distribute.client_host 127.0.0.1 distribute.client_port 50054
```

The above commands are used for generating a toy dataset for easily building model benchmarks. Then, the server is started and by entering the IP address and port for the system. 

```shell
INFO: Server: Listen to x.x.x.x:xxxx...
INFO: Server has been set up ...
Model meta-info: <class 'federatedscope.core.lr.LogisticRegression'>.
... ...
INFO: Client: Listen to x.x.x.x:xxxx...
INFO: Client (address x.x.x.x:xxxx) has been set up ...
Client (address x.x.x.x:xxxx) is assigned with #1.
INFO: Model meta-info: <class 'federatedscope.core.lr.LogisticRegression'>.
... ...
{'Role': 'Client #2', 'Round': 0, 'Results_raw': {'train_avg_loss': 5.215108394622803, 'train_loss': 333.7669372558594, 'train_total': 64}}
{'Role': 'Client #1', 'Round': 0, 'Results_raw': {'train_total': 64, 'train_loss': 290.9668884277344, 'train_avg_loss': 4.54635763168335}}
----------- Starting a new training round (Round #1) -------------
... ...
INFO: Server: Training is finished! Starting evaluation.
INFO: Client #1: (Evaluation (test set) at Round #20) test_loss is 30.387419
... ...
INFO: Server: Final evaluation 
```

These are the results obtained once the clients start listening to the server and start generating training results. 

The datasets used are: 

- Shakespeare
A federation text dataset of Shakespeare Dialogues from LEAF [1] for next-character prediction, which contains 422,615 sentences and about 1,100 clients.

- subReddit
A federation text dataset and subsampled of reddit from LEAF for next-word prediction, which contains 216,858 sentences and about 800 clients.


The use of FederatedScope makes it easier to implement different algorithms like Federated Averaging, FedME, FedEM algorithms.


## Results

For demonstrating the results of our project , we used Wandb, also known as Weights and Biases. 

Wandb provides several features that are useful in FL experiments. First, it allows tracking of the training progress of each client in the FL system, which can help identify any issues related to the training process. Second, it allows visualization of the performance of the model on different datasets, which can help identify any issues related to overfitting or underfitting. Third, it allows comparing the performance of different models trained on different datasets or with different hyperparameters.

In addition to these features, Wandb also provides a dashboard where the progress of the experiments can be monitored in real-time. The dashboard provides several visualizations, such as accuracy plots, loss plots, and learning rate plots, which can help track the progress of the experiments and identify any issues in the training process.


Also, the application developed for performing next word prediction is used for displaying the results. The performance of different algorithms can be viewed and analysed at one place. 

<p align=center">

<img width="525" alt="image" src="https://user-images.githubusercontent.com/77115883/235992076-a4da7ed8-e75c-4713-8c47-3433c89d2b94.png">

<img width="525" alt="image" src="https://user-images.githubusercontent.com/77115883/235992102-84300e68-7479-453a-a513-f7722d8fa38d.png">

<img width="525" alt="image" src="https://user-images.githubusercontent.com/77115883/235992124-7161cd07-d9e1-40f9-869b-9cbd81f79712.png">

<img width="525" alt="image" src="https://user-images.githubusercontent.com/77115883/235992137-d8c4c34f-9d53-4450-9bad-35e619caf39d.png">

<img width="525" alt="image" src="https://user-images.githubusercontent.com/77115883/235992154-d53f3004-4816-4e5d-b398-879ef1577118.png">
</p>


## Conclusion

In conclusion, the project aimed to address the challenges associated with data privacy and protection in federated learning. The scope of the project included solving the challenges of statistical and systems heterogeneity and privacy concerns. The project also aimed to create a client-server cluster for model training, implement the FedScope architecture on generalized and graph data, and develop a recommendation system based on the FedScope architecture.

The literature survey revealed several relevant papers, including FederatedScope, FedBN, FedGNN, Personalized Federated Learning using Hypernetworks, and Federated Social Recommendation with Graph Neural Network. These papers presented various techniques and algorithms for addressing the challenges of federated learning and were instrumental in informing the design and implementation of the project.

The use of the FedME model and FedEM federated learning algorithms, along with the WandB platform, helped in achieving the objectives of the project. The results showed that the project was successful in creating a secure and privacy-preserving federated learning system that could handle heterogeneous data and protect user privacy.

Overall, the project demonstrated the feasibility of using federated learning for privacy-preserving data analysis and highlighted the potential for future research in this field.


## Future Scope

- Implementation of advanced privacy-preserving techniques: While the proposed solution addresses privacy concerns to a great extent, there is still room for improvement. Advanced techniques such as homomorphic encryption, differential privacy, or secure multi-party computation could be explored to enhance privacy and security.

- Optimization of model performance: The proposed FederatedScope platform can benefit from optimization techniques to enhance the performance of the models. Techniques such as model compression, quantization, or pruning can be explored to reduce the size of models and improve their efficiency.

- Integration with edge computing: The integration of the proposed solution with edge computing could enhance the performance and efficiency of the platform. This could involve exploring methods to distribute computation between the edge devices and cloud servers and optimize communication between them.

- Exploration of new use cases: Federated learning has applications in several domains, including healthcare, finance, and smart cities. Further exploration of these domains and developing use cases for them could expand the scope of the project and help solve real-world problems.


## Bibliography

[1] Academy, Data Analytics and Intelligence Lab (DAIL) of DAMO. ‘FederatedScope’. FederatedScope, https://federatedscopeteam.github.io/. Accessed 3 May 2023.

[2] University, Machine Learning Department, Carnegie Mellon. ‘Federated Learning: Challenges, Methods, and Future Directions’. Machine Learning Blog | ML@CMU | Carnegie Mellon University, 12 Nov. 2019, https://blog.ml.cmu.edu/2019/11/12/federated-learning-challenges-methods-and-future-directions/.

[3] Federated Learning: Collaborative Machine Learning without Centralized Training Data. 6 Apr. 2017, https://ai.googleblog.com/2017/04/federated-learning-collaborative.html.

[4] IBM Documentation. 2 May 2023, https://www.ibm.com/docs/en/cloud-paks/cp-data/4.6.x?topic=models-federated-learning.

[5] Wu, Chuhan, et al. ‘FedGNN: Federated Graph Neural Network for Privacy-Preserving Recommendation’. Nature Communications, vol. 13, no. 1, June 2022, p. 3091. arXiv.org, https://doi.org/10.1038/s41467-022-30714-9.

[6] Matsuda, Koji, et al. FedMe: Federated Learning via Model Exchange. arXiv, 15 Oct. 2021. arXiv.org, https://doi.org/10.48550/arXiv.2110.07868.



