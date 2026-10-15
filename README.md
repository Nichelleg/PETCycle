# ♻️ PETCycle
## AI-Powered Textile Identification & Recycling Awareness
### *Know Your Fabric. Rethink Your Waste.*

**Project Creator & Developer:** Nichelle Graf

**Course:** ITAI 1378 – Computer Vision | Fall 2026  
**Institution:** Houston City College  
**Project Status:** Midterm Project Blueprint – Planning & Research

___
## Project Overview

PETCycle is a proposed consumer-focused application that explores
the integration of computer vision, near-infrared (NIR) spectroscopy,
and artificial intelligence to identify textile fiber composition
and promote awareness of textile waste.

The long-term vision is a smartphone application that could identify
polyester-containing garments, educate consumers about the
environmental impact of synthetic textiles, and connect them
with appropriate recycling opportunities.

The project is inspired by emerging technologies such as
Fraunhofer IPMS's miniature NIR spectrometer for textile
identification and Carbios' enzymatic PET recycling process.

---

## Problem Statement

Millions of tons of discarded textiles enter landfills annually,
including clothing manufactured from polyester, a synthetic
material derived from petroleum-based PET plastic.

Although consumers generally recognize plastic bottles as
recyclable materials, many may not realize that their clothing
contains similar plastic-based polymers. This lack of awareness,
combined with limited textile recycling infrastructure and
difficulties identifying fiber composition, contributes to
the disposal of potentially recoverable materials.

PETCycle seeks to bridge the gap between emerging textile recycling technologies and consumer participation by exploring how computer vision, near-infrared (NIR) spectroscopy, and artificial intelligence can work together to identify polyester-containing garments, increase awareness of their environmental impact, and help consumers make more informed decisions about textile disposal and recycling.

---

## Proposed Solution

PETCycle envisions an AI-assisted textile identification system
that combines computer vision with near-infrared (NIR)
spectroscopy to identify fabric composition.

The proposed system would:

1. Use computer vision to identify a garment and locate
   relevant fabric regions for analysis.
2. Incorporate NIR spectral information to help distinguish
   polyester from other textile fibers and identify blends.
3. Apply machine learning to classify materials based on
   available visual and spectral data.
4. Provide consumers with information about identified
   materials, environmental considerations, and potential
   recycling pathways.

The long-term vision is to integrate these capabilities into
an accessible smartphone application.

For the Computer Vision course, PETCycle will focus on
developing and evaluating a feasible proof of concept using
publicly available textile image and spectral datasets.

---

## Technical Approach

PETCycle will investigate a multimodal approach to textile
identification, combining conventional RGB images with
near-infrared (NIR) spectral information.

The proposed workflow includes:

- **Computer Vision:** Analyze textile images to identify
  fabric regions and extract visual features.
- **Spectral Analysis:** Explore NIR measurements to distinguish
  textile fibers that may appear visually similar.
- **Machine Learning:** Investigate classification models
  suitable for identifying polyester and polyester blends.
- **Multimodal Integration:** Evaluate how visual and spectral
  information could complement each other to improve
  material identification.

The initial proof of concept will use publicly available
datasets and free, open-source Python libraries.

Specific models and evaluation methods will be selected
after examining dataset structure, labels, and compatibility.

---

## Dataset & Data Sources

### Primary Dataset: OpenTextile-NIR (2026)

PETCycle will use OpenTextile-NIR, a publicly available
research dataset designed to support automated textile
identification, sorting, and recycling.

**Source:** https://zenodo.org/records/18269172

The dataset provides:

- **71 textile samples** with documented fiber compositions.
- **71 RGB photographs** captured using a smartphone camera.
- **Near-infrared hyperspectral imaging data** containing
  material-specific spectral information.
- **Fiber composition labels** identifying materials such as
  polyester, cotton, viscose, wool, and elastane.
- **Polyester concentration data**, including pure polyester
  fabrics and polyester blends.

### Preliminary Data Exploration

Initial examination of the composition labels identified:

- 8 samples labeled as 100% polyester.
- 54 samples containing polyester blends.
- 9 samples without a recorded polyester percentage.

The RGB archive contains 71 JPEG photographs,
each approximately 1875 × 1832 pixels.

A preliminary comparison identified 70 exact filename matches
between the image archive and the composition records.
One naming inconsistency requires further investigation.

### Dataset Limitations

The dataset contains only 71 physical textile samples,
despite providing millions of spectral measurements.

This creates limitations for model training and evaluation.

Potential challenges include:

- Small sample size for image classification.
- Uneven representation of polyester and non-polyester fabrics.
- Possible differences between reported and actual
  fiber compositions.
- Risk of data leakage when multiple measurements originate
  from the same textile sample.
- One unresolved image-to-label filename discrepancy.

