# PINN Hyperparameters

The following hyperparameters were used for training the Physics-Informed Neural Network (PINN).

| Category          | Hyperparameter                     | Value                                       |
| ----------------- | ---------------------------------- | ------------------------------------------- |
| **Architecture**  | Number of hidden layers            |  3                                          |
| **Architecture**  | Neurons per hidden layer           | 64                                          |
| **Architecture**  | Activation function                | Tanh and Relu                               |
| **Architecture**  | Output activation                  | Relu                                        |
| **Training**      | Optimizer                          | Adam                                        |
| **Training**      | Learning rate                      | 0.001                                       |
| **Training**      | Number of epochs                   | 10                                          |
| **Training**      | Batch size                         | 1024                                        |
| **Training**      | Training data split                | 80%                                         |
| **Training**      | Validation data split              | 20%                                         |
| **Loss Function** | Total loss                         | `L_total = λ₁L_data + λ₂L_physics + λ₃L_IC` |
| **Input**         | Input variables                    | `time, ρ`                                   |
| **Output**        | Predicted variables                | `p, C1, C2, C3, C4, C5, C6`                 |
| **Preprocessing** | Data scaling                       | MinMaxScaler                                |
| **Framework**     | Deep learning framework            | TensorFlow / Keras                          |
| **Framework**     | Additional framework               | PyTorch                                     |
