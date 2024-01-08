# Fake Review Detection in E-Commerce Platforms

## Overview
This project focuses on the classification of fake reviews in e-commerce platforms using advanced transformer-based models. The primary goal is to accurately identify computer-generated fake reviews, leveraging the capabilities of models like ELECTRA and MiniLM. This repository contains the code and datasets used in the study, along with detailed documentation on the methodology and results.

## Dataset
The dataset includes Amazon reviews, with a balanced mix of human-written and computer-generated fake reviews. The fake reviews were generated using GPT-2, ensuring diversity and complexity in the data. This approach helps avoid biases typically present in manually labeled datasets.

## Project Flow Chart
![image](https://github.com/Zayuki/Fake-Review-Detection-in-E-commerce-Platform/assets/67309677/432a8602-77d5-4a90-83be-0458618498e9)

## Algorithm Selections
* ELECTRA-Base
* ELECTRA-Small
* ELECTRA-Large
* MiniLM
  
### Hyperparameters of the models

| Hyperparameter          | Base ELECTRA                       | Large ELECTRA                      | Small ELECTRA                      | MiniLM                                 |
|-------------------------|------------------------------------|------------------------------------|------------------------------------|----------------------------------------|
| Repository Path         | google/electra-base-discriminator  | google/electra-large-discriminator | google/electra-small-discriminator | microsoft/Multilingual-MiniLM-L12-H384 |
| Parameters              | 109M                               | 335M                               | 14M                                | 118M                                   |
| Batch Size for Training | 32                                 | 6                                  | 32                                 | 32                                     |
| Batch Size for Testing  | 32                                 | 6                                  | 32                                 | 32                                     |
| Epoch                   | 2                                  | 1                                  | 2                                  | 2                                      |
| Maximum Sequence Length | 512                                | 512                                | 512                                | 512                                    |
| Activation Function     | GELU                               | GELU                               | GELU                               | GELU                                   |
| Learning Rate           | 0.00005                            | 0.00005                            | 0.00005                            | 0.00005                                |
| Dropout Probability     | 0.1                                | 0.1                                | 0.1                                | 0.1                                    |

## Results
| Model                              | Parameters | Accuracy | Precision | Recall | F1-score | Total Fine-tuning time (s) |
|------------------------------------|------------|----------|-----------|--------|----------|---------------------------|
| ELECTRA-Base                       | 109M       | 96       | 96        | 96     | 96       | 2984                      |
| ELECTRA-Small                      | 14M        | 95       | 95        | 95     | 95       | 651                       |
| ELECTRA-Large                      | 335M       | 98       | 98        | 98     | 98       | 12649                     |
| fakeROBERTA (Salminen et al., 2022)| 125M       | 97       | 97        | 97     | 97       | 3069                      |
| MiniLM                             | 118M       | 97       | 97        | 97     | 97       | 1054                      |

