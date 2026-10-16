# 编写训练代码

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