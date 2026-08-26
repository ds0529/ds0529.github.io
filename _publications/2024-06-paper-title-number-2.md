---
title: "Focus on your Geometry: Exploiting the Potential of Multi-Frame Stereo Depth Estimation Pre-training for 3D Object Detection"
collection: publications
link: 'https://ieeexplore.ieee.org/abstract/document/10650924'
date: 2024-06-30
venue: '2024 International Joint Conference on Neural Networks (IJCNN)'
paperurl: 'http://ds0529.github.io/files/IJCNN2024.pdf'
citation_key: ijcnn2024
---

Authors: Zichen Wang, Zhuokun Yao, Jianwei Zhang, Ye Zheng, Zhengyuan Zhang, <u>Shuang Deng</u>, Yajing Liu, Hao Liu

Abstract: Existing camera-based 3D object detection methods yield inaccurate position, scale, and orientation results due to the inherent challenge of ill-posed depth estimation from 2D images. Recent research has demonstrated that pre-training depth estimation from a single frame substantially enhances the quality of camera-based 3D object detection. We hypothesize that integrating multi-view stereo matching technology into the pretraining process can equip the backbone model with superior geometric feature extraction capabilities, thereby further improving 3D object detection performance. Building upon this premise, we propose MVS3D, a novel depth estimation pre-training method for camera-based 3D object detection. MVS3D incorporates a VMS (Video-stream-based Multi-view Stereo) module and a PME (Pose and Motion Estimation) module, which collectively encourage the backbone to explicitly learning 3D geometric information from image streams through stereo matching. Our method enables existing camera-based 3D object detection frameworks to seamlessly integrate our pre-trained backbone weight, thereby enhancing detection performance without necessitating extensive modifications. Extensive experimental results on nuScenes dataset show that loading the pre-trained weight from MVS3D can significantly improve the mean average precision (mAP) and nuScenes detection score (NDS) of both existing single-frame and multi-frame camera-based methods.

<p>Download <a href='http://ds0529.github.io/files/publications/IJCNN2024.pdf'>here</a></p>

<p>Cite {% include cite-link.html key=page.citation_key label="here" %}</p>
