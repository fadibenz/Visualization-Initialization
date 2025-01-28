# Visualization Notebook: Local Linearization of Neural Networks with different Initializations

## Overview
This notebook explores the effects of initialization strategies and network depth on the local linearization of neural networks. 
By visualizing singular values, principal features, and gradient norms, we investigate how different initialization scales and network architectures influence training dynamics and model performance.

## Key Topics Covered
1. **Local Linearization of Neural Networks:**  
   - Understanding the behavior of neural networks in the neighborhood of their parameters.
   - Visualizing singular values and principal features of the gradient matrix.

2. **Initialization Strategies:**  
   - Comparing small (`-0.03` to `0.03`), large (`-3.0` to `3.0`), and properly scaled initialization methods.
   - Analyzing gradient norms and their impact on training stability.

3. **Shallow vs. Deep Networks:**  
   - Comparing the performance and feature representations of shallow (1 hidden layer) and deep (4 hidden layers) networks.
   - Investigating how depth affects the complexity of learned features.

4. **Mismatched Training Data Distribution:**  
   - Evaluating model performance when training data ranges from `-1.0` to `0.4`.

## Key Observations
1. **Small Initialization Scale (`-0.03` to `0.03`):**  
   - Gradient norms are very small, leading to negligible weight updates.
   - Training loss remains constant, and the model predicts a constant value for any input.
   - Singular values are dominated by a single large value, and principal features are constant.

2. **Large Initialization Scale (`-3.0` to `3.0`):**  
   - Gradient norms are very large, causing training to diverge due to numeric overflow.
   - Singular values and principal features are scaled up but exhibit similar patterns to properly initialized networks.

3. **Proper Initialization:**  
   - Gradient norms are balanced across layers, enabling stable training.
   - The model outperforms shallow networks, capturing more complex functions.
   - Singular values and principal features show diverse patterns, reflecting the network's capacity to learn nonlinear relationships.

4. **Shallow vs. Deep Networks:**  
   - Shallow networks produce principal features with fewer linear segments.
   - Deep networks produce principal features with many more segments, enabling them to represent more complex functions.

5. **Mismatched Training Data:**  
   - When training data ranges from `-1.0` to `0.4`, the model's performance is limited outside this range, highlighting the importance of data distribution alignment.

## Usage
1. **Setup:**  
   - Ensure all dependencies are installed (`numpy`, `matplotlib`, `torch`, etc.).
   - Run the notebook in Google Colab or a local environment.

2. **Experiments:**  
   - Modify initialization scales, network depth, and training data ranges to observe their effects.
   - Visualize singular values, principal features, and gradient norms using the provided plotting functions.

3. **Analysis:**  
   - Compare results across different initialization strategies and network architectures.
   - Interpret the impact of initialization and depth on model performance and feature learning.

## Acknowledgements
This notebook is based on coursework from **UC Berkeley EECS 182 (Spring 2023)**. 
The experiments and visualizations are inspired by the homework assignment on local linearization of neural networks.