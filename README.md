<p align="center">
<img width="394" alt="Screenshot 2023-05-03 at 10 21 27 PM" src="https://user-images.githubusercontent.com/77115883/235985781-3535a20e-61f3-46d9-8a6a-d66605dfc906.png">
</p>


<h1 align="center">Federated Recommendation System </h3>


# Table of Contents

* [Background](#background)
* [Objective](#objective)
* [Scope](#scope)
* [Literature Survey](#literature-survey)
* [Project Design](#project-design)
* [System Architecture](#system-architecture)
* [Tech Stack](#tech-stack)
* Implementation(#implementation)
* [Conclusion](#conclusion)


## Background

Traditional machine learning is a field of artificial intelligence (AI) that involves the use of algorithms and statistical models to enable machines to learn from data and make predictions or decisions. In traditional machine learning, the data is typically centralized in a single location for training, and the trained model is deployed to make predictions on new data.

One of the main challenges of traditional machine learning is the need to centralize the data in a single location for training. This can be difficult or impractical in scenarios where the data is distributed across multiple devices or servers, such as in the case of mobile devices, IoT devices, or healthcare data.

In addition, centralizing data for training can raise privacy and security concerns, particularly when the data is sensitive or personally identifiable. Centralizing the data in a single location can make it vulnerable to breaches and hacking attempts, which can have serious consequences for individuals and organizations.

Federated learning addresses these challenges by enabling the training of models across multiple devices or servers, without the need to centralize the data. Instead of transmitting the data to a central location, the model is trained locally on each device or server, and only the model updates are transmitted to a central location for aggregation.

![image](https://user-images.githubusercontent.com/77115883/235986543-f1b04c94-ca7f-4b9a-be18-e70f371e2449.png)



