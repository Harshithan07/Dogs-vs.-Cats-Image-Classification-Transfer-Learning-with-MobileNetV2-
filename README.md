# Dogs vs. Cats Image Classification – Transfer Learning with MobileNetV2 


## ABOUT THE PROJECT:
This project addressed the Kaggle “Dogs vs. Cats Redux” binary image classification task by building and benchmarking multiple CNN-based architectures. The final deployed model used MobileNetV2 with transfer learning, which offered the best accuracy and efficiency for generalizing to unseen pet images.


## USE CASE EXPLANATION:
Binary image classification is essential in automated image tagging, pet detection systems, and real-time mobile vision applications. This project lies within the deep learning and computer vision domains and is useful to businesses or platforms dealing with image categorization under limited computational budgets.


## HOW IT IS BUILT AND FULL WORKING:

1. Data Pipeline:

- Dataset: ~25,000 labeled dog/cat images

- Images resized to 224x224 for compatibility with pre-trained models

- Applied augmentation: horizontal flip, zoom, rotation, shear

- Used ImageDataGenerator for on-the-fly transformations

2. Modeling Process:

- Explored Architectures:


   1. Custom CNN (baseline)

   2. VGG16 (transfer learning)

   3. EfficientNetB0

   4. Xception

   5. MobileNetV2 (transfer learning + fine-tuning)

- Final Model – MobileNetV2:

   - Pretrained on ImageNet

   - Top layers replaced with custom head (GlobalAveragePooling → Dropout → Dense sigmoid)

   - Base layers frozen during initial training, then selectively unfrozen for fine-tuning

   - Achieved highest validation accuracy and lowest overfitting

3. Training Setup:

- Optimizer: Adam, with learning rate tuning

- Loss: Binary Crossentropy

- Batch Size: 32 | Epochs: 30

- Used EarlyStopping and ModelCheckpoint to preserve best weights


## OUTPUT AND RESULTS OR BENCHMARKS:

- Best Model: MobileNetV2 + transfer learning (fine-tuned)

- Outperformed VGG16, EfficientNet, and Xception in both accuracy and inference time

- Prevented overfitting with dropout, data augmentation, and selective fine-tuning

- Delivered a high-performance, lightweight, production-ready model


## SKILLS, TOOLS:
 Python, TensorFlow/Keras, MobileNetV2, ImageDataGenerator, Transfer Learning, ModelCheckpoint, EarlyStopping, Binary Classification, Kaggle CLI


## KEYWORDS:
 Deep learning, MobileNetV2, transfer learning, image classification, computer vision, CNN, TensorFlow, binary classifier, model fine-tuning, Kaggle competition
