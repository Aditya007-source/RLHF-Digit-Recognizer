# 🖊️ RLHF Digit Recognizer

An interactive digit recognition system built using PyTorch and Pygame, with a Reinforcement Learning from Human Feedback (RLHF) loop to improve predictions over time. You can draw digits in a 28×28 grid, get real-time predictions from a trained neural network, and provide corrections stored for future retraining.

---

## Project Structure
.  
├── digit_recognizer.py     # Interactive app (inference + RLHF feedback)  
├── train_model.py          # Model training script (MNIST dataset)  
├── best_model.pth          # Trained model weights  
├── correction_data.json    # Stores RLHF user corrections  
├── README.md               # This file  

---

## Project Preview

<img width="992" height="788" alt="digit_recognition" src="https://github.com/user-attachments/assets/795595c8-988e-4c33-a1fd-4d8e2a24f214" />

---
## Installation
Clone the repo and install dependencies:  
`git clone https://github.com/Aditya007-source/RLHF-Digit-Recognizer.git`  
`cd RLHF-Digit-Recognizer/1_With RLHF`  
`pip install torch torchvision pygame numpy matplotlib scikit-learn scipy`

---

## Usage
**Train the Model:** `python train_model.py`  
- Loads the MNIST dataset from .idx files  
- Trains the model with batch normalization and dropout  
- Saves best model weights to `best_model.pth`  

**Run the Interactive App:** `python digit_recognizer.py`  

---

## Controls
- **Left Click & Drag** → Draw on the 28×28 grid  
- **C** → Clear the grid  
- **R** → Record correction (prompts for correct digit)  
- **ESC** → Exit the app  

---

## RLHF Workflow
1. User draws a digit → Model predicts  
2. If wrong, press **R** and enter the correct digit  
3. Data saved in `correction_data.json`  
4. Retrain model with correction data to improve accuracy  

---

## Model Architecture
- Fully connected feed-forward network  
- Layers: 784 → 512 → 256 → 128 → 10  
- Batch normalization, ReLU activation, dropout  
- Softmax output layer  
