<a target="_blank" href="https://colab.research.google.com/github/benmoseley/symbolic-regression-with-deep-neural-networks-workshop/blob/main/Symbolic%20regression%20with%20deep%20neural%20networks%20workshop%20-%20student.ipynb">
  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/>
</a>

# Symbolic regression with deep neural networks

Written by Ben Moseley, April 2025.

In this workshop we will train **deep neural networks** to carry out **symbolic regression**. This workshop is inspired by these papers: [Deep Learning for Symbolic Mathematics, Lample and Charton, 2019](https://arxiv.org/abs/1912.01412) and [End-to-end symbolic regression with transformers, Kamienny et al, 2022](https://arxiv.org/abs/2204.10532).

The workshop is split into 3 parts:
 - Part 1: Understanding mathematical expressions and how to generate them
 - Part 2: Generating a training dataset of expressions and tokenization
 - Part 3: Training a deep neural network to carry out symbolic regression

# Coding tasks

The notebook includes coding tasks. Each task is labelled like this:

> Task: do this!
 
The notebook is designed for you to go at your own pace, and also contains extension exercises to stretch those with previous experience.

If you get stuck, please ask the instructors for help, and the completed notebooks are available in this repository for your reference.

# Goal

The goal of this workshop is to train a network to identify a mathematical expression given example data points from the expression. More precisely, given a dataset, $\mathscr{D} = \{(x_0, f(x_0)), \dots, (x_N, f(x_N))\}$, consisting of $N$ observed data points from a unknown function $f(x)$, can we predict the underlying **mathematical expression** for $f(x)$?

<div align="center"><img src="https://benmoseley.blog/uploads/teaching/2025-AIMS-SA/symbolic-regression-task.png" width="60%"></div>

Note:
- We are not just doing function fitting! In function fitting, we want to predict the **value** of $f$ given $\mathscr{D}$. In symbolic regression we want to discover the underlying **mathematical expression** of $f$ given $\mathscr{D}$. This means the network must predict an **expression**.
- For simplicity, we only consider **scalar** (1D) functions with a single **input variable** ($x$) and **integer** constant coefficients. It is a fun task to extend the methods in this notebook to higher dimensions with floating point constants!

# Approach

We will use a deep neural network to **directly predict $f(x)$ given $\mathscr{D}$ as input to the network**, as shown below:

<div align="center"><img src="https://benmoseley.blog/uploads/teaching/2025-AIMS-SA/symbolic-regression-train.png" width="80%"></div>

<div align="center"><img src="https://benmoseley.blog/uploads/teaching/2025-AIMS-SA/symbolic-regression-infer.png" width="80%"></div>

In Part 2 we will explain how to enable the network to directly predict symbolic expressions by using **tokenization** and **autoregressive prediction**.
