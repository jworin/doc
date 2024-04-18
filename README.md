
# Pose Eetimation

### Sensor needed

#### active sensor: (emit signals):

- Motion Capture (MoCap) systems
- tactile sensing
    - [Intelligent Carpet: Inferring 3D Human Pose from Tactile Signals](https://openaccess.thecvf.com/content/CVPR2021/papers/Luo_Intelligent_Carpet_Inferring_3D_Human_Pose_From_Tactile_Signals_CVPR_2021_paper.pdf)
- Time of Flight (ToF) cameras *(RGBD camera)*
    - Pixels2Pose: Super-resolution time-of-flight imaging for 3D pose estimation
    - [Volumetric Capture of Humans with a Single RGBD Camera via Semi-Parametric Learning](https://arxiv.org/abs/1905.12162)
- Radio Frequency (RF) technologies
    - [3D Human Pose Estimation for Free-from and Moving Activities Using WiFi](https://arxiv.org/abs/2204.07878)
    - [Unsupervised Learning for Human Sensing Using Radio Signals](https://arxiv.org/abs/2207.02370)

#### passive sensor: (no extra signals):

- Inertial Measurement Units (IMUs)
    - [DeepFuse: An IMU-Aware Network for Real-Time 3D Human Pose Estimation from Multi-View Image](https://arxiv.org/abs/1912.04071)
    - [SparsePoser: Real-time Full-body Motion Reconstruction from Sparse Data](https://arxiv.org/abs/2311.02191)
- *other image sensors*
    - [Human Pose and Shape Estimation from Single Polarization Images](https://arxiv.org/abs/2108.06834)
    - [EventCap: Monocular 3D Capture of High-Speed Human Motions using an Event Camera](https://arxiv.org/abs/1908.11505)

### multiple views

- [Probabilistic Triangulation for Uncalibrated Multi-View 3D Human Pose Estimation](https://arxiv.org/abs/2309.04756)
- [Adaptive Multi-view and Temporal Fusing Transformer for 3D Human Pose Estimation](https://arxiv.org/abs/2110.05092)

---

### **Monocular RGB inputs**

#### single person

- direct estimation method
-  2D to 3D lifting method

##### image based

current problems and solutions

> **Depth Ambiguity**:
> 
> different 3d pose projecting to 2d images may result in same pose

- [View Invariant 3D Human Pose Estimation](https://arxiv.org/abs/1901.10841)
  - View-Invariant Hierarchical Correction (VI-HC), view consistent constraints
- [Ray3D: ray-based 3D human pose estimation for monocular absolute 3D localization](https://arxiv.org/abs/2203.11471)
  - convert pixel to 3D normalized *rays(?)*
- [HEMlets PoSh: Learning Part-Centric Heatmap Triplets for 3D Human Pose and Shape Estimation](https://arxiv.org/abs/2003.04894)
  - to learn a more appropriate feature representation in extra


> **Body Structure Understanding**:
> 
> Human body’s unique structures can provide constraints or prior information which could be used to improve pose estimation. 
> 
> How to utilize?

- [A Joint Relationship Aware Neural Network for Single-Image 3D Human Pose Estimation](https://ieeexplore.ieee.org/document/8995784)
  - feature attention block
- [Limb Pose Aware Networks for Monocular 3D Pose Estimation](https://ieeexplore.ieee.org/abstract/document/9663053)
  - can be used to reduce errors
- [Monocular 3D Pose Estimation via Pose Grammar and Data Augmentation](https://ieeexplore.ieee.org/document/9450016)
  - kinematics, symmetry, motor coordination -> RNN

keypoints based human model can be processed by a GNN (Graph) network to better understand for nodes and edges.

- [Feature Boosting Network For 3D Pose Estimation](https://arxiv.org/abs/1901.04877)
  - graphic ConvLSTM
- [Learning Skeletal Graph Neural Networks for Hard 3D Pose Estimation](https://arxiv.org/abs/2108.07181)

> **Occlusion Problems**:
>
> 


##### video based



#### multi person



---

## Others

### human modeling

- skelton keypoints
  - [PoseFormerV2: Exploring Frequency Domain for Efficient and Robust 3D Human Pose Estimation](https://arxiv.org/abs/2303.17472) (discussion about input joint sequence)
- mesh
  - [SMPLer-X: Scaling Up Expressive Human Pose and Shape Estimation](https://arxiv.org/abs/2309.17448)
- voxels
  - [TetraTSDF: 3D human reconstruction from a single image with a tetrahedral outer shell](https://arxiv.org/abs/2004.10534)

### training method (learning model)

- weakly supervised learning
  - [CameraPose: Weakly-Supervised Monocular 3D Human Pose Estimation by Leveraging In-the-wild 2D Annotations](https://arxiv.org/abs/2301.02979)
- unsupervised learning
  - [Global Adaptation meets Local Generalization: Unsupervised Domain Adaptation for 3D Human Pose Estimation](https://arxiv.org/abs/2303.16456)
- few-shot learning
  - [PandaNet : Anchor-Based Single-Shot Multi-Person 3D Pose Estimation](https://arxiv.org/abs/2101.02471)
- meta learning
  - [Camera Distortion-aware 3D Human Pose Estimation in Video with Optimization-based Meta-Learning](https://arxiv.org/abs/2111.15056)
- reinforcement learning
  - [PoseTriplet: Co-evolving 3D Human Pose Estimation, Imitation, and Hallucination under Self-supervision](https://arxiv.org/abs/2203.15625)

### efficiency related (model optimization techniques)

- knowledge distillation
  - [Effective Whole-body Pose Estimation with Two-stages Distillation](https://arxiv.org/abs/2307.15880)
  - [PoseNet3D: Learning Temporally Consistent 3D Human Pose via Knowledge Distillation](https://arxiv.org/abs/2003.03473)
- model pruning
  - [An Effective 3D Human Pose Estimation Method Based on Dilated Convolutions for Videos](https://ieeexplore.ieee.org/document/8961588)
- parameter quantization
  - [MobileHumanPose: Toward real-time 3D human pose estimation in mobile devices](https://openaccess.thecvf.com/content/CVPR2021W/MAI/papers/Choi_MobileHumanPose_Toward_Real-Time_3D_Human_Pose_Estimation_in_Mobile_Devices_CVPRW_2021_paper.pdf)