### Planned Data Preparation

The initial preparation process will include:

1. Validate sample identifiers and composition labels.
2. Examine the distribution of textile fiber percentages.
3. Resize and normalize RGB images for model input.
4. Explore appropriate spectral preprocessing techniques.
5. Separate training and evaluation data by physical
   textile sample to minimize data leakage.

The initial proof of concept will prioritize a manageable
subset of the available data rather than downloading
the complete hyperspectral archive.

---

## Proposed Models & Evaluation

PETCycle will investigate three complementary approaches
to textile identification using the OpenTextile-NIR dataset.

### 1. RGB Computer Vision Model

A pretrained MobileNetV2 convolutional neural network (CNN)
will be explored for extracting visual features from fabric
photographs.

Transfer learning will reduce the need to train a deep
learning model from scratch.

### 2. NIR Spectral Classification

A Support Vector Machine (SVM) will be explored for
classifying textile composition using near-infrared
spectral measurements.

Spectral preprocessing and feature scaling will be
evaluated as part of this approach.

### 3. Multimodal Feature Fusion

PETCycle will investigate combining RGB image features
with NIR spectral features in a classification model.

This approach will explore whether integrating visual
and spectral information improves textile identification
compared with either modality alone.

### Evaluation Strategy

The proposed models will be evaluated using:

- Classification accuracy.
- Precision, recall, and F1-score.
- Confusion matrices.
- Comparison of RGB-only, NIR-only, and combined models.
- Inference time, where practical.

Training and evaluation data will be separated by
physical textile sample to reduce data leakage.

### Preliminary Success Criteria

The initial goal is to demonstrate a reproducible
computer vision proof of concept that processes textile
images and generates interpretable classification results.

A preliminary quantitative target is an F1-score of
at least 0.70 on a clearly defined textile classification
task, subject to dataset feasibility and class balance.

The project will also investigate whether combining
RGB and NIR information improves performance over
the individual approaches.

Results will be reported with appropriate limitations
given the small number of independent textile samples.

---

## Development Milestones

### Phase 1: Research & Planning
- Define the problem and project objectives.
- Research textile recycling and identification technologies.
- Identify and examine publicly available datasets.
- Develop the Midterm Blueprint and technical approach.

### Phase 2: Data Preparation
- Validate image filenames and composition labels.
- Explore fiber composition distributions.
- Preprocess RGB images.
- Examine and prepare NIR spectral measurements.
- Establish appropriate training and evaluation splits.

### Phase 3: Computer Vision Development
- Implement a pretrained MobileNetV2 model.
- Extract features from textile photographs.
- Train and evaluate an initial classification model.
- Document results and limitations.

### Phase 4: Spectral Analysis & Integration
- Develop an SVM baseline using NIR spectral features.
- Investigate combining RGB and NIR features.
- Compare individual and multimodal approaches.
- Evaluate classification performance and inference time.

### Phase 5: Final Evaluation & Documentation
- Refine the working proof of concept.
- Prepare visualizations and model comparisons.
- Document findings, limitations, and future improvements.
- Complete the final demonstration and project report.

---

## Risks & Contingency Plans

| Potential Risk | Mitigation / Fallback |
|---|---|
| Limited number of textile samples | Use pretrained models, avoid training a CNN from scratch, and clearly report evaluation limitations. |
| Imbalanced material compositions | Examine class distributions and select an appropriate classification task and metrics. |
| Data leakage between measurements | Split training and evaluation data by physical textile sample. |
| RGB images may not reliably identify fiber composition | Treat visual classification as an exploratory baseline and investigate NIR as complementary evidence. |
| Large hyperspectral files | Begin with available CSV spectral measurements rather than full hyperspectral image cubes. |
| Incomplete or inconsistent sample identifiers | Validate image-to-label matches and exclude unresolved records from supervised training. |
| Multimodal integration proves infeasible | Deliver a working RGB computer vision demonstration and document NIR integration as future development. |
| Limited development time or computing resources | Use Google Colab, lightweight pretrained models, and manageable datasets. |

---

## Tools & Development Environment

- **Google Colab:** Notebook development and experimentation.
- **Python:** Primary programming language.
- **TensorFlow / Keras:** MobileNetV2 and transfer learning.
- **scikit-learn:** SVM classification and evaluation.
- **NumPy / pandas:** Data preparation and analysis.
- **OpenCV / Pillow:** Image processing.
- **Matplotlib:** Visualizations.
- **GitHub:** Version control and project documentation.

The project will use free and open-source tools.

---

## Project Deliverables

- Public GitHub repository with documentation.
- Data source information and preparation notes.
- Reproducible Google Colab notebook.
- Working computer vision proof of concept.
- Model evaluation and visualizations.
- Midterm Blueprint presentation.
- Final project demonstration and report.
