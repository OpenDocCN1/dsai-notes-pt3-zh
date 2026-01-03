# 数据科学导论

> 原文：[`rafalab.dfci.harvard.edu/dsbook-part-2/`](https://rafalab.dfci.harvard.edu/dsbook-part-2/)

1.  前言

1.  序言

统计与预测算法案例研究

# 序言

这是《通过案例研究学习统计与预测算法》（Statistics and Prediction Algorithms Through Case Studies）的第二个部分《数据科学导论》的网站。

第一部分《使用 R 进行数据整理和可视化》的网站[在这里](http://rafalab.dfci.harvard.edu/dsbook-part-1/)。

本书最初是哈佛 X [数据科学系列](https://www.edx.org/professional-certificate/harvardx-data-science) 中使用的课堂笔记的一部分。

可以从 [CRC Press](https://www.routledge.com/Introduction-to-Data-Science-Data-Wrangling-and-Visualization-with-R/Irizarry/p/book/9781032116556) 获取本书第一版的印刷版，该版结合了两个部分。

可以从 [Leanpub](https://leanpub.com/datasciencebook) 获取 2019 年 10 月 24 日版本的免费 PDF，该版本结合了两个部分。

生成本书的 Quarto 代码可在 [GitHub](https://github.com/rafalab/dsbook-part-2) 上找到。

本作品根据 Creative Commons Attribution-NonCommercial-ShareAlike 4.0 国际 [CC BY-NC-SA 4.0](https://creativecommons.org/licenses/by-nc-sa/4.0) 许可协议授权。

我们在 X 上发布与本书相关的公告。请关注 [@rafalab](https://x.com/rafalab) 以获取更新。

# 致谢

特别感谢艾米·吉尔（Amy Gill）、豪尔赫·康尼克（Jorge Cornick）、巴里·麦克莱恩（Barry MacLean）和罗伯特· gentleman（Robert Gentleman）对数十条评论、编辑和建议。还要感谢斯蒂芬妮·希克斯（Stephanie Hicks），她两次担任我的数据科学课程助教，以及耐心回答我关于 bookdown 的许多问题的谢一辉（Yihui Xie）。还要感谢赫克托·科拉德-布拉沃（Héctor Corrada-Bravo），他提供了关于如何最好地教授机器学习的建议。感谢阿莉萨·弗拉齐（Alyssa Frazee）帮助创建成为推荐系统案例研究的家庭作业问题。还要感谢哈代·维克汉姆（Hadley Wickham）、米内·切廷卡亚-朗德尔（Mine Çetinkaya-Rundel）和加勒特·格罗勒蒙德（Garrett Grolemund）使他们的《R for Data Science》一书的 Quarto 代码开源。最后，感谢亚历克斯·诺恩斯（Alex Nones）在各个阶段校对稿件。

本书是在过去十五年中教授几门应用统计学课程的过程中构思的。多年来与我合作的助教对本书做出了重要的间接贡献。本课程的最新版本是由希瑟·斯滕申（Heather Sternshein）和佐菲亚·加约多斯（Zofia Gajdos）协调的哈佛 X 系列。我们感谢他们的贡献。我们还要感谢所有提出问题和评论的学生，他们的帮助使我们改进了本书。这些课程部分由 NIH 奖学金 R25GM114818 资助。我们非常感谢美国国立卫生研究院的支持。

特别感谢所有通过 GitHub 拉取请求编辑书籍或通过创建一个*问题*或发送电子邮件提出建议的人：`jcornickm`（Jorge Cornick）、`hbmaclean`（Barry MacLean）、`nickyfoto`（黄强）、`desautm`（Marc-André Désautels）、`michaschwab`（Michail Schwab）、`alvarolarreategui`（Alvaro Larreategui）、`jakevc`（Jake VanCampen）、`omerta`（Guillermo Lengemann）、`espinielli`（Enrico Spinielli）、`asimumba`（Aaron Simumba）、`braunschweig`（Maldewar）、`gwierzchowski`（Grzegorz Wierzchowski）、`technocrat`（Richard Careaga）、`atzakas`、`defeit`（David Emerson Feit）、`shiraamitchell`（Shira Mitchell）、`Nathalie-S`、`andreashandel`（Andreas Handel）、`berkowitze`（Elias Berkowitz）、`Dean-Webb`（Dean Webber）、`mohayusuf`、`jimrothstein`、`mPloenzke`（Matthew Ploenzke）、`NicholasDowand`（Nicholas Dow）、`kant`（Darío Hereñú）、`debbieyuster`（Debbie Yuster）、`tuanchauict`（Tuan Chau）、`phzeller`、`BTJ01`（BradJ）、`glsnow`（Greg Snow）、`mberlanda`（Mauro Berlanda）、`wfan9`、`larswestvang`（Lars Westvang）、`jj999`（Jan Andrejkovic）、`Kriegslustig`（Luca Nils Schmid）、`odahhani`、`aidanhorn`（Aidan Horn）、`atraxler`（Adrienne Traxler）、`alvegorova`、`wycheong`（Won Young Cheong）、`med-hat`（Medhat Khalil）、`biscotty666`（Brian Carey）、`kengustafson`、`Yowza63`、`ryan-heslin`（Ryan Heslin）、`SydneyUni-Jim`（Jim Nicholls）、`raffaem`、`BruciiZ`（Huiyuan (Bruce) Zhou）、`tim8west`、`aosaf-e-c`（Aosaf Ershad Chowdhury）、`annlia`、David D. Kane、El Mustapha El Abbassi、Vadim Zipunnikov、Anna Quaglieri、Chris Dong、Rick Schoenberg、Isabella Grabski、Doug Snyder 和 JT Harton。
