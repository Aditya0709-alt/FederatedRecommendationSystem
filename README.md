<p align="center">
<img width="394" alt="Screenshot 2023-05-03 at 10 21 27 PM" src="https://user-images.githubusercontent.com/77115883/235985781-3535a20e-61f3-46d9-8a6a-d66605dfc906.png">
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
* [Tech Stack](#tech-stack)
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


## Project Design

<p align="center">
<img width="372" alt="image" src="https://user-images.githubusercontent.com/77115883/235989091-9d44195e-e26d-4a9e-b034-8bfc0604881b.png">
</p>

