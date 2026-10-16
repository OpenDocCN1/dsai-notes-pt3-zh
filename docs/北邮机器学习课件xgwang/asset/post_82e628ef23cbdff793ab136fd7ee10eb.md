
## Related works

[14] Saito K, Ushiku Y, Harada T. Asymmetric tri-training for unsupervised domain adaptation. In ICML 2017.

[15] Chen C, Xie W, Xu T, et al. Progressive Feature Alignment for Unsupervised Domain Adaptation. arXiv preprint arXiv:1811.08585, 2018.

[16] M. Wang and W. Deng. Deep face recognition: A survey. arXiv preprint arXiv:1804.06655, 2018. 1, 2, 3

[17] Wang M, Deng W, Hu J, et al. Racial Faces in-the-Wild: Reducing Racial Bias by Deep Unsupervised Domain Adaptation. arXiv preprint arXiv:1812.00194, 2018.

[18] D. Yi, Z. Lei, S. Liao, and S. Z. Li. Learning face representation from scratch. arXiv preprint arXiv:1411.7923, 2014.

[19] Q. Cao, L. Shen, W. Xie, O. M. Parkhi, and A. Zisserman. Vggface2: A dataset for recognising faces across pose and age. arXiv preprint arXiv:1710.08092, 2017.

[20] Y. Guo, L. Zhang, Y. Hu, X. He, and J. Gao. Ms-celeb-1m: A dataset and benchmark for large-scale face recognition. In ECCV, pages 87–102. Springer, 2016.

[21] G. B. Huang, M. Ramesh, T. Berg, and E. Learned-Miller. Labeled faces in the wild: A database for studying face recognition in unconstrained environments. Technical report, Technical Report 07-49, University of Massachusetts, Amherst, 2007

[22] B. F. Klare, B. Klein, E. Taborsky, A. Blanton, J. Cheney, K. Allen, P. Grother, A. Mah, and A. K. Jain. Pushing the frontiers of unconstrained face detection and recognition: Iarpa janus benchmark a. In CVPR, pages 1931–1939, 2015.

[23] A. Nech and I. Kemelmacher-Shlizerman. Level playing field for million scale face recognition. In CVPR, pages 3406–3415. IEEE, 2017.

## PyTorch

- 上手简单
- 调试方便
- 文档友好

## 用PyTorch进行人脸分类

- 任务：正确分类10M人脸图片，包含100K人
- 步骤
  - 1.准备数据集
  - 2.搭建网络
  - 3.编写训练、验证代码

## 数据集

- torchvision.datasets
  - MNIST
  - Fashion-MNIST
  - EMNIST
  - COCO
  - LSUN
  - ImageFolder
  - DatasetFolder
  - Imagenet-12
  - CIFAR
  - STL10
  - SVHN
  - PhotoTour

```
root/dog/xxx.png
root/dog/xxy.png
root/dog/xxz.png

root/cat/123.png
root/cat/nsdf3.png
root/cat/asd932_.png
```

- MS-Celeb1M
  - ID1
  - ID2
    - 1.jpg
    - 2.jpg
    - 3.jpg

## 数据集-ImageFolder

```
import torch
import torchvision.datasets as datasets
import torchvision.transforms as transforms

traindir = '/ssd/Dataset/MS-Celeb-1M'
normalize = transforms.Normalize(mean=[0.485, 0.456, 0.406])
train_dataset = datasets.ImageFolder(
    traindir,
    transforms.Compose([
        transforms.Resize(224),
        transforms.CenterCrop(224),
        transforms.RandomHorizontalFlip(),
        transforms.ToTensor(),
        normalize,
    ])
```

## 搭建网络-ResNet

- torchvision.models
  - VGG
  - ResNet
  - Alexnet

```
```python
# 载入现有网络
net = torchvision.models.resnet34(pretrained=False)
# 重写最后一层Fc
net.fc = torch.nn.Linear(512, 100000, bias=False)

# loss公式 以及 更新器
criterion = torch.nn.CrossEntropyLoss()
optimizer = torch.optim.SGD(net.parameters(), args.lr,
                            momentum=args.momentum,
                            weight_decay=args.weight_decay)
```
```

## 编写训练代码

```
26 # 数据读取器
27 train_loader = torch.utils.data.DataLoader(
28     train_dataset, batch_size=args.batch_size, shuffle=(train_sampler is None),
29     num_workers=args.workers, pin_memory=True, sampler=train_sampler)
30 
31 # 开始训练
32 for epoch in range(args.start_epoch, args.epochs):
33     # 训练模式
34     net.train()
35     for i, (input, target) in enumerate(train_loader):
36         # 前向传递, 计算Loss
37         output = net(input)
38         loss = crite
39         # 反向传导, 更新参数
40         optimizer.zero_grad()
41         loss.backward()
42         optimizer.step()
```

## 资源

- 官方文档: https://pytorch.org/docs/stable/index.html
- 官方论坛: https://discuss.pytorch.org/
  - Bug
  - Method
- GitHub: https://github.com/pytorch/
  - Code
  - Example
