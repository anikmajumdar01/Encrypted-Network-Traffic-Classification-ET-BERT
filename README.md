# Encrypted Network Traffic Classification using ET-BERT

This repository contains the practical implementation and experimental evaluation of a network security and traffic classification project conducted for the Advanced Computer Networks course. 

## Project Motivation and Context
In modern enterprise and campus networks, an overwhelming majority of internet traffic is encrypted using protocols like TLS 1.3 to protect user privacy. While encryption secures data in transit, it poses a significant challenge for network administrators, firewalls, and Intrusion Detection Systems (IDS) that need to monitor traffic, detect malicious payloads, and enforce Quality of Service (QoS). 

Traditional port-based or shallow packet inspection methods fail when dealing with encrypted streams. To solve this network security challenge, this project implements **ET-BERT**—a deep learning framework that treats network datagram payloads like natural language text, leveraging Transformer-based architectures to learn contextual byte representations and accurately classify encrypted network traffic without decrypting the packets.

---

## Experimental Workflow and Scope
This project is divided into two comprehensive evaluation phases to study how transformer models generalize across different networking environments:

1. **Baseline Reproduction (CSTNET-TLS 1.3 Dataset):**
   * Evaluated the pre-trained ET-BERT model on a large-scale real-world encrypted transport layer security dataset consisting of 120 traffic categories.
   * Focused on packet-level representation learning to classify complex encrypted application behaviors.

2. **Custom Dataset Adaptation (CIC-Darknet2020 Dataset):**
   * Extended the framework to handle network flow records from the CIC-Darknet2020 dataset (`Darknet.CSV`).
   * Implemented data cleaning, standard scaling, class balancing via `RandomOverSampler`, and feature-to-text sequence conversion to adapt structured network flow telemetry into transformer-compatible tokens.

---

## Summary of Results

| Phase | Dataset | Traffic Classes | Training Instances | Epochs | Batch Size | Test Accuracy |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **Phase 1** | CSTNET-TLS 1.3 (Baseline) | 120[cite: 1] | 465,367[cite: 1] | 3[cite: 1] | 32[cite: 1] | **92.17%**[cite: 1] |
| **Phase 2** | CIC-Darknet2020 (`Darknet.CSV`) | 11[cite: 2] | 426,976 (Resampled)[cite: 2] | 5[cite: 2] | 32[cite: 2] | **85.78%**[cite: 2] |

---

## Repository Structure
```text
Encrypted-Network-Traffic-Classification-ET-BERT/
│
├── notebooks/
│   ├── 01-encrypted-network-traffic-classification.ipynb
│   └── 02-encrypted-network-traffic-classification-darknet.ipynb
│
├── requirements.txt
└── README.md