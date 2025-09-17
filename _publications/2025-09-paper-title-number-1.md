---
title: "Towards Semi-supervised Dual-modal Semantic Segmentation"
collection: publications
link: 'https://ieeexplore.ieee.org/document/11146486'
date: 2025-09-01
venue: 'IEEE Transactions on Multimedia (TMM)'
paperurl: 'http://ds0529.github.io/files/TMM2025.pdf'
---

Authors: Qiulei Dong, Jianan Li, <u>Shuang Deng</u>

Abstract: With the development of 3D and 2D data acquisition techniques, it has become easy to obtain point clouds and images of scenes simultaneously, which further facilitates dual-modal semantic segmentation. Most existing methods for simultaneously segmenting point clouds and images rely heavily on the quantity and quality of the labeled training data. However, massive point-wise and pixel-wise labeling procedures are time-consuming and labor-intensive. To address this issue, we propose a parallel dual-stream network to handle the semi-supervised dual-modal semantic segmentation task, called PD-Net, by jointly utilizing a small number of labeled point clouds, a large number of unlabeled point clouds, and unlabeled images. The proposed PD-Net consists of two parallel streams (called original stream and pseudo-label prediction stream). The pseudo-label prediction stream predicts the pseudo labels of unlabeled point clouds and their corresponding images. Then, the unlabeled data is sent to the original stream for self-training. Each stream contains two encoder-decoder branches for 3D and 2D data respectively. In each stream, multiple dual-modal fusion modules are explored for fusing the dual-modal features. In addition, a pseudo-label optimization module is explored to optimize the pseudo labels output by the pseudo-label prediction stream. Experimental results on two public datasets demonstrate that the proposed PD-Net not only outperforms the comparative semi-supervised methods but also achieves competitive performances with some fully-supervised methods in most cases.

<p>Download <a href='http://ds0529.github.io/files/TMM2025.pdf'>here</a></p>
