# Decision Tree Classifier

> A lightweight C++ implementation of the Decision Tree algorithm for multi-class classification, supporting multiple splitting criteria and pruning.

---

## Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Algorithm](#algorithm)
- [Prerequisites](#prerequisites)
- [Installation](#installation)
- [Usage](#usage)
  - [Parameters](#parameters)
  - [Input Format](#input-format)
  - [Example](#example)
- [Output](#output)
- [Project Structure](#project-structure)
- [Applications](#applications)
- [References](#references)

---

## Overview

This project implements a Decision Tree classifier — a supervised learning algorithm that builds a tree-like model of decisions based on feature values. The tree is constructed by recursively partitioning the dataset on the most informative attributes, producing a model that is both highly interpretable and effective across a range of classification tasks.

---

## Features

- **Multiple splitting criteria** — information gain, gain ratio, and Gini index
- **Automated tree construction** — entropy-based recursive splitting
- **Pruning support** — reduces overfitting via configurable pruning techniques
- **Multi-class classification** — handles any number of target classes
- **Human-readable output** — exports decision rules and tree structure in plain text

---

## Algorithm

The classifier is built in four stages:

1. **Feature selection** — selects the best attribute to split on using information gain or Gini index
2. **Tree construction** — recursively partitions the dataset into branches and leaf nodes
3. **Stopping criteria** — halts splitting based on max depth, minimum sample count, or node purity
4. **Prediction** — traverses the tree from root to leaf to assign class labels to new instances

---

## Prerequisites

- C++ compiler with **C++11** support or later (e.g., `g++`, `clang++`)
- Standard Template Library (STL) — no external dependencies

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/decision-tree.git
cd decision-tree
```

Compile:

```bash
g++ -std=c++11 -O2 -o decisiontree decision_tree.cpp
```

---

## Usage

```bash
./decisiontree <training_file> <test_file> [output_file]
```

### Parameters

| Argument | Required | Description |
|:---|:---:|:---|
| `training_file` | ✅ | Path to the training dataset (CSV) |
| `test_file` | ✅ | Path to the test dataset for prediction (CSV) |
| `output_file` | ❌ | Optional path to write results and tree structure |

### Input Format

Input files must be **CSV** with feature names in the first row and the **class label in the last column**:

```
feature1,feature2,feature3,class
value1,value2,value3,classA
value4,value5,value6,classB
value7,value8,value9,classA
```

### Example

```bash
./decisiontree train.csv test.csv results.txt
```

Trains on `train.csv`, predicts labels for `test.csv`, and writes the full output to `results.txt`.

---

## Output

The program produces three sections of output:

**1. Tree structure**
```
Root [feature1]
├── value <= threshold
│   ├── [feature2]
│   │   ├── Leaf: ClassA
│   │   └── Leaf: ClassB
└── value > threshold
    └── Leaf: ClassC
```

**2. Classification results** — predicted class label for each test instance

**3. Performance metrics**
```
Test Accuracy: 92.5%

Confusion Matrix:
         ClassA  ClassB  ClassC
ClassA     45      2       1
ClassB      1     38      3
ClassC      0      2      43
```

---

## Project Structure

```
decision-tree/
├── decision_tree.cpp   # Core algorithm implementation
├── README.md           # This file
└── examples/           # Sample datasets and expected outputs
```

---

## Applications

Decision Trees are used across a wide range of domains:

- Medical diagnosis and clinical prediction
- Credit risk assessment and fraud detection
- Customer segmentation and churn modeling
- Image classification and pattern recognition
- Feature importance analysis

---

## References

- Quinlan, J. R. (1986). Induction of decision trees. *Machine Learning*, 1(1), 81–106.
- Breiman, L., Friedman, J., Stone, C. J., & Olshen, R. A. (1984). *Classification and Regression Trees.* CRC Press.

---

*Licensed under the MIT License.*
