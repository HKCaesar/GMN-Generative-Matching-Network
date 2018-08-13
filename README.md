# GMN-Generative-Matching-Network
paper：Deep Generative Matching Network for Optical and SAR Image Registration（IEEE GARSS 2018已发表（7.26））   
patent：基于深度卷积GAN的光学和SAR图像配准方法（申请号：201810276562.7）

### 概述    
  不同传感器得到的多源图像之间包含大量的互补信息，对获取完整的图像信息十分有利，主要是应用在图像融合、变换检测、目标识别等领域。     
  图像配准是利用这些异源信息的关键前提，但一般不同传感器由于成像机制不同，得到的图像存在较大的差异，传统的基于SIFT特征点的配准方法无法配准，多源有不同的成像机制，所以图像appearances、结构、表征等差异较大，很难度量他们的相似性。    
  因此就想到利用CNN来挖掘学习异源图像间潜在的关系，实验证明这个方法确实可以配准，但是存在网络训练数据量不足（大多是无标签数据）且缺乏样本多样性的问题。    
  因此我们想到利用GAN来进行训练数据样本扩充（无标签的数据通过GAN得到有标签的训练数据，不需人工标注）。这也是论文的关键创新点。（因为不同传感器采集到的异源图像大多不是可以一一对应的，可能这个传感器拍了这个区域，那个传感器拍了另一个区域，这时候为了数据多样性，可以使用GAN将这两幅图像进行转换得到对应的四幅图像，从而进行数据扩充）。
