# Pet Segmentation with U-Net + ResNet-34

## Project Description
Semantic segmentation model trained on the Oxford-IIIT Pet dataset.
The model predicts a pixel-level mask identifying the animal in each photo.

## Model
- Architecture: U-Net with ResNet-34 encoder
- Encoder weights: pretrained on ImageNet
- Framework: PyTorch Lightning + segmentation-models-pytorch
- Epochs: 15
- Optimizer: Adam (lr=1e-3)
- Loss function: Dice Loss

## Results
- Validation IoU: 0.878 (target was 0.7)
- Training IoU: 0.873
- No overfitting observed

## Dataset
Oxford-IIIT Pet Dataset — 7,390 images of cats and dogs
- Train: 5,912 images
- Validation: 1,478 images
- Each image has a pixel-level trimap annotation (animal / background / border)

## How it works
1. Download Oxford Pets dataset via wget
2. Preprocess masks into binary (animal=1, background=0)
3. Apply augmentations (flip, brightness/contrast, normalize)
4. Train U-Net with ResNet-34 backbone
5. Evaluate IoU on validation set
6. Visualize predicted masks vs ground truth

## Requirements
- torch
- torchvision
- pytorch-lightning
- segmentation-models-pytorch
- albumentations
- opencv-python
- scikit-learn
