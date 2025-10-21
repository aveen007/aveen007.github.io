---
layout: page
title: Laser Weld Defect Detection
description: Automated quality control system using semantic segmentation and generative data augmentation for laser weld inspection.
img: /assets/img/laser-weld-detection.jpg
importance: 1
category: work
related_publications: true
---

This project addresses the critical need for automated quality control in laser welding processes through computer vision and machine learning. Traditional manual inspection of weld macrosections is slow, subjective, and error-prone, making automation essential for modern manufacturing.



## Project Overview

Laser-weld macrosection analysis is essential for assessing weld quality and detecting defects according to ISO 6520-1 standards. This research proposes an automated pipeline that integrates generative data augmentation with weld segmentation to overcome the limitations of manual inspection and data scarcity in industrial settings.

## Technical Approach

### Generative Data Augmentation
To address the scarcity of annotated industrial weld data, we employed Stable Diffusion to synthesize high-quality weld macrosection images. This approach generated up to 4,500 synthetic weld images, significantly expanding our training dataset while preserving crucial contour features that standard augmentations like flipping or cropping would distort.

### Semantic Segmentation Architecture
We evaluated multiple state-of-the-art segmentation models for defect identification:

- **DDRNet**: Deep Dual-Resolution Network maintaining parallel high- and low-resolution feature streams
- **BiSeNet**: Bilateral Segmentation Network combining spatial and contextual paths
- **YOLOv11**: Adapted for segmentation with stable inference and strong robustness

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="/assets/img/WeldArch.jpg" title="Model Architecture Pipeline" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="/assets/img/WeldDefectAsDefinedByISO.png" title="Weld Defect Examples" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Complete model architecture (left) and examples of detected weld defects including undercut, shrinkage groove, and incomplete penetration (right).
</div>

## Experimental Results

Our evaluation employed both standard segmentation metrics and domain-specific geometrical measurements compared against expert manual assessments:

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <table class="table table-striped table-bordered">
            <thead class="thead-dark">
                <tr>
                    <th scope="col">Model</th>
                    <th scope="col">mIoU</th>
                    <th scope="col">Agreement Accuracy</th>
                </tr>
            </thead>
            <tbody>
                <tr>
                    <td>DDRNet</td>
                    <td>95.46%</td>
                    <td>88.62%</td>
                </tr>
                <tr>
                    <td>BiSeNet</td>
                    <td>95.21%</td>
                    <td>94.78%</td>
                </tr>
                <tr>
                    <td>YOLOv11</td>
                    <td>95.24%</td>
                    <td>97.50%</td>
                </tr>
            </tbody>
        </table>
    </div>
</div>
<div class="caption">
    Table 1: Comparative performance of segmentation architectures on weld defect detection.
</div>

**Key Findings:**
- YOLOv11 achieved **97.5% agreement** with expert measurements across 1,312 defects
- All models demonstrated high mIoU scores (>95%)
- The pipeline successfully identified critical defects including continuous undercut, shrinkage groove, excess weld metal, and linear misalignment
- Generated synthetic data maintained geometrical accuracy with <10% deviation from expert measurements

## Implementation Details

### Data Collection
- Material: 09G2S pipeline structural steel (3 × 150 × 450 mm)
- Camera positioned at multiple locations along weld (72mm, 152mm, 232mm, 312mm)
- 166 original weld macrosection images collected from manufacturing line

### Measurement Parameters
- Weld width (b), depth (s), and heat-affected zone area (Aw)
- Defect quantification according to ISO 6520-1 standards
- Real-time monitoring and control capabilities

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="/assets/img/quality-metrics.jpg" title="Quality Assessment Metrics" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="/assets/img/weldUI.PNG" title="Real-time Monitoring Interface" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Automated geometrical measurements (left) and real-time quality monitoring system (right).
</div>

## Research Impact

This work represents the first approach combining generative augmentation and segmentation for reliable, high-precision weld macrosection inspection. The pipeline enables:

- **Automated Quality Control**: Reduces manual inspection time and subjectivity
- **High-Precision Measurements**: Achieves expert-level accuracy in defect quantification
- **Scalable Deployment**: Suitable for integration into manufacturing production lines
- **Standard Compliance**: Adheres to ISO 6520-1 welding defect standards

## Publications

This research has been presented at international conferences:
- **GECCO 2025**: Genetic and Evolutionary Computation Conference (ACM/SIGEVO)
- **FLAMN 2025**: Conference on Artificial Intelligence Applications
- **AAAI Conference**: Under review for 2025 proceedings

**Code Repository**: [LaserWeldMonitor on GitHub](https://github.com/ILT-ITMO/LaserWeldMonitor.git)

## Technologies Used

- **Computer Vision**: YOLOv11, DDRNet, BiSeNet
- **Generative AI**: Stable Diffusion for data augmentation
- **Deep Learning**: PyTorch, semantic segmentation
- **Industrial Standards**: ISO 6520-1 compliance
- **Programming**: Python, OpenCV, image processing libraries