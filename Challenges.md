# Cricket Bat Corner Detection with DETR:

## Introduction

### Project Overview
The primary objective of this project is to accurately detect the corners of cricket bats in images. This task involves identifying both the top and bottom corners, even in cases of partial occlusion or when the bat is captured at an angle.

### Choice of Model
The DETR (DEtection TRansformers) model was selected due to its remarkable performance in object detection tasks. Its transformer-based architecture and end-to-end approach make it particularly well-suited for this application.

## Data Preparation and Augmentation

### Data Collection
We collected a specialized dataset for this task by leveraging Google Images. This approach allowed us to curate a dataset focused exclusively on cricket bats, ensuring that the model is trained on relevant and representative images.

### Data Augmentation Techniques
1. **Rotation**: Images were randomly rotated to simulate bats captured at various angles. This helps the model generalize better to real-world scenarios.
2. **Flipping**: Horizontal flipping was applied to double the dataset size, while still maintaining the integrity of the annotations.
3. **Occlusion Addition**: Custom augmentation involved adding simulated occlusion to images. For instance, a portion of the bat might be covered to train the model to handle partially visible bats.

### Example:
For example, consider an original image of a cricket bat. By applying rotation augmentation, we create multiple versions of the same image, each showing the bat at a different angle. This augmentation technique exposes the model to a wider range of potential scenarios it might encounter in real-world images.

## Challenges Faced

### Limited Annotated Data
One significant challenge was the scarcity of annotated data specifically for cricket bats. This required the implementation of robust training techniques and an emphasis on effective data augmentation strategies.

### Occlusion and Angled Bats
Real-world images often contain bats that are partially obscured or captured from non-standard angles. This can pose difficulties for the model in accurately detecting corners. Addressing this challenge involved the application of various augmentation techniques to simulate occlusion and rotated bats during training.

### Model Tuning for Specificity
DETR is a versatile object detection model, not specialized for cricket bats. Fine-tuning it for corner detection required adjustments to hyperparameters, particularly the confidence threshold and IOU (Intersection over Union) threshold. This tuning process was crucial for achieving accurate results.

## Handling Challenges

### Data Augmentation and Curriculum Learning
To mitigate the challenge of limited annotated data, a combination of traditional augmentation techniques and custom augmentation methods were employed. This diversified the training data and enabled the model to generalize better to different scenarios.

Additionally, curriculum learning was applied during training. The model was initially exposed to less challenging samples to grasp basic features. As training progressed, more complex and occluded samples were introduced. This gradual learning approach helped the model adapt to handling difficult cases.

### Fine-tuning and Hyperparameter Optimization
Fine-tuning involved meticulous adjustments of confidence thresholds and IOU thresholds. Extensive experimentation was conducted to find the optimal values that balanced precision and recall. This fine-tuning step significantly enhanced the model's performance.

## Conclusion

This project successfully addressed the challenge of cricket bat corner detection using the DETR model. Through careful consideration of specific challenges such as limited annotated data, occlusion, and angled bats, the model achieved accurate and robust results. The combination of data augmentation, curriculum learning, and hyperparameter tuning played pivotal roles in overcoming these challenges.

This project serves as a compelling example of leveraging DETR for specialized object detection tasks and provides valuable insights for similar applications.
