# Waste Classification using Deep Learning

## Introduction
Waste management is a critical environmental concern worldwide. Traditional methods of waste sorting are often labor-intensive and time-consuming. This project aims to develop a deep learning model to automate waste classification tasks, specifically focusing on classifying images of different types of waste.

## Dataset
We used the **Real Waste Dataset from UCI**, which contains **4,752 images** across **9 waste categories**:
- Cardboard: 461
- Food Organics: 411
- Glass: 420
- Metal: 790
- Miscellaneous Trash: 495
- Paper: 500
- Plastic: 921
- Textile Trash: 318
- Vegetation: 436

Each image has dimensions **524 × 524 × 3 (RGB)**. The dataset was standard-scaled before training to ensure faster convergence.

Dataset link: [UCI Real Waste Dataset](https://archive.ics.uci.edu/dataset/908/realwaste)

## Evaluation Metrics
- **Categorical Cross-Entropy Loss**: measures prediction error.
- **F1 Score**: harmonic mean of precision and recall, ensuring balanced classification.

## Models & Experimentation
We trained four different CNN architectures with an **80/20 train-validation split**.  
Training setup included **Adamax optimizer**, **CrossEntropy loss**, **Learning Rate Scheduler**, and **Model Checkpoints**.

### Models:
1. **Custom CNN architecture** – baseline model built from scratch.  
2. **VGG 19** – deep CNN, rarely explored for this dataset in Kaggle.  
3. **Inception V3** – transfer learning with fine-tuning (20 epochs).  
4. **MobileNets V1.0** – lightweight CNN optimized for speed.  

### Training Strategy:
- Initially trained only the top layer for **10 epochs**.  
- Fine-tuned selected pre-trained layers for another **10 epochs** at a reduced learning rate.  
- Implemented **Step Learning Rate Scheduling** and **Model Checkpoints** to optimize performance.

## Results
| Model | Validation F1-Score | Epochs |
|-------|----------------------|--------|
| Custom CNN | 0.6598 | 30 |
| VGG 19 | 0.7905 | 20 |
| Inception V3 | 0.8947 | 20 |
| MobileNets V1.0 | 0.8464 | 20 |

- **Best Accuracy**: Inception V3 (F1 = 0.8947)  
- **Best Efficiency**: MobileNets V1.0 (fast, lightweight)  

## Conclusion
- **Inception V3** delivered the best accuracy.  
- **MobileNets V1.0** offered the best balance of speed and performance using depthwise separable convolutions.  
- Deep learning shows strong potential for real-world waste classification, enabling smarter and faster recycling systems.

## Team Members
- Amish Faldu (af557)  
- Sneh Vora (sv992)  
- Palak Pabani (pp872)  

## Resources
- 📂 Dataset: [UCI Real Waste Dataset](https://archive.ics.uci.edu/dataset/908/realwaste)  
- 💻 Code: [Google Drive Repository](https://drive.google.com/drive/folders/1UnGzeVwuwI4ap-v0p4m4ro1qXug3mnD_?usp=share_link)  
- 🎥 Project Video: [Video Link](https://drive.google.com/file/d/1DwDitx8-5ZPQMI9rPKuNIy034M6QPGFj/view)

---

