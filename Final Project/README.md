# Final Project: Computer Vision Course

## Project Title: Implementation and Exploration of the **Neighborhood Attention Transformer (NAT)**

### Team Members:
- **Mehrdad Baradaran**
- **Katayoun Kobraei**

---

## Project Overview

In this final project, we were tasked with exploring and presenting the **Neighborhood Attention Transformer (NAT)** as detailed in the paper: "Neighborhood Attention Transformer." After understanding the paper and presenting its concepts, we implemented the NAT model, tested it using various datasets, and explored potential innovations based on the original work.

The project required us to:
1. **Read and present the NAT paper**, covering its architecture, attention mechanism, and how it compares with other models like the Vision Transformer (ViT).
2. **Implement the NAT model using PyTorch** and perform modifications to test our understanding and extend the paper's innovations.
3. **Evaluate the NAT model's performance** using datasets like CIFAR-10, explore the model's classification capabilities, and compare it to other attention-based models such as Swin Transformers.

---

## Paper: **Neighborhood Attention Transformer**

### Key Concepts:

- **Neighborhood Attention (NA)**: Introduces a localized attention mechanism that focuses on nearby spatial neighbors, improving efficiency over the global self-attention used in traditional transformers.
- **Benefits**:
  - Reduces computation complexity.
  - Enhances spatial locality, making it ideal for tasks with significant spatial coherence.
  - Scales better for high-resolution images, unlike global attention.

---

## Code Implementation

We implemented the **Neighborhood Attention Transformer (NAT)** using the `natten` library provided by Shi Labs. We followed these steps:

### 1. **Install Dependencies**

```bash
!pip install natten==0.17.1+torch230cu121 -f https://shi-labs.com/natten/wheels/
!pip install transformers datasets
```

### 2. **Model and Dataset Setup**

We used pre-trained models (`shi-labs/nat-mini-in1k-224`) to classify images and fine-tuned the model on the **CIFAR-10** dataset for a customized classification task.

#### Key Steps:

1. **Load and Preprocess CIFAR-10**: Resize images to the input size expected by the NAT model (224x224 pixels), and normalize the images for training.
2. **Modify the NAT Classifier**: Since CIFAR-10 has 10 classes, we modified the pre-trained NAT model's final classifier to handle these 10 output classes.
3. **Training and Validation**: Implemented a training loop to train the NAT model on CIFAR-10 using `torch.optim.Adam`, and tracked the model's performance across training and validation phases.

---

## Results

After training the NAT model for 3 epochs on the CIFAR-10 dataset, we obtained the following results:

- **Training Accuracy**: ~85%
- **Validation Accuracy**: ~80%
- The NAT model, with localized attention mechanisms, was able to efficiently classify CIFAR-10 images. The localized nature of attention allowed the model to focus on nearby spatial features, leading to improved accuracy in the classification task.

---

## Exploring Innovations

We explored modifications such as:

1. **Adjusting the Attention Window Size**: Experimented with varying the neighborhood size to assess its effect on performance and computation.
2. **Alternative Datasets**: We tested NAT on the Hugging Face Cats dataset to understand its generalization to other domains.
3. **Comparison with Swin Transformer**: We compared the NAT model's performance with Swin Transformer models, observing that NAT provided competitive results with fewer computational resources.

---

## Conclusion

The **Neighborhood Attention Transformer (NAT)** is an effective architecture for vision tasks, offering computational efficiency with attention to local regions. Our implementation demonstrated its robustness on CIFAR-10, and through our experiments, we saw how NAT's innovations compared to more conventional transformers like Swin.

---

## Future Work

- Explore further optimizations in NAT for large-scale datasets.
- Investigate real-world deployment scenarios where NAT's localized attention could offer significant benefits, such as object detection or segmentation.

---

### References:
- **NAT Paper**: *Neighborhood Attention Transformer* (Shi Labs)
- **Natten Library**: [https://shi-labs.com/natten](https://shi-labs.com/natten)
