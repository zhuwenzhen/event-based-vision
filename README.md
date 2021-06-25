# Event-based Vision
My notes of getting familiar of this subfield, common datasets, SoPs, and classic code framework

- [ ]  Datasets
- [ ]  Classical Methods
- [ ]  Classical Code Framework

## A Survey

### Abstract

- Event cameras v.s. traditional cameras
    - low-latency
    - high speed
    - high dynamic range

- Common Tasks
    - low-level vision: feature detection & tracking, optical flow, etc.)
    - high-level vision: reconstruction, segmentation, recognition

- Techniques
    - Learning-based
        - specialized processors for novel sensors
            - spiking neural networks
    - bio-inspired

### Overview of Bio-inspired technology

- Focus: solve classical computer vision & robotics tasks
- image sensors:
    - high-speed motion estimation
    - high dynamic range (HDR) imaging
- ***definition***: **Event cameras** are *asynchronous* sensors that pose a *paradigm shift* in the way visual information is acquired.
    - reason: they sample light based on the scene dynamics
    - advantages:
        - very high temporal resolution
        - low latency (order: ms)
        - high dynamic range (140 dB vs. 60 dB standard cameras)
        - low power consumption

    - results: event cameras have a large potential for robotics and wearable applications in challenging scenarios for standard cameras.
    - Applications:
        - object tracking
        - surveillance and monitoring
        - object / gesture recognition
        - depth estimation
        - structured light 3D scanning
        - optical flow estimation
        - HDR image reconstruction
        - simultaneous localization and mapping (SLAM)
        - image deblurring
        - star tracking

## Paper organization

1. intro & application
2. event cameras working principle and advantages
3. several methodologies commonly used to extract information from the event camera output, and discusses the biological inspiration behind some of the approaches.
4. reviews applications of event cameras, from low-level to high-level vision tasks, and some of the algorithms that have been designed to unlock their potential
5. neuro-morphic processors & embedded systems
6. software, dataset, and simulators

[Event Cameras v.s. Standard Cameras](https://www.notion.so/28e13f1320634d2c8fe7d4a408f6af29)