[![Awesome](https://cdn.rawgit.com/sindresorhus/awesome/d7305f38d29fed78fa85652e3a63e154dd8e8829/media/badge.svg)](https://github.com/sindresorhus/awesome)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](https://opensource.org/licenses/MIT)

# One-Sentence_Diffusion_summary
The repo for studying and sharing diffusion models. (Korean) \
Computer Vision with Diffusion models

Update 알람용 디스코드 (업데이트되면 메세지가 날아옵니다.) \
Discord : https://discord.gg/7Wt8DqpsPU  (A message will be sent when updated)

## New updated

<details>
  <summary>In the last month</summary>
  
  ### 09 Jan 2023
  
  **Scalable Diffusion Models with Transformers** \
  *William Peebles, Saining Xie* \
  arXiv 2022. [[Paper](https://arxiv.org/abs/2212.09748)] [[Project page](https://www.wpeebles.com/DiT)] [[Git](https://github.com/facebookresearch/DiT)]\
  [Submitted on 19 Dec 2022] \
  트랜스포머를 사용해서 이미지넷에서 SOTA. 기본적으로 VAE의 latent 상에서의 Diffusion이며, t랑 class를 concat 해서 mlp 하나 태우고, adaLN 을 적용시킴. 약간 LDM을 transformer로 구현한 느낌. 실험 좋고 내용 간단한데 굳이 열심히 읽어볼 필요는 없는 논문.
  
  
  ### 23 Dec 2022
  
  **Null-text Inversion for Editing Real Images using Guided Diffusion Models** \
  *Ron Mokady, Amir Hertz, Kfir Aberman, Yael Pritch, Daniel Cohen-Or* \
  arXiv 2022. [[Paper](https://arxiv.org/abs/2211.09794)] \
  17 Nov 2022 \
  별도의 model fine-tuning 없이, real image 에 해당하는 null-text를 optimization 하여 prompt2prompt 방식으로 object의 semantic detail을 유지하면서 image editing을 가능하게함. 방법 좋은 결과 좋은. 괜찮은 논문.
  
  **An Image is Worth One Word: Personalizing Text-to-Image Generation using Textual Inversion** \
  *Rinon Gal, Yuval Alaluf, Yuval Atzmon, Or Patashnik, Amit H. Bermano, Gal Chechik, Daniel Cohen-Or* \
  arXiv 2022. ICLR2023 submission [[Paper](https://arxiv.org/abs/2208.01618)] \
  [Submitted on 2 Aug 2022] \
  이미지 3~5장을 S* 라는 문자로 inversion한다. GAN inversion과 유사. 이미지를 생성하는 과정에서 나오는 노이즈와 given image를 inversion 하는 과정에서 나오는 노이즈간의 MSE loss를 사용하여 "A photo of S*" 라는 prompt의 S*에 해당하는 토큰을 직접 optimize한다.
  
  **Optimizing Prompts for Text-to-Image Generation** \
  *Yaru Hao, Zewen Chi, Li Dong, Furu Wei* \
  arXiv 2022. [[Paper](https://arxiv.org/abs/2212.09611)][[Demo page](https://huggingface.co/spaces/microsoft/Promptist)][[Git](https://github.com/microsoft/LMOps/tree/main/promptist)] \
  [Submitted on 19 Dec 2022] \
  "A white knight riding a black horse." -> "a white knight riding a black horse, intricate, elegant, highly detailed, digital painting, artstation, concept art, sharp focus, illustration, by justin gerard and artgerm, 8 k" 텍스트 뒤에 붙는 글자들을 강화학습으로 만들어낸다. GPT모델을 prompt pair로 fintuning하여 policy 모델로 사용한다. 이미지의 심미적, 텍스트 반영을 기반으로 reward를 주는 형태로 짜여져 있다.
  
  **Human Motion Diffusion Model** \
  *Guy Tevet, Sigal Raab, Brian Gordon, Yonatan Shafir, Daniel Cohen-Or, Amit H. Bermano* \
  arXiv 2022. [[Paper](https://arxiv.org/abs/2209.14916)][[Project page](https://guytevet.github.io/mdm-page/)] \
  [Submitted on 29 Sep 2022] \
  사람의 Motion을 생성하는데 Diffusion을 사용. spatial한 정보가 필요없기에 Transformer를 사용하였다. 이 때 모든 xt에 대하여 모델은 바로 x0를 예측한다. classifier-free guidance를 10%로 사용하였으며 이를 통해 text-to-motion 생성이 가능하다.
  
  **PhysDiff: Physics-Guided Human Motion Diffusion Model** \
  *Ye Yuan, Jiaming Song, Umar Iqbal, Arash Vahdat, Jan Kautz* \
  arXiv 2022. [[Paper](https://arxiv.org/abs/2212.02500)] \
  [Submitted on 5 Dec 2022] \
  Motion Diffusion Model에서 발이 떨어지는 문제를 해결하기 위해 강화학습을 사용함. 자세한건 패스..

  
  ### 7 Dec 2022
  
  **Paint by Example: Exemplar-based Image Editing with Diffusion Models** \
  *Binxin Yang, Shuyang Gu, Bo Zhang, Ting Zhang, Xuejin Chen, Xiaoyan Sun, Dong Chen, Fang Wen* \
  CVPR2023 submission. [[Paper](https://arxiv.org/abs/2211.13227)] \
  [Submitted on 23 Nov 2022] \
  유저가 지정한 영역에 컨디션으로 주어진 이미지의 semantic을 생성한 논문. 1. StableDiffusion으로 init 2. 이미지의 메인 오브젝트 패치를 떼어내고, CLIP 이미지 인코더에 augmentation해서 넣어준다. 이 때 CLIP을 1024까지 임베딩을 시켜버리고, 이걸 다시 리니어레이어 몇개 통과시켜서 컨디션으로 넣어줌. 3. 2번에 따라서 학습.  결과 좋음. 방법 좋음. 논문 잘 읽힘. 괜찮은 논문.
  
  **DiffEdit: Diffusion-based semantic image editing with mask guidance** \
*Guillaume Couairon, Jakob Verbeek, Holger Schwenk, Matthieu Cord* \
Submitted to ICLR2023. [[Paper](https://arxiv.org/abs/2210.11427)] \
20 Oct 2022 \
Reference text와 query text가 주어졌을때 두 텍스트를 적용했을때의 noise estimates 차이로 마스크를 생성 - 생성한 마스크를 통해 DDIM decoding과정에서 encoding된 것과 적절히 합쳐서 text 부분만 edit하는 간단한 방법.
  
  **DiffRF: Rendering-Guided 3D Radiance Field Diffusion** \
  *Norman Müller, Yawar Siddiqui, Lorenzo Porzi, Samuel Rota Bulò, Peter Kontschieder, Matthias Nießner*\
  arXiv 2022. [[Paper](https://arxiv.org/abs/2212.01206)] \
  2 Dec 2022 \
  Diffusion 으로 3d radiacne field generation한 논문. 이전에 DreamFusion이나 GAUDI 와 같이 diffusion으로 3D generation하는 works이 있었지만, 3d unet 을 활용하여 3d Radiance field를 직접 denoise하는 것은 이 연구가 처음. 모든 sample을 voxel grid로 만들어야하는 precomputation이 필요하다. quality를 높이기 위해 3d radiance field의 denoising network 학습이외에 render 된 2d image 상에서의 RGB loss와 마찬가지로 rendered image를 처리하는 CNN network를 추가하였다.
  
  
  **Maximum Likelihood Training of Implicit Nonlinear Diffusion Models**\
  *Dongjun Kim, Byeonghu Na, Se Jung Kwon, Dongsoo Lee, Wanmo Kang, Il-Chul Moon*\
  NeurIPS22. [[Paper](https://arxiv.org/abs/2205.13699)]\
  27 May 2022 \
  Normalizing flow의 invertible한 성질을 적용하여, data adatible 한 nonlinear diffusion process를 implicit하게 학습. FID 성능을 올림.
  
  
  
  

</details>


## Contents
- [Resources](#resources)
  - [Introductory Posts](#introductory-posts)
  - [Introductory Papers](#introductory-papers)
  - [Introductory Videos](#introductory-videos)
- [Papers](#papers)
  - [Must-read papers](#must-read-papers)
  - [Connection with other framworks](#connection-with-other-framworks)
  - [Image Generation](#image-generation)
  - [Image space guidance sampling](#image-space-guidance-sampling)
  - [Classifier guidance sampling](#classifier-guidance-sampling)
  - [Image Editing](#image-editing)
  - [Text-focused](#text-focused)
  - [Fast Sampling](#fast-sampling)
  - [Video Generation](#video-generation)
  - [3D](#3d)
  - [기타](#기타)
    
  
# Resources
## Introductory Posts

**What are Diffusion Models?** \
[[Website](https://lilianweng.github.io/lil-log/2021/07/11/diffusion-models.html)] \
11 Jul 2021 \
전반적인 Generative 모델에 대한 소개와 Diffusion model의 수식적인 정리가 깔끔하게 되어있음. 복숭아 아이콘 사이트.

**Generative Modeling by Estimating Gradients of the Data Distribution** \
[[Website](https://yang-song.github.io/blog/2021/score/)] \
5 May 2021 \
Yang Song 블로그. Score-based models를 기존의 MCMC 부터 시작하여 차근차근 훑어줌. 추천.

## Introductory Papers

**Understanding Diffusion Models: A Unified Perspective** \
*Calvin Luo* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2208.11970)] \
25 Aug 2022 \
기존 Diffusion 논문들의 notation이 다 달라서 힘든데, 이 논문이 전체적인 정리를 싹 다 해놓음. 구글에서 썼고, VAE에서 부터 classifier guidance까지 수식적으로도 총정리 해둠. 수학 증명이 안되는 부분이 있다면 참고하기 좋음.

**A Survey on Generative Diffusion Model** \
*Hanqun Cao, Cheng Tan, Zhangyang Gao, Guangyong Chen, Pheng-Ann Heng, Stan Z. Li* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2209.02646)] \
6 Sep 2022 \
Survey.

**Diffusion Models: A Comprehensive Survey of Methods and Applications** \
*Ling Yang, Zhilong Zhang, Shenda Hong, Wentao Zhang, Bin Cui* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2209.00796)] \
9 Sep 2022 \
Survey.

## Introductory Videos
*이상윤*\
[[Youtube channel](https://www.youtube.com/channel/UC0xHseqVPJCGy1oNIfJA4VQ)] \
디퓨전관련 스터디 영상을 업로드 해준 채널. 아쉽게도 2022.08 즈음부터 멈추긴 했지만 한국말 설명이라 찾아보면 좋음.

*디퓨전 전반적인 정리영상*\
[[Youtube](https://youtu.be/uFoGaIVHfoE)] \
제가 발표한 영상입니다. DDPM, DDIM, ADM-G, NCSN, Score-based models, 그리고 여러 모델들의 흐름과 수학을 총정리 했습니다.

# Papers


## Must-read papers

**Deep Unsupervised Learning using Nonequilibrium Thermodynamics** \
*Jascha Sohl-Dickstein, Eric A. Weiss, Niru Maheswaranathan, Surya Ganguli* \
ICML 2015. [[Paper](https://arxiv.org/abs/1503.03585)] [[Github](https://github.com/Sohl-Dickstein/Diffusion-Probabilistic-Models)] \
2 Mar 2015 \
Diffusion의 시작. Reverse diffusion process를 통해 데이터를 복구하는 방식을 제안함. 각각의 time step 별 가우시안 분포를 reparameterize 하는 방식의 시초라고 할 수 있다. 하지만 안읽어도 큰 문제는 없음. (DDPM을 이해했다는 전제하에)

**Denoising Diffusion Probabilistic Models** \
*Jonathan Ho, Ajay Jain, Pieter Abbeel* \
NeurIPS 2020. [[Paper](https://arxiv.org/abs/2006.11239)] [[Github](https://github.com/hojonathanho/diffusion)] [[Github2](https://github.com/pesser/pytorch_diffusion)] \
19 Jun 2020 \
DDPM. 읽어야 함. xt를 x0를 가지고 바로 샘플링하는 방식 제안, Loss를 simple하게 만들어도 잘 된다는 것을 보임.

**Improved Denoising Diffusion Probabilistic Models** \
*Alex Nichol<sup>1</sup>, Prafulla Dhariwal<sup>1</sup>* \
ICLR 2021. [[Paper](https://arxiv.org/abs/2102.09672)] [[Github](https://github.com/openai/improved-diffusion)] \
18 Feb 2021 \
사실 필수로 읽어야 하는 논문까지는 아님. 아키텍처의 변화와 스케줄링의 변화를 줌. 하지만 여기저기서 많이 등장하므로 읽어두면 좋음. 중요도는 그리 높지 않음.

**Diffusion Models Beat GANs on Image Synthesis** \
*Prafulla Dhariwal<sup>1</sup>, Alex Nichol<sup>1</sup>* \
arXiv 2021. [[Paper](https://arxiv.org/abs/2105.05233)] [[Github](https://github.com/openai/guided-diffusion)] \
11 May 2021 \
Classifier guidance 방식을 제안한 논문. 정말 많이 쓰이고 있으며 읽어두는 것을 추천.

**Denoising Diffusion Implicit Models**  \
*Jiaming Song, Chenlin Meng, Stefano Ermon* \
ICLR 2021. [[Paper](https://arxiv.org/abs/2010.02502)] [[Github](https://github.com/ermongroup/ddim)] \
6 Oct 2020 \
Marcov chain을 끊고 Deterministic 하게 만든 논문. 수식적으로 복잡하나, 잘 이해해둬야 하는 필수 논문 중 하나.

**Generative Modeling by Estimating Gradients of the Data Distribution** \
*Yang Song, Stefano Ermon* \
NeurIPS 2019. [[Paper](https://arxiv.org/abs/1907.05600)] [[Project](https://yang-song.github.io/blog/2021/score/)] [[Github](https://github.com/ermongroup/ncsn)] \
12 Jul 2019 \
Score-based models의 시초격인 논문. 결국 VE-SDE를 이해하기 위해선 이 논문이 선행되어야 함.

**Score-Based Generative Modeling through Stochastic Differential Equations** \
*Yang Song, Jascha Sohl-Dickstein, Diederik P. Kingma, Abhishek Kumar, Stefano Ermon, Ben Poole* \
ICLR 2021 (Oral). [[Paper](https://arxiv.org/abs/2011.13456)] [[Github](https://github.com/yang-song/score_sde)] \
26 Nov 2020 \
Score-based 와 DDPM을 SDE로 묶어낸 논문. 매우 잘 써진 논문이라 생각하며, 필수적으로 읽어봐야 한다고 생각.

**Variational Diffusion Models** \
*Diederik P. Kingma, Tim Salimans, Ben Poole, Jonathan Ho* \
NeurIPS 2021. [[Paper](https://arxiv.org/abs/2107.00630)] [[Github](https://github.com/revsic/jax-variational-diffwave)] \
1 Jul 2021 \
필수라고 적어놨지만 필자도 아직 안읽었습니다.. SNR을 정의 내린 논문. 그리고 수식적으로 잘 정리된 논문. 조만간 읽고 업데이트 하겠습니다.

**Elucidating the Design Space of Diffusion-Based Generative Models** \
*Tero Karras, Miika Aittala, Timo Aila, Samuli Laine* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2206.00364)] \
1 Jun 2022 \
실험적으로 Diffusion model을 어떻게 설계하는 것이 좋은지 잘 정리해놓은 논문.

**Classifier-Free Diffusion Guidance** \
*Jonathan Ho, Tim Salimans* \
NeurIPS Workshop 2021. [[Paper](https://arxiv.org/abs/2207.12598)] \
28 Sep 2021 \
GAN으로 치면 condition GAN. 외부에서 classifier로 guidance를 주는 대신, UNet에 바로 컨디션을 꽂아줌. 이 때 수식을 classifier guidance랑 같아지도록 전개, 잘 됨. 현재 잘 되는 대부분의 모델들은 free guidance 방식으로 학습됨.

## Image Generation

**Score-Based Generative Modeling with Critically-Damped Langevin Diffusion** \
*Tim Dockhorn, Arash Vahdat, Karsten Kreis* \
arXiv 2021. [[Paper](https://arxiv.org/abs/2112.07068)] [[Project](https://nv-tlabs.github.io/CLD-SGM/)] \
14 Dec 2021 \
Nvidia에서 낸 논문으로 기존에 Score-based에 velocity 축을 하나 더 만들어서 수렴도 잘 되고 학습도 빠르게 만듬. 수학적으로 잘 정리되어있어서 좋은 논문.

**Cascaded Diffusion Models for High Fidelity Image Generation** \
*Jonathan Ho<sup>1</sup>, Chitwan Saharia<sup>1</sup>, William Chan, David J. Fleet, Mohammad Norouzi, Tim Salimans* \
arXiv 2021. [[Paper](https://arxiv.org/abs/2106.15282)] [[Project](https://cascaded-diffusion.github.io/)] \
30 May 2021 \
이미지 resolution을 키워가면서 생성하는 방법 소개.

**Soft Truncation: A Universal Training Technique of Score-based Diffusion Model for High Precision Score Estimation**\
*Dongjun Kim, Seungjae Shin, Kyungwoo Song, Wanmo Kang, Il-Chul Moon*\
icml 2022. [[Paper](https://arxiv.org/abs/2106.05527)] \
11 Jun 2022 \
이미지를 좀 더 잘 뽑아내는 방법 소개.

**Your ViT is Secretly a Hybrid Discriminative-Generative Diffusion Model** \
*Xiulong Yang<sup>1</sup>, Sheng-Min Shih<sup>1</sup>, Yinlin Fu, Xiaoting Zhao, Shihao Ji* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2208.07791)] [[Github](https://github.com/sndnyang/Diffusion_ViT)] \
16 Aug 2022 \
ViT를 가지고 Diffusion을 만들었지만 classification도 같이 한다는 것이 중요포인트. 그러나 이미지 생성 성능은 그리 좋지 못함. 다만 기존 하이브리드모델 중에선 제일 좋은듯.

**Progressive Deblurring of Diffusion Models for Coarse-to-Fine Image Synthesis, Sangyun Lee et al., 2022** \
*Sangyun Lee, Hyungjin Chung, Jaehyeon Kim, Jong Chul Ye* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2207.11192?context=cs)] [[Project](https://github.com/sangyun884/blur-diffusion)] \
16 Jul 2022 \
상윤좌의 논문으로, diffusion models의 generation과정이 coarse-to-fine이 아니라 holistically 생성되는것에 주목하여 이를 해결하고자 blur kernel을 삽입하여 train.
Noise에 가까울 수록 low frequency 정보만 남도록 gaussian kernel 통과시키고, 결과적으로 low freqeucny(content)정보부터 미리 생성하고, high freqeuncy(style, detail)을 나중에 생성하도록 explicit bias를 줌.

**Soft Diffusion: Score Matching for General Corruptions, Giannis Daras et al., 2022**  \
*Giannis Daras, Mauricio Delbracio, Hossein Talebi, Alexandros G. Dimakis, Peyman Milanfar* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2209.05442)] \
12 Sep 2022 \
gaussian noise말고 blur까지 씌우면 fid가 더 좋아진다 + new sampling method (momentum sampling)제안, noise(blur) scheduling 제안\

**Maximum Likelihood Training of Implicit Nonlinear Diffusion Models**\
*Dongjun Kim, Byeonghu Na, Se Jung Kwon, Dongsoo Lee, Wanmo Kang, Il-Chul Moon*\
NeurIPS22. [[Paper](https://arxiv.org/abs/2205.13699)]\
27 May 2022 \
Normalizing flow의 invertible한 성질을 적용하여, data adatible 한 nonlinear diffusion process를 implicit하게 학습. FID 성능을 올림.\

**Scalable Diffusion Models with Transformers** \
*William Peebles, Saining Xie* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2212.09748)] [[Project page](https://www.wpeebles.com/DiT)] [[Git](https://github.com/facebookresearch/DiT)]\
[Submitted on 19 Dec 2022] \
트랜스포머를 사용해서 이미지넷에서 SOTA. 기본적으로 VAE의 latent 상에서의 Diffusion이며, t랑 class를 concat 해서 mlp 하나 태우고, adaLN 을 적용시킴. 약간 LDM을 transformer로 구현한 느낌. 실험 좋고 내용 간단한데 굳이 열심히 읽어볼 필요는 없는 논문. \


## Connection with other framworks

**Diffusion Autoencoders: Toward a Meaningful and Decodable Representation** \
*Konpat Preechakul, Nattanat Chatthee, Suttisak Wizadwongsa, Supasorn Suwajanakorn* \
CVPR 2022. [[Paper](https://arxiv.org/abs/2111.15640)] [[Project](https://diff-ae.github.io/)] [[Github](https://github.com/phizaz/diffae)] \
30 Dec 2021 \
Diffusion models에 semantic latent를 컨디션으로 주어서 Autoencoder 처럼 만듬. 그래서 latent가 생겼고, manipulation이 가능해짐. 성능 좋고 잘됨.

**DiffuseVAE: Efficient, Controllable and High-Fidelity Generation from Low-Dimensional Latents** \
*Kushagra Pandey, Avideep Mukherjee, Piyush Rai, Abhishek Kumar* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2201.00308)] [[Github](https://github.com/kpandey008/DiffuseVAE)] \
2 Jan 2022 \
제대로 못읽었지만, VAE의 형태를 빌려와서 합친 논문.

**High-Resolution Image Synthesis with Latent Diffusion Models** \
*Robin Rombach<sup>1</sup>, Andreas Blattmann<sup>1</sup>, Dominik Lorenz, Patrick Esser, Björn Ommer* \
arXiv 2021. [[Paper](https://arxiv.org/abs/2112.10752)] [[Github](https://github.com/CompVis/latent-diffusion)] \
20 Dec 2021 \
global AutoEncoder를 학습해서 그 latent 상에서 diffusion을 한 논문. stable-diffusion이 이 논문이다.

**Score-based Generative Modeling in Latent Space** \
*Arash Vahdat<sup>1</sup>, Karsten Kreis<sup>1</sup>, Jan Kautz* \
arXiv 2021. [[Paper](https://arxiv.org/abs/2106.05931)] \
10 Jun 2021
VAE랑 합친 논문. VAE와 Diffusion을 동시에 학습. Diffusion은 VAE의 latent space에서 학습된다.

**Tackling the Generative Learning Trilemma with Denoising Diffusion GANs** \
*Zhisheng Xiao, Karsten Kreis, Arash Vahdat* \
ICLR 2022 (Spotlight). [[Paper](https://arxiv.org/abs/2112.07804)] [[Project](https://nvlabs.github.io/denoising-diffusion-gan)] \
15 Dec 2021 \
GAN으로 특정 timestep의 이미지를 생성하는 방법으로 샘플링도 빠르게, 퀄리티도 좋게 함. GAN+Diffusion.

## Image space guidance sampling

**ILVR: Conditioning Method for Denoising Diffusion Probabilistic Models** \
*Jooyoung Choi, Sungwon Kim, Yonghyun Jeong, Youngjune Gwon, Sungroh Yoon* \
ICCV 2021 (Oral). [[Paper](https://arxiv.org/abs/2108.02938)] [[Github](https://github.com/jychoi118/ilvr_adm)] \
6 Aug 2021 \
이미지를 Low-pass filter 통과시킨 후 합쳐서 원하는 이미지랑 비슷한 이미지 생성

**RePaint: Inpainting using Denoising Diffusion Probabilistic Models** \
*Andreas Lugmayr, Martin Danelljan, Andres Romero, Fisher Yu, Radu Timofte, Luc Van Gool* \
CVPR 2022. [[Paper](https://arxiv.org/abs/2201.09865)] [[Github](https://github.com/andreas128/RePaint)] \
24 Jan 2022 \
Inpainting 논문. 마스크된 영역만 바꿔껴주는 방식을 제안. 여러번 돌리는 방법만 주목해서 보면 됨. 나머진 그닥 필요 없음.

**SDEdit: Image Synthesis and Editing with Stochastic Differential Equations**  \
*Chenlin Meng, Yang Song, Jiaming Song, Jiajun Wu, Jun-Yan Zhu, Stefano Ermon* \
ICLR 2022. [[Paper](https://arxiv.org/abs/2108.01073)] [[Project](https://sde-image-editing.github.io/)] [[Github](https://github.com/ermongroup/SDEdit)] \
2 Aug 2021 \
stroke를 노이즈를 적당히 씌웠다가 샘플링하면 비슷한 색의 real한 이미지를 얻을 수 있음.

## Classifier guidance sampling

**Blended Diffusion for Text-driven Editing of Natural Images** \
*Omri Avrahami, Dani Lischinski, Ohad Fried* \
CVPR 2022. [[Paper](https://arxiv.org/abs/2111.14818)] [[Project](https://omriavrahami.com/blended-diffusion-page/)] [[Github](https://github.com/omriav/blended-diffusion)] \
29 Nov 2021 \
특정 영역에만 CLIP을 가지고 classifier guidance로 text prompt에 맞게 이미지 생성.

**More Control for Free! Image Synthesis with Semantic Diffusion Guidance** \
*Xihui Liu, Dong Huk Park, Samaneh Azadi, Gong Zhang, Arman Chopikyan, Yuxiao Hu, Humphrey Shi, Anna Rohrbach, Trevor Darrell* \
arXiv 2021. [[Paper](https://arxiv.org/abs/2112.05744)] [[Github](https://xh-liu.github.io/sdg/)] \
10 Dec 2021 \
처음으로 text와 image guidance를 둘 다 줄 수 있다고 설명하는 논문. 그런데 둘 다 CLIP을 사용한 classifier guidance이다.

**Generating High Fidelity Data from Low-density Regions using Diffusion Models** \
*Vikash Sehwag, Caner Hazirbas, Albert Gordo, Firat Ozgenel, Cristian Canton Ferrer* \
CVPR2022, arXiv 2022. [[Paper](https://arxiv.org/abs/2203.17260)] \
31 Mar 2022 \
GAN처럼 Discriminator를 하나 사용해서 확률이 낮은 이미지를 뽑도록 유도. Low-density 이미지를 생성함.

**Self-Guided DIffusion Models** \
*Vincent Tao Hu, David W.Zhang, Yuki M.Asano, Gertjan J. Burghouts, Cees G. M. Snoek* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2210.06462)] \
12 Oct 2022 \
Off-the-shelf model들의 사용으로 feature를 뽑아내고 클러스터링을 활용한 self-guided label -> classifier, object detection, semantic segmentation 등으로 guidance를 주어 그에 따르 이미지생성 (시간이 오래 걸릴듯, high resolution 어렵다는 단점)

## Image Editing

**Null-text Inversion for Editing Real Images using Guided Diffusion Models** \
*Ron Mokady, Amir Hertz, Kfir Aberman, Yael Pritch, Daniel Cohen-Or* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2211.09794)] \
17 Nov 2022 \
별도의 model fine-tuning 없이, real image 에 해당하는 null-text를 optimization 하여 prompt2prompt 방식으로 object의 semantic detail을 유지하면서 image editing을 가능하게함. 방법 좋은 결과 좋은. 괜찮은 논문.

**Paint by Example: Exemplar-based Image Editing with Diffusion Models** \
*Binxin Yang, Shuyang Gu, Bo Zhang, Ting Zhang, Xuejin Chen, Xiaoyan Sun, Dong Chen, Fang Wen* \
CVPR2023 submission. [[Paper](https://arxiv.org/abs/2211.13227)] \
[Submitted on 23 Nov 2022] \
유저가 지정한 영역에 컨디션으로 주어진 이미지의 semantic을 생성한 논문. 1. StableDiffusion으로 init 2. 이미지의 메인 오브젝트 패치를 떼어내고, CLIP 이미지 인코더에 augmentation해서 넣어준다. 이 때 CLIP을 1024까지 임베딩을 시켜버리고, 이걸 다시 리니어레이어 몇개 통과시켜서 컨디션으로 넣어줌. 3. 2번에 따라서 학습.  결과 좋음. 방법 좋음. 논문 잘 읽힘. 괜찮은 논문.

**Denoising Diffusion Restoration Models** \
*Bahjat Kawar, Michael Elad, Stefano Ermon, Jiaming Song* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2201.11793)] \
27 Jan 2022 \
이미지 자체가 하자가 있다고 생각하고 특정 행렬 곱으로 노이즈나.. 크롭이나.. 그런걸 나타낼 수 있다면 원본을 복구하는 방식 제안.

**Palette: Image-to-Image Diffusion Models** \
*Chitwan Saharia, William Chan, Huiwen Chang, Chris A. Lee, Jonathan Ho, Tim Salimans, David J. Fleet, Mohammad Norouzi* \
NeurlPS 2022. [[Paper](https://arxiv.org/abs/2111.05826)] \
10 Nov 2021 \
별거 안하고 그냥 튜닝해서 모델 하나로 4가지 task에서 SOTA 달성.

**DiffEdit: Diffusion-based semantic image editing with mask guidance** \
*Guillaume Couairon, Jakob Verbeek, Holger Schwenk, Matthieu Cord* \
Submitted to ICLR2023. [[Paper](https://arxiv.org/abs/2210.11427)] \
20 Oct 2022 \
Reference text와 query text가 주어졌을때 두 텍스트를 적용했을때의 noise estimates 차이로 마스크를 생성 - 생성한 마스크를 통해 DDIM decoding과정에서 encoding된 것과 적절히 합쳐서 text 부분만 edit하는 간단한 방법.

**DiffusionCLIP: Text-guided Image Manipulation Using Diffusion Models** \
*Gwanghyun Kim, Jong Chul Ye* \
CVPR 2022. [[Paper](https://arxiv.org/abs/2110.02711)] \
6 Oct 2021 \
CLIP을 가지고 model을 finetuning해서 원하는 attribute로 변환하는 논문.

**TEXT-GUIDED DIFFUSION IMAGE STYLE TRANSFER WITH CONTRASTIVE LOSS FINE-TUNING** \
*Anonymous authors* \
Submitted to ICLR2023. [[Paper](https://openreview.net/forum?id=iJ_E0ZCy8fi)] \
30 Sept 2022 \
CLIP (global + directional) & CUT loss (UNet featuremap들을 패치로 쪼개서 contrastive loss)를 사용해서 stylestransfer.

**Plug-and-Play Diffusion Features for Text-Driven Image-to-Image Translation** \
*Narek Tumanyan, Michal Geyer, Shai Bagon, Tali Dekel* \
CVPR 2023 Submission / preprint [[Paper](https://arxiv.org/abs/2211.12572)] [[Project page](https://pnp-diffusion.github.io)] \
[Submitted on 22 Nov 2022]
Stable Diffusion의 4th layer의 featuremap과 4-11th laeyr의 self attention Q,K 값을 injection 하여 real image의 structure를 유지하면서 text guided로 I2I translation을 가능하게 함. Diffusion model은 freeze, feature만 만져서 성공적으로 editing. 좋은 접근.

**Diffusion Models already have a Semantic Latent Space** \
*Mingi Kwon, Jaeseok Jeong, Youngjung Uh* \
ICLR 2023 Submission / preprint [[Paper](https://arxiv.org/abs/2210.10960)] [[Project page](https://kwonminki.github.io/Asyrp/)] \
[Submitted on 20 Oct 2022] \
DDIM의 샘플링 공식 중 predicted x0 부분만 바꿔주면 U-Net의 bottle-neck 부분을 semantic latent space로 쓸 수 있음을 보여준 논문. Asyrp을 제안함. 잘됩니당 좋은 논문입니당 읽어주세요.




## Text-focused

**Optimizing Prompts for Text-to-Image Generation** \
*Yaru Hao, Zewen Chi, Li Dong, Furu Wei* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2212.09611)][[Demo page](https://huggingface.co/spaces/microsoft/Promptist)][[Git](https://github.com/microsoft/LMOps/tree/main/promptist)] \
[Submitted on 19 Dec 2022] \
"A white knight riding a black horse." -> "a white knight riding a black horse, intricate, elegant, highly detailed, digital painting, artstation, concept art, sharp focus, illustration, by justin gerard and artgerm, 8 k" 텍스트 뒤에 붙는 글자들을 강화학습으로 만들어낸다. GPT모델을 prompt pair로 fintuning하여 policy 모델로 사용한다. 이미지의 심미적, 텍스트 반영을 기반으로 reward를 주는 형태로 짜여져 있다.

**An Image is Worth One Word: Personalizing Text-to-Image Generation using Textual Inversion** \
*Rinon Gal, Yuval Alaluf, Yuval Atzmon, Or Patashnik, Amit H. Bermano, Gal Chechik, Daniel Cohen-Or* \
arXiv 2022. ICLR2023 submission [[Paper](https://arxiv.org/abs/2208.01618)] \
[Submitted on 2 Aug 2022] \
이미지 3~5장을 S* 라는 문자로 inversion한다. GAN inversion과 유사. 이미지를 생성하는 과정에서 나오는 노이즈와 given image를 inversion 하는 과정에서 나오는 노이즈간의 MSE loss를 사용하여 "A photo of S*" 라는 prompt의 S*에 해당하는 토큰을 직접 optimize한다.


## Fast Sampling

**Learning Fast Samplers for Diffusion Models by Differentiating Through Sample Quality** \
*Daniel Watson, William Chan, Jonathan Ho, Mohammad Norouzi* \
ICLR 2022. [[Paper](https://openreview.net/forum?id=VFBjuF8HEp)]  \
11 Feb 2022 \
Pre-trained을 fine-tunning 하지 않고 step#를 줄여서 빠르게 sampling 하면서도 FID/IS 를 최대한 유지할 수 있는 방법제시,
diffusion의 object function(ELBO) term을 무시하고, step과 step사이에 sampling하는 paremeter들만 KID loss 를 줘서 train.

**Pseudo Numerical Methods for Diffusion Models on Manifolds** \
*Luping Liu, Yi Ren, Zhijie Lin, Zhou Zhao* \
ICLR 2022 Poster [[Paper](https://arxiv.org/abs/2202.09778)] \
Submitted on 20 Feb 2022  \
이전 numerical ODE의 방식이 DDPM의 sampling manifold를 제대로 반영하지 못함을 지적, DDIM과 high-order numerical sampling의 장점을 결합하여 새로운 sampling 방식을 제시.
stable diffusion에서 사용된 sampling방식이고 성능이 좋다.

**gDDIM: Generalized denoising diffusion implicit models** \
*Qinsheng Zhang, Molei Tao, Yongxin Chen* \
ICLR 2023 Submission / preprint [[Paper](https://arxiv.org/abs/2206.05564)] \
[Submitted on 11 Jun 2022] \
DDPM, DDIM, 등등을 모두 SDE의 형태로 전환, Blur Diffusion이나 Critically-Damped Langevin Diffusion 까지도 SDE로 표현한 뒤, general한 form의 SDE -> DDIM을 만드는 방법을 제안한다. 이를 통해 istropic diffusion models까지 DDIM으로 fast sampling 가능하게 함. 


## Video Generation

**Video Diffusion Models** \
*Jonathan Ho, Tim Salimans, Alexey Gritsenko, William Chan, Mohammad Norouzi, David Fleet* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2204.03458)] \
7 April 2022 \
Diffusion을 이용한 Video generation을 처음으로 한 논문, Video의 길이를 늘리고, quality를 높이는 것에 대한 방법제시.

## 3D

**DiffRF: Rendering-Guided 3D Radiance Field Diffusion** \
*Norman Müller, Yawar Siddiqui, Lorenzo Porzi, Samuel Rota Bulò, Peter Kontschieder, Matthias Nießner*\
arXiv 2022. [[Paper](https://arxiv.org/abs/2212.01206)] \
2 Dec 2022 \
Diffusion 으로 3d radiacne field generation한 논문. 이전에 DreamFusion이나 GAUDI 와 같이 diffusion으로 3D generation하는 works이 있었지만, 3d unet 을 활용하여 3d Radiance field를 직접 denoise하는 것은 이 연구가 처음. 모든 sample을 voxel grid로 만들어야하는 precomputation이 필요하다. quality를 높이기 위해 3d radiance field의 denoising network 학습이외에 render 된 2d image 상에서의 RGB loss와 마찬가지로 rendered image를 처리하는 CNN network를 추가하였다.\


## 기타

**Human Motion Diffusion Model** \
*Guy Tevet, Sigal Raab, Brian Gordon, Yonatan Shafir, Daniel Cohen-Or, Amit H. Bermano* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2209.14916)][[Project page](https://guytevet.github.io/mdm-page/)] \
[Submitted on 29 Sep 2022] \
사람의 Motion을 생성하는데 Diffusion을 사용. spatial한 정보가 필요없기에 Transformer를 사용하였다. 이 때 모든 xt에 대하여 모델은 바로 x0를 예측한다. classifier-free guidance를 10%로 사용하였으며 이를 통해 text-to-motion 생성이 가능하다.

**PhysDiff: Physics-Guided Human Motion Diffusion Model** \
*Ye Yuan, Jiaming Song, Umar Iqbal, Arash Vahdat, Jan Kautz* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2212.02500)] \
[Submitted on 5 Dec 2022] \
Motion Diffusion Model에서 발이 떨어지는 문제를 해결하기 위해 강화학습을 사용함. 자세한건 패스..

## 읽을것들

**Soft Diffusion: Score Matching for General Corruptions** \
*Giannis Daras, Mauricio Delbracio, Hossein Talebi, Alexandros G. Dimakis, Peyman Milanfar* \
arXiv 2022. [[Paper](https://arxiv.org/abs/2209.05442)] \
12 Sep 2022 \
blur써 Sota (안읽음)
