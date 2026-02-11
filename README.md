# An Analysis of Data Association Strategies for Multi-Object Tracking in Crowded Scenes

**Author:** Jana Nikolovska  
Master's Degree in Artificial Intelligence  
University of Bologna  

---

![Demo](dancetrack0001_results.gif)


## Abstract

This project analyzes the impact of different data association strategies for multi-object tracking on the DanceTrack dataset, a challenging benchmark characterized by crowded motion and visually similar targets.

A tracking-by-detection pipeline is implemented and evaluated using three progressively complex tracker configurations:

- **B0:** IoU-only motion-based association  
- **B1:** ByteTrack-style confidence-aware association  
- **B2:** ByteTrack with appearance-based re-identification  

All tracker variants use identical YOLOv8n detections to isolate the effect of the association mechanism.

Detector performance is evaluated independently, and an IoU threshold of **τ = 0.25** is selected based on F1 score. The goal of this work is to understand how different association strategies influence recall, identity consistency, and tracking stability in crowded scenes.

---

## Project Structure

The repository includes:

- YOLO-based detection scripts  
- Tracker implementations for B0, B1, and B2  
- Evaluation scripts using `motmetrics`  
- Configuration files for tested parameter settings  

---

## Execution Setup

To avoid redundant computation and ensure consistent detector input across experiments, YOLO detections are precomputed once and saved to disk.

All tracker variants reuse these detections during evaluation. This approach:

- Ensures fair comparison across models  
- Reduces overall runtime  
- Prevents detector variability from affecting tracker comparison  

---

## Dataset

Experiments are conducted on the training split of the DanceTrack dataset (40 annotated sequences), with each sequence limited to a maximum of 1000 frames due to computational constraints.

Official dataset website:  
https://dancetrack.github.io/

**Note:** In this repository, not all saved prediction files are included. Only one file (`dancetrack00001`) is provided as an example to illustrate the format and structure of the generated outputs.
