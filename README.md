# Event-based Vision

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

## Overview of Bio-inspired technology

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

## Software

- [jAER (java Address-Event Representation) project](http://jaerproject.org/). *Real time sensory-motor processing for event-based sensors and systems*. [github page](https://github.com/SensorsINI/jaer). [Wiki](https://sourceforge.net/p/jaer/wiki/Home/)
    - is a Java-based environment for event sensors and processing like noise reduction, feature extraction, optical flow, de-rotation using IMU, CNN and RNN inference, etc.
- [caer (AER event-based framework, written in C, targeting embedded systems)](https://github.com/inilabs/caer)
- [libcaer (Minimal C library to access, configure and get/send AER data from sensors or to/from neuromorphic processors)](https://github.com/inilabs/libcaer)
- [evl (Open Source Computer Vision Library for Event-based camera and vision for C++)](https://github.com/EventVisionLibrary/evl)
- [ROS (Robotic Operating System)](https://github.com/uzh-rpg/rpg_dvs_ros)
- [YARP (Yet Another Robot Platform)](https://github.com/robotology/event-driven)
- [Prophesee ROS Wrapper](https://github.com/prophesee-ai/prophesee_ros_wrapper) ROS driver and messages for Prophesee event-based sensors
- [Prophesee camera plugins](https://docs.prophesee.ai/stable/installation/windows.html#camera-plugins)
- [CeleX5 ROS Wrapper](https://github.com/kehanXue/CeleX5-ROS) A ROS driver and some other tools for [CeleX5_MP](http://www.celepixel.com/#/Samples) event-based sensor (which has a high resolution at 1280×800)

## Datasets

- [Datasets from the Sensors group at INI](http://sensors.ini.uzh.ch/databases.html) (Institute of Neuroinformatics), Zurich:
    - DVS09 - DVS128 Dynamic Vision Sensor Silicon Retina
    - DVSFLOW16 - DVS/DAVIS Optical Flow Dataset
    - DVSACT16 - DVS Datasets for Object Tracking, Action Recognition and Object Recognition
        - Paper:  Y. Hu, H. Liu, M. Pfeiffer, and T. Delbruck, “[DVS benchmark datasets for object tracking, action recognition, and object recognition](https://www.frontiersin.org/articles/10.3389/fnins.2016.00405/full),” Front. Neurosci., vol. 10, p. 405, 2016.
    - [PRED18](https://docs.google.com/document/d/e/2PACX-1vQ8HzlVv1ZzUEIfCUfUOUazXi__cacsCMU3LTqECrZk3-8nlyDCe2V29CHh20-cr42j8DrrMkFZGd14/pub) 
        - VISUALISE Predator/Prey Dataset
    - DDD17 - DAVIS Driving Dataset 2017
        - J. Binas, D. Neil, S.-C. Liu, and T. Delbruck, “[DDD17: End-to-end DAVIS driving dataset](https://arxiv.org/abs/1711.01458),” in ICML Workshop on Machine Learning for Autonomous Vehicles, 2017.
        - [HMTL link](http://sensors.ini.uzh.ch/news_page/DDD17.html)
    - ROSHAMBO17 - RoShamBo Rock Scissors Paper game DVS dataset
    - DHP19 - DAVIS Human Pose Estimation and Action Recognition
    - DDD20 - End-to-End Event Camera Driving Dataset

- Datasets for optical flow
    - Since ground-truth optical flow is difficult to acquire, [190] considers only flow during purely rotational motion recorded with an IMU, and so, the dataset lacks flow due to translational (parallax) motion. The datasets in [22], [281] provide optical flow as the motion field induced on the image plane by the camera motion and the depth of the scene (measured with a range sensor, such as an RGB-D camera, a stereo pair or a LiDAR). Naturally, ground truth optical flow is subject to noise and inaccuracies in alignment and calibration of the different sensors involved.
    - [22] EV-FlowNet:
        - A. Z. Zhu, L. Yuan, K. Chaney, and K. Daniilidis, “EV-FlowNet: Self-supervised optical flow estimation for event-based cameras,” in Robotics: Science and Systems (RSS), 2018.
    - [281] Visual Navigation
        - F. Barranco, C. Fermuller, Y. Aloimonos, and T. Delbruck, “A dataset for visual navigation with neuromorphic methods,” Front. Neurosci., vol. 10, p. 49, 2016.
        - [Github](https://github.com/fbarranco/eventVision-evbench): Matlab (R) implementations of methods to generate and handle DVS data for building a dataset
    - [190] DVS/DAVIS Optical Flow Dataset
        - B. Rueckauer and T. Delbruck, “[Evaluation of event-based algorithms for optical flow with ground-truth from inertial measurement sensor](https://www.frontiersin.org/articles/10.3389/fnins.2016.00176/full),” Front. Neurosci., vol. 10, no. 176, 2016.
        - [DVS/DAVIS Optical Flow Dataset](https://docs.google.com/document/d/1r9sRYANGuDTUcfSSq-sL4sd79SfjHGNRul_10uztDaI/pub) associated to the paper [Rueckauer and Delbruck, FNINS 2016]().
    - [Bardow et al., CVPR2016](), [Four sequences](http://wp.doc.ic.ac.uk/pb2114/datasets/)
    - [Zhu et al., RAL2018](): *MVSEC The Multi Vehicle Stereo Event Camera Dataset*.
    - [Almatrafi et al. PAMI 2020](): *Distance Surface for Event-Based Optical Flow*. [DVSMOTION20 Dataset](https://sites.google.com/a/udayton.edu/issl/software/dataset?authuser=0)

- Datasets for Pose Estimation and SLAM
    - include [225], [98], [197], [281], [282]. The most popular one is described in [98], which has been used to benchmark visual odometry and visual-inertial odometry methods [27], [103], [104], [127], [128], [129], [131]. This dataset is also popular to evaluate corner detectors [111], [115] and feature trackers [64], [126].
    - [Combined Dynamic Vision / RGB-D Dataset](http://ebvds.neurocomputing.systems/EBSLAM3D/index.html) associated to the paper [Weikersdorfer et al., ICRA 2014]().
    - Barranco, F., Fermüller, C., Aloimonos, Y.,*[A Dataset for Visual Navigation with Neuromorphic Methods](https://dx.doi.org/10.3389%2Ffnins.2016.00049),*
    Front. Neurosci. (2016), 10:49.
    - E. Mueggler, H. Rebecq, G. Gallego, T. Delbruck, D. Scaramuzza,*[The Event-Camera Dataset and Simulator: Event-based Data for Pose Estimation, Visual Odometry, and SLAM](http://rpg.ifi.uzh.ch/davis_data.html),*
    Int. J. Robotics Research, 36:2, pp. 142-149, 2017. [PDF](https://arxiv.org/pdf/1610.08336.pdf), [PDF IJRR](http://dx.doi.org/10.1177/0278364917691115), [YouTube](https://youtu.be/bVVBTQ7l36I), [Dataset](http://rpg.ifi.uzh.ch/davis_data.html).
    - Binas, J., Neil, D., Liu, S.-C., Delbruck, T.,*[DDD17: End-To-End DAVIS Driving Dataset](https://www.openreview.net/pdf?id=HkehpKVG-),*
    Int. Conf. Machine Learning, Workshop on Machine Learning for Autonomous Vehicles, 2017. [Dataset](http://sensors.ini.uzh.ch/databases.html)
    - Zhu, A., Thakur, D., Ozaslan, T., Pfrommer, B., Kumar, V., Daniilidis, K.,*[The Multi Vehicle Stereo Event Camera Dataset: An Event Camera Dataset for 3D Perception](https://doi.org/10.1109/LRA.2018.2800793),*
    IEEE Robotics and Automation Letters (RA-L), 3(3):2032-2039, Feb. 2018. [PDF](https://arxiv.org/abs/1801.10202), [Dataset](https://daniilidis-group.github.io/mvsec/), [YouTube](https://youtu.be/9FaUvvzaHW8).
    - [Event-based, 6-DOF Camera Tracking from Photometric Depth Maps](http://rpg.ifi.uzh.ch/direct_event_camera_tracking/index.html) associated to the paper [Gallego et al., PAMI 2018]()
    - Leung, S., Shamwell, J., Maxey, C., Nothwang, W. D.,[Toward a large-scale multimodal event-based dataset for neuromorphic deep learning applications](https://doi.org/10.1117/12.2305504),
    Proc. SPIE 10639, Micro- and Nanotechnology Sensors, Systems, and Applications X, 106391T. [PDF](https://www.researchgate.net/publication/325939343)
    - [Event-based, Direct Camera Tracking from a Photometric 3D Map using Nonlinear Optimization](http://rpg.ifi.uzh.ch/direct_event_camera_tracking/index.html) associated to the paper [Bryner et al., ICRA 2019]().
    - Delmerico, J., Cieslewski, T., Rebecq, H., Faessler, M., Scaramuzza, D.,[Are We Ready for Autonomous Drone Racing? The UZH-FPV Drone Racing Dataset](http://rpg.ifi.uzh.ch/uzh-fpv.html),
    IEEE Int. Conf. Robotics and Automation (ICRA), 2019. [PDF](http://rpg.ifi.uzh.ch/docs/ICRA19_Delmerico.pdf), [YouTube](https://youtu.be/G5w4ZcEzvoo), [Project page](http://rpg.ifi.uzh.ch/uzh-fpv.html).
    - Lee, A. J., Cho, Y., Yoon, S., Shin, Y., Kim, A.,[ViViD: Vision for Visibility Dataset](https://sites.google.com/view/dgbicra2019-vivid/),
    IEEE Int. Conf. Robotics and Automation (ICRA) Workshop: Dataset Generation and Benchmarking of SLAM Algorithms for Robotics and VR/AR, 2019.
    - [Mitrokhin et al., IROS 2019]().*EV-IMO: Motion Segmentation Dataset and Learning Pipeline for Event Cameras*
    - Hu, Y., Binas, J., Neil, D., Liu, S.-C., Delbruck, T.,*[DDD20 End-to-End Event Camera Driving Dataset: Fusing Frames and Events with Deep Learning for Improved Steering Prediction](https://arxiv.org/abs/2005.08605)*,
    IEEE Intelligent Transportation Systems Conf. (ITSC), 2020. [Dataset](https://sites.google.com/view/davis-driving-dataset-2020/home), [More datasets](http://sensors.ini.uzh.ch/databases.html)
    - Rodríguez-Gómez, J. P., Tapia, R., Paneque, J. L., Grau, P., Gómez Eguíluz, A., Martínez-de Dios, J. R., Ollero A.,*[The GRIFFIN Perception Dataset: Bridging the Gap Between Flapping-Wing Flight and Robotic Perception](https://arxiv.org/pdf/2101.10371)*,
    IEEE Robotics and Automation Letters (RA-L), 2021.

- Datasets for Recognition
    - are currently of limited size compared to traditional computer vision ones. They consist of cards of a deck (4 classes), faces (7 classes), handwritten digits (36 classes), gestures (rocks, papers, scissors) in dynamic scenes, cars, etc. Neuromorphic versions of popular frame-based computer vision datasets, such as MNIST and Caltech101, have been obtained by using saccade-like motions [242], [283]. Newer datasets [17], [113], [284], [285] are acquired in real scenarios (not generated from frame-based data). These datasets have been used in [15], [109], [113], [137], [150], [151], among others, to benchmark event-based recognition algorithms.

    - Orchard, G., Jayawant, A., Cohen, G.K., Thakor, N.,*[Converting Static Image Datasets to Spiking Neuromorphic Datasets Using Saccades](https://doi.org/10.3389/fnins.2015.00437),*
    Front. Neurosci. (2015), 9:437. [YouTube](https://youtu.be/2RBKNhxHvdw)
        - [Neuromorphic-MNIST (N-MNIST) dataset](http://www.garrickorchard.com/datasets/n-mnist) is a spiking version of the original frame-based MNIST dataset (of handwritten digits). [YouTube](https://youtu.be/6qK97qM5aB4)
        - [The Neuromorphic-Caltech101 (N-Caltech101) dataset](http://www.garrickorchard.com/datasets/n-caltech101) is a spiking version of the original frame-based Caltech101 dataset. [YouTube](https://youtu.be/dxit9Ce5f_E)
    - Serrano-Gotarredona,T. and Linares-Barranco, B.,*[Poker-DVS and MNIST-DVS. Their History, How They were Made, and Other Details](http://dx.doi.org/10.3389/fnins.2015.00481)*,
    Front. Neurosci. (2015), 9:481.
        - [MNIST-DVS and FLASH-MNIST-DVS datasets](http://www2.imse-cnm.csic.es/caviar/MNISTDVS.html) are based on the original frame-based MNIST dataset. MNIST-DVS are DVS128 recordings of moving MNIST digits (at 3 scales), while FLASH-MNIST-DVS datasets are recorded by flashing the digits on a monitor.
        - [POKER-DVS](http://www2.imse-cnm.csic.es/caviar/POKERDVS.html). From a set of DVS recordings of very fast poker card browsing, 32x32 pixel windows tracking the symbols are cropped. On average each symbol lasts about 10-30ms.
        - [SLOW-POKER-DVS](http://www2.imse-cnm.csic.es/caviar/SLOWPOKERDVS.html). Paper printed poker card symbols are moved at "human speed" in front of a DVS camera and recorded at 128x128 resolution.
    - [VISUALISE Predator/Prey Dataset](https://www.dropbox.com/sh/x6nm6zl9rrd7yzn/AAB_Fa5F-Y4fSo1nrIJxc8Xoa?dl=0) associated to the paper [Moeys et al., EBCCSP 2016]()
    - Hu, Y., Liu, H., Pfeiffer, M., Delbruck, T.,*[DVS Benchmark Datasets for Object Tracking, Action Recognition, and Object Recognition](https://doi.org/10.3389/fnins.2016.00405),*
    Front. Neurosci. (2016), 10:405. [Dataset](http://dgyblog.com/projects-term/dvs-dataset.html)
    - Liu, Q., Pineda-García, G., Stromatias, E., Serrano-Gotarredona, T., Furber, SB.,*[Benchmarking Spike-Based Visual Recognition: A Dataset and Evaluation](https://doi.org/10.3389/fnins.2016.00496)*,
    Front. Neurosci. (2016), 10:496. [Dataset](https://github.com/qian-liu/benchmarking), [Dataset](https://github.com/NEvision/NE15)
    - [DVS128 Gesture Dataset](http://research.ibm.com/dvsgesture/): The dataset that was used to build the real-time gesture recognition system described in [Amir et al., CVPR 2017]().
    - [N-CARS Dataset](http://www.prophesee.ai/dataset-n-cars/): A large real-world event-based dataset for car classification. [Sironi et al., CVPR 2018]().
    - [Mitrokhin et al., IROS 2018]() *Event-based Moving Object Detection and Tracking*. [Project page and Dataset](http://prg.cs.umd.edu/BetterFlow.html)
    - [ATIS Plane Dataset](https://www.westernsydney.edu.au/bens/home/reproducible_research/atis_planes), assocated to the paper [Afshar et al., Front. Neurosci. 2018]().
    - Cheng, W., Luo, H., Yang, W., Yu, L., Chen, S., Li, W.,*[DET: A High-resolution DVS Dataset for Lane Extraction](http://openaccess.thecvf.com/content_CVPRW_2019/papers/EventVision/Cheng_DET_A_High-Resolution_DVS_Dataset_for_Lane_Extraction_CVPRW_2019_paper.pdf),*
    IEEE Conf. Computer Vision and Pattern Recognition Workshops (CVPRW), 2019. [Project page](https://spritea.github.io/DET/).
    - Miao, S., Chen, G., Ning, X., Zi, Y., Ren, K., Bing, Z., Knoll, A.,*[Neuromorphic Vision Datasets for Pedestrian Detection, Action Recognition, and Fall Detection](https://doi.org/10.3389/fnbot.2019.00038),*
    Front. Neurorobot. (2019). [Dataset](https://github.com/MSZTY/PAFBenchmark)
    - de Tournemire, P., Nitti, D., Perot, E., Migliore, D., Sironi, A.,*[A Large Scale Event-based Detection Dataset for Automotive](https://arxiv.org/abs/2001.08499)*,
    arXiv, 2020. [Code](https://github.com/prophesee-ai/prophesee-automotive-dataset-toolbox), [News](https://www.prophesee.ai/2020/01/24/prophesee-gen1-automotive-detection-dataset/)
    - [N-SOD Dataset](https://drive.google.com/drive/folders/10_bnZ_TOcq7xCtCiDcaDiIO3_Txgr19S) associated to the paper [Ramesh et al., FNINS 2020]().
    - [SL-ANIMALS-DVS Database](http://www2.imse-cnm.csic.es/neuromorphs/index.php/SL-ANIMALS-DVS-Database) associated to the paper [Vasudevan et al., FG 2020](). Recordings made using the sensitive DVS developed at [IMSE](http://imse-cnm.csic.es/).
    - Perot, E., de Tournemire, P., Nitti, D., Masci, J., Sironi, A., [1Mpx Detection Dataset](https://www.prophesee.ai/2020/11/24/automotive-megapixel-event-based-dataset/): [Learning to Detect Objects with a 1 Megapixel Event Camera. NeurIPS 2020]().

- Datasets for Segmentation
    - [Mitrokhin et al., IROS 2018](), Extreme Event Dataset (EED). [Project page and Dataset](http://prg.cs.umd.edu/BetterFlow.html)
    - Mitrokhin, A., Ye, C., Fermüller, C., Aloimonos, Y., Delbrück, T.,*[EV-IMO: Motion Segmentation Dataset and Learning Pipeline for Event Cameras](https://doi.org/10.1109/IROS40897.2019.8968520)*,
    IEEE/RSJ Int. Conf. Intelligent Robots and Systems (IROS), 2019. [PDF](https://arxiv.org/pdf/1903.07520.pdf), [Dataset](https://better-flow.github.io/evimo), [Project page](http://prg.cs.umd.edu/EV-IMO.html)
- The DVS emulators
    - and the simulators in [98] are based on the working principle of an ideal DVS pixel (2). Given a virtual 3D scene and the trajectory of a moving DAVIS within it, the simulator generates the corresponding stream of events, intensity frames and depth maps. The simulator has been extended in [74]: it uses an adaptive rendering scheme, is more photo-realistic, includes a simple event noise model and returns estimated optical flow. The v2e tool [40] generates events from video with a realistic non-ideal noisy DVS pixel model that extends modeling to low lighting conditions. A comprehensive characterization of the noise and dynamic effects of existing event cameras has not been carried out yet, and so, the noise models used are currently somewhat oversimplified.
    