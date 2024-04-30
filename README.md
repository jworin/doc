
# Pose Eetimation


> **"In contrast to image-based methods, utilizing video-based methods is unequivocally seen as the trajectory of future advancements."**

> one-stage, end-to-end methods represent this field's future direction, in line with other domains in computer vision. 

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
- [Learnable Triangulation of Human Pose](https://arxiv.org/abs/1905.05754)
  - multi-view based approach
- [Lightweight Multi-View 3D Pose Estimation through Camera-Disentangled Representation](https://arxiv.org/abs/2004.02186)

> **Data Lacking**:

- [Unsupervised Adversarial Learning of 3D Human Pose from 2D Joint Locations
](https://arxiv.org/abs/1803.08244)
- [Unsupervised 3D Pose Estimation with Geometric Self-Supervision](https://arxiv.org/abs/1904.04812)
- [ElePose: Unsupervised 3D Human Pose Estimation by Predicting Camera Elevation and Learning Normalizing Flows on 2D Poses](https://arxiv.org/abs/2112.07088)
- [Self-Supervised Learning of 3D Human Pose using Multi-view Geometry](https://arxiv.org/abs/1903.02330)
  - train without any 3d groundtruth
- [3D Human Pose Machines with Self-supervised Learning](https://arxiv.org/abs/1901.03798)
- [Weakly-supervised 3D Human Pose Estimation with Cross-view U-shaped Graph Convolutional Network](https://arxiv.org/abs/2105.10882)
- [CameraPose: Weakly-Supervised Monocular 3D Human Pose Estimation by Leveraging In-the-wild 2D Annotations](https://arxiv.org/abs/2301.02979)
- [AdaptPose: Cross-Dataset Adaptation for 3D Human Pose Estimation by Learnable Motion Generation](https://arxiv.org/abs/2112.11593)

##### video based

> **Single-frame Limitations**:
>
> using continuous data to extract motion features and spatiotemporal relationships -> strengthen pose information

- [3D human pose estimation in video with temporal convolutions and semi-supervised training](https://arxiv.org/abs/1811.11742)
- [3D Human Pose Estimation with Spatial and Temporal Transformers](https://arxiv.org/abs/2103.10455)
- [UniPose: Unified Human Pose Estimation in Single Images and Videos](https://arxiv.org/abs/2001.08095)
- [Multihypothesis transformer for 3d human pose estimation](https://arxiv.org/abs/2111.12707)
  - three stage framework
- [MixSTE: Seq2seq Mixed Spatio-Temporal Encoder for 3D Human Pose Estimation in Video](https://arxiv.org/abs/2203.00859)
- [Temporal Representation Learning on Monocular Videos for 3D Human Pose Estimation](https://arxiv.org/abs/2012.01511)
- [HSTFormer: Hierarchical Spatial-Temporal Transformers for 3D Human Pose Estimation](https://arxiv.org/abs/2301.07322)
- [3D Human Pose Estimation with Spatio-Temporal Criss-cross Attention](https://openaccess.thecvf.com/content/CVPR2023/papers/Tang_3D_Human_Pose_Estimation_With_Spatio-Temporal_Criss-Cross_Attention_CVPR_2023_paper.pdf)
  - [code](https://github.com/zhenhuat/STCFormer)


> **Real Time Problems**:

 - [Uplift and Upsample: Efficient 3D Human Pose Estimation with Uplifting Transformers](https://arxiv.org/abs/2210.06110)
 - [MixSynthFormer: A Transformer Encoder-like Structure with Mixed Synthetic
Self-attention for Efficient Human Pose Estimation](https://openaccess.thecvf.com/content/ICCV2023/papers/Sun_MixSynthFormer_A_Transformer_Encoder-like_Structure_with_Mixed_Synthetic_Self-attention_for_ICCV_2023_paper.pdf)
    - reduced the complexity of attention calculation in Transformers through spatiotemporal sparse sampling


> **Body Structure Understanding**:

- [Motion Guided 3D Pose Estimation from Videos](https://arxiv.org/abs/2004.13985)
- [Anatomy-aware 3D Human Pose Estimation with Bone-based Pose Decomposition](https://arxiv.org/abs/2002.10322)
- [Boosting Monocular 3D Human Pose Estimation With Part Aware Attention](https://ieeexplore.ieee.org/document/9798770)

> **Occlusion**:

- [Occlusion-Aware Networks for 3D Human Pose Estimation in Video](https://openaccess.thecvf.com/content_ICCV_2019/papers/Cheng_Occlusion-Aware_Networks_for_3D_Human_Pose_Estimation_in_Video_ICCV_2019_paper.pdf)
  

> **Data Lacking**:
>
> annotated 3D videos are relatively scarce

- [Towards Alleviating the Modeling Ambiguity of Unsupervised Monocular 3D
Human Pose Estimation](https://openaccess.thecvf.com/content/ICCV2021/papers/Yu_Towards_Alleviating_the_Modeling_Ambiguity_of_Unsupervised_Monocular_3D_Human_ICCV_2021_paper.pdf)
  - unsupervised
- [Weakly-Supervised Discovery of Geometry-Aware Representation for 3D Human Pose Estimation](https://arxiv.org/abs/1903.08839)
- [P-STMO: Pre-Trained Spatial Temporal Many-to-One Model for 3D Human Pose Estimation](https://arxiv.org/abs/2203.07628)
  - randomly mask body joints in spatial and temporal domains


#### multi person

*same like 2D pose*, in multiple person scenarios, the method can be separated into:

- Top-Down: detection + estimation
- Bottom-Up: estimation + association

Moreover:

Dual:
- [Dual networks based 3D Multi-Person Pose Estimation from Monocular Video](https://arxiv.org/abs/2205.00748)
  - finally fed into a network to obtain final 3D pose

Single Stage:
- [Single-Stage is Enough: Multi-Person Absolute 3D Pose Estimation](https://openaccess.thecvf.com/content/CVPR2022/papers/Jin_Single-Stage_Is_Enough_Multi-Person_Absolute_3D_Pose_Estimation_CVPR_2022_paper.pdf)

##### Top-Down

~~*我觉得这几篇都可以看一下*~~

- [AlphaPose: Whole-Body Regional Multi-Person Pose Estimation and Tracking in Real-Time](https://arxiv.org/abs/2211.03375)
- [Cross-View Tracking for Multi-Human 3D Pose Estimation at over 100 FPS](https://arxiv.org/abs/2003.03972)
  - real-time from videos + **multi-camera setup**
- [VoxelTrack: Multi-Person 3D Human Pose Estimation and Tracking in the Wild](https://arxiv.org/abs/2108.02452)
  - based on voxel
- [PandaNet : Anchor-Based Single-Shot Multi-Person 3D Pose Estimation](https://arxiv.org/abs/2101.02471)
  - based on anchor?
- [Camera Distance-aware Top-down Approach for 3D Multi-person Pose Estimation from a Single RGB Image](https://arxiv.org/abs/1907.11346)
  - no ground truth needed?

#### Bottom-Up

~~*似乎都不是纯关键点做的了，都沾点别的表示方法*~~
这边有几篇也可以看一下的，都挺经典的

- [Deep Network for the Integrated 3D Sensing of Multiple People in Natural Images](https://proceedings.neurips.cc/paper/2018/hash/6a6610feab86a1f294dbbf5855c74af9-Abstract.html)
  - MubyNet 2018, probably the typical method in 3d
- [Compressed Volumetric Heatmaps for Multi-Person 3D Pose Estimation](https://arxiv.org/abs/2004.00329)
  - high-resolution volumetric heatmap -> performance 
  - autoencoder -> compress the size of representation
- [HMOR: Hierarchical Multi-Person Ordinal Relations for Monocular Multi-Person 3D Pose Estimation](https://arxiv.org/abs/2008.00206)
  - corse to fine architecture
- [Single-Shot Multi-Person 3D Pose Estimation From Monocular RGB](https://arxiv.org/abs/1712.03453)
  - occlusion-robust
- [Single-shot 3D multi-person pose estimation in complex images](https://arxiv.org/abs/1911.03391)
  - based on PandaNet, no bounding-box, extends Stacked Hourglass Network
- [LCR-Net++: Multi-person 2D and 3D Pose Detection in Natural Images](https://arxiv.org/abs/1803.00455)
  - address the issue of occlusion
  - "integrates adjacent pose hypotheses to predict the multi-person 2D and 3D poses without approximating initial human localization when a person is partially occluded or truncated by the image boundaries."
  - 引用数挺高，可以看一下的
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