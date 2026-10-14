# Federated Learning Simulation

This project was created as part of my bachelor's thesis on Federated Learning (FL) in medicine. Its goal is an environment that simulates Federated Learning on a single machine. Multiple participants (e.g. clinics) train locally on their own data, and a server aggregates their models into a shared global model. The raw data never leaves the participants.

## Features

- **Dataset:** [MedMNIST](https://medmnist.com/) is integrated as the data source.
- **Central configuration:** `config.py` lets you control, among other things:
  - Number of participants
  - Optimizer
  - Data augmentation
  - Non-IID data distribution (`non_iid`)
  - Further training parameters
- **Aggregation:** The server uses **FedAvg** as its algorithm.
- **Monitoring:** TensorBoard is integrated to follow, for example, the validation loss curves.

## Installation

```bash
git clone https://github.com/levonbo/project-federal-learning
cd project-federated-learning
```
The main branch uses an centralized machine learning approach, while the branch "federated-learning-concept" is the main implementation of the federated learning approach. 
This will be changed in the near future. 

## Usage

1. Adjust the parameters in `config.py`.
2. Start the simulation:

   ```bash
   python <entry-script>.py
   ```

## Monitoring Training with TensorBoard

```bash
tensorboard --logdir <log-directory>
```

TensorBoard is then available at [http://localhost:6006](http://localhost:6006).

<!-- Insert screenshot here, e.g. validation loss curves -->
![Validation loss in TensorBoard](docs/tensorboard.png)

## Background

Medical imaging data is sensitive and protected by the GDPR, and individual clinics often only have small sample sizes. Centralized training on pooled data is therefore usually not possible. Federated Learning avoids this by exchanging only model parameters.

## Author

Levon, bachelor's thesis in Media Informatics.
