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
  <img src="/images/OpenPoseKeyPoints.png" width="70%" height="70%"></p>
  
2.  Use instance segmentation models for human body parsing like [Self-Correction for Human Parsing(SCHP)](https://arxiv.org/abs/1910.09777) and [Part Grouping Network](https://arxiv.org/abs/1808.00157). Once we have the segmented image, use edge detection technique to identify the edges. Find contours correspoding to cloth part from the edge output. 

<p align="center"><img src="/images/Clothcontour.png" width="70%" height="70%"></p>

## Related works

Some of the best related research work done in this area with there publication is mentioned below. Do checkout these great research for more insights into Virtual faishon TryON. 
1. [GarmentGAN: Photo-realistic Adversarial Fashion Transfer](https://arxiv.org/pdf/2003.01894.pdf)
2. [ACGPN: Towards Photo-Realistic Virtual Try-On by Adaptively Generating↔Preserving Image Content](https://arxiv.org/abs/2003.05863)
3. [Styleposegan: Style and Pose Control for Image Synthesis of Humans from a Single Monocular View](http://gvv.mpi-inf.mpg.de/projects/Styleposegan/)
4. [VOGUE: Try-On by StyleGAN Interpolation Optimization](https://arxiv.org/abs/2101.02285)
5. [VITON: An Image-based Virtual Try-on Network](https://arxiv.org/abs/1711.08447)


## Limitations


<p align="center">
  <img src="/images/artifacts.png" width="60%" height="60%"></p>

## References

1. [Deep Learning for Virtual Try On Clothes – Challenges and Opportunities](https://www.kdnuggets.com/2020/10/deep-learning-virtual-try-clothes.html)
