# DeepFashionSwap
Virtual Faishon TryON - Fashion(Garment) transfer on a given target from a refrence using Generative Adversarial Networks. 

<p align="center">
  <img src="/images/fswap.png"></p>


Virtual faishon try on is a challenging research area with one of the aim to make shopping more easier. With its development a person can be able to virtually try the desired cloths or faishon items sitting at home. How to acheive it with minimal artifacts, is still a question? Upon several research on different approach I found that the predominant approach to the problem is - To use GAN on combination of key pose of the target person wearing fashion garment along with its segmented image and the Refrence Fashion Item. With this Idea, below I have shown the proposed network architecture for this task.


## Proposed Architecture

In the proposed arcitecture, two Encoders and one decoder is used for the Generator Network. Where one encoder is used for Learning features for the corresponding Fused cloth key points and segmented body parts, Whereas other encoder is used to learn the features from the Reference garment. The below image shows the complete proposed architecture, designed by modifying Chao-Te Chou et al. [PIVTONS](https://winstonhsu.info/pubs/pivtons-virtual-try-on-shoe/) architecture for virtual shoe tryon. 
<p align="center">
  <img src="/images/deepfashionswap.png"></p>

    Other Ideas to for Generator are  - 
    1. Use of StyleGAN2 architecture, where corresponding keypoints and segmented masked part will be sent as input and Feature of Reference cloth will be given  as a Style vector. 
    2. UNet architeccture can be used as a Generator Network.  

### Some Methods to generate pose keypoints

1. Openpose pretrained network can be used to generate COCO keypoints for the cloth part. Like shown in below image. 
    <p align="center">
  <img src="/images/OpenPoseKeyPoints.png"></p>
  
2.  Use instance segmentation models for human body parsing like [Self-Correction for Human Parsing(SCHP)](https://arxiv.org/abs/1910.09777) and [Part Grouping Network](https://arxiv.org/abs/1808.00157). Once we have the segmented image, use edge detection technique to identify the edges. Find contours correspoding to cloth part from the edge output. 

<p align="center"><img src="/images/Clothcontour.png"></p>

## Related works


## Limitations


<p align="center">
  <img src="/images/artifacts.png"></p>

## References
