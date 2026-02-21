# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕（deepseek p06 Lecture_6_Perceptron.zh_en -BV1Z2cUefE4A_p6-

![](img/223aea760bce52b872e46ca99b14c6fe_0.png)

![](img/223aea760bce52b872e46ca99b14c6fe_2.png)

![](img/223aea760bce52b872e46ca99b14c6fe_3.png)

![](img/223aea760bce52b872e46ca99b14c6fe_4.png)

![](img/223aea760bce52b872e46ca99b14c6fe_5.png)

![](img/223aea760bce52b872e46ca99b14c6fe_6.png)

![](img/223aea760bce52b872e46ca99b14c6fe_7.png)

![](img/223aea760bce52b872e46ca99b14c6fe_9.png)

![](img/223aea760bce52b872e46ca99b14c6fe_10.png)

![](img/223aea760bce52b872e46ca99b14c6fe_12.png)

![](img/223aea760bce52b872e46ca99b14c6fe_14.png)

![](img/223aea760bce52b872e46ca99b14c6fe_16.png)

![](img/223aea760bce52b872e46ca99b14c6fe_17.png)

![](img/223aea760bce52b872e46ca99b14c6fe_18.png)

![](img/223aea760bce52b872e46ca99b14c6fe_19.png)

![](img/223aea760bce52b872e46ca99b14c6fe_21.png)

![](img/223aea760bce52b872e46ca99b14c6fe_22.png)

![](img/223aea760bce52b872e46ca99b14c6fe_23.png)

![](img/223aea760bce52b872e46ca99b14c6fe_25.png)

![](img/223aea760bce52b872e46ca99b14c6fe_26.png)

![](img/223aea760bce52b872e46ca99b14c6fe_27.png)

![](img/223aea760bce52b872e46ca99b14c6fe_29.png)

![](img/223aea760bce52b872e46ca99b14c6fe_30.png)

![](img/223aea760bce52b872e46ca99b14c6fe_32.png)

![](img/223aea760bce52b872e46ca99b14c6fe_33.png)

![](img/223aea760bce52b872e46ca99b14c6fe_34.png)

## 概述

![](img/223aea760bce52b872e46ca99b14c6fe_35.png)

![](img/223aea760bce52b872e46ca99b14c6fe_37.png)

![](img/223aea760bce52b872e46ca99b14c6fe_38.png)

![](img/223aea760bce52b872e46ca99b14c6fe_40.png)

![](img/223aea760bce52b872e46ca99b14c6fe_42.png)

![](img/223aea760bce52b872e46ca99b14c6fe_43.png)

![](img/223aea760bce52b872e46ca99b14c6fe_45.png)

![](img/223aea760bce52b872e46ca99b14c6fe_46.png)

![](img/223aea760bce52b872e46ca99b14c6fe_47.png)

![](img/223aea760bce52b872e46ca99b14c6fe_49.png)

![](img/223aea760bce52b872e46ca99b14c6fe_50.png)

![](img/223aea760bce52b872e46ca99b14c6fe_52.png)

在本节课中，我们将介绍机器学习中的感知器模型，并探讨在线学习这一新的机器学习范式。我们将学习如何使用感知器进行分类，并了解在线学习在现实世界应用中的重要性。

![](img/223aea760bce52b872e46ca99b14c6fe_54.png)

![](img/223aea760bce52b872e46ca99b14c6fe_55.png)

![](img/223aea760bce52b872e46ca99b14c6fe_57.png)

![](img/223aea760bce52b872e46ca99b14c6fe_59.png)

![](img/223aea760bce52b872e46ca99b14c6fe_61.png)

![](img/223aea760bce52b872e46ca99b14c6fe_63.png)

![](img/223aea760bce52b872e46ca99b14c6fe_65.png)

![](img/223aea760bce52b872e46ca99b14c6fe_66.png)

![](img/223aea760bce52b872e46ca99b14c6fe_67.png)

## 1. 课程回顾

![](img/223aea760bce52b872e46ca99b14c6fe_69.png)

![](img/223aea760bce52b872e46ca99b14c6fe_70.png)

![](img/223aea760bce52b872e46ca99b14c6fe_71.png)

![](img/223aea760bce52b872e46ca99b14c6fe_72.png)

![](img/223aea760bce52b872e46ca99b14c6fe_73.png)

![](img/223aea760bce52b872e46ca99b14c6fe_75.png)

![](img/223aea760bce52b872e46ca99b14c6fe_77.png)

![](img/223aea760bce52b872e46ca99b14c6fe_79.png)

![](img/223aea760bce52b872e46ca99b14c6fe_80.png)

![](img/223aea760bce52b872e46ca99b14c6fe_81.png)

![](img/223aea760bce52b872e46ca99b14c6fe_82.png)

![](img/223aea760bce52b872e46ca99b14c6fe_84.png)

![](img/223aea760bce52b872e46ca99b14c6fe_85.png)

![](img/223aea760bce52b872e46ca99b14c6fe_86.png)

![](img/223aea760bce52b872e46ca99b14c6fe_87.png)

![](img/223aea760bce52b872e46ca99b14c6fe_89.png)

![](img/223aea760bce52b872e46ca99b14c6fe_91.png)

![](img/223aea760bce52b872e46ca99b14c6fe_93.png)

在开始介绍感知器之前，让我们回顾一下之前学过的内容：

![](img/223aea760bce52b872e46ca99b14c6fe_95.png)

![](img/223aea760bce52b872e46ca99b14c6fe_96.png)

![](img/223aea760bce52b872e46ca99b14c6fe_97.png)

![](img/223aea760bce52b872e46ca99b14c6fe_99.png)

![](img/223aea760bce52b872e46ca99b14c6fe_101.png)

![](img/223aea760bce52b872e46ca99b14c6fe_103.png)

![](img/223aea760bce52b872e46ca99b14c6fe_104.png)

![](img/223aea760bce52b872e46ca99b14c6fe_105.png)

![](img/223aea760bce52b872e46ca99b14c6fe_106.png)

![](img/223aea760bce52b872e46ca99b14c6fe_107.png)

![](img/223aea760bce52b872e46ca99b14c6fe_109.png)

![](img/223aea760bce52b872e46ca99b14c6fe_110.png)

![](img/223aea760bce52b872e46ca99b14c6fe_112.png)

![](img/223aea760bce52b872e46ca99b14c6fe_113.png)

![](img/223aea760bce52b872e46ca99b14c6fe_114.png)

![](img/223aea760bce52b872e46ca99b14c6fe_115.png)

![](img/223aea760bce52b872e46ca99b14c6fe_116.png)

![](img/223aea760bce52b872e46ca99b14c6fe_117.png)

* **线性回归**：使用线性模型预测连续值。
* **逻辑回归**：使用线性模型进行二分类。
* **K近邻（KNN）**：基于最近邻的决策规则进行分类。

![](img/223aea760bce52b872e46ca99b14c6fe_119.png)

![](img/223aea760bce52b872e46ca99b14c6fe_121.png)

![](img/223aea760bce52b872e46ca99b14c6fe_123.png)

![](img/223aea760bce52b872e46ca99b14c6fe_125.png)

![](img/223aea760bce52b872e46ca99b14c6fe_126.png)

![](img/223aea760bce52b872e46ca99b14c6fe_127.png)

## 2. 感知器模型

![](img/223aea760bce52b872e46ca99b14c6fe_129.png)

![](img/223aea760bce52b872e46ca99b14c6fe_130.png)

![](img/223aea760bce52b872e46ca99b14c6fe_132.png)

![](img/223aea760bce52b872e46ca99b14c6fe_133.png)

![](img/223aea760bce52b872e46ca99b14c6fe_134.png)

![](img/223aea760bce52b872e46ca99b14c6fe_136.png)

![](img/223aea760bce52b872e46ca99b14c6fe_137.png)

![](img/223aea760bce52b872e46ca99b14c6fe_139.png)

![](img/223aea760bce52b872e46ca99b14c6fe_141.png)

![](img/223aea760bce52b872e46ca99b14c6fe_143.png)

![](img/223aea760bce52b872e46ca99b14c6fe_145.png)

![](img/223aea760bce52b872e46ca99b14c6fe_147.png)

![](img/223aea760bce52b872e46ca99b14c6fe_148.png)

感知器是一种简单的线性二分类模型，它使用线性决策边界来区分不同的类别。其公式如下：

![](img/223aea760bce52b872e46ca99b14c6fe_150.png)

![](img/223aea760bce52b872e46ca99b14c6fe_152.png)

![](img/223aea760bce52b872e46ca99b14c6fe_154.png)

![](img/223aea760bce52b872e46ca99b14c6fe_156.png)

![](img/223aea760bce52b872e46ca99b14c6fe_157.png)

![](img/223aea760bce52b872e46ca99b14c6fe_159.png)

![](img/223aea760bce52b872e46ca99b14c6fe_161.png)

![](img/223aea760bce52b872e46ca99b14c6fe_163.png)

**公式**：y = sign(W^T * x + b)

![](img/223aea760bce52b872e46ca99b14c6fe_165.png)

![](img/223aea760bce52b872e46ca99b14c6fe_166.png)

![](img/223aea760bce52b872e46ca99b14c6fe_167.png)

![](img/223aea760bce52b872e46ca99b14c6fe_168.png)

![](img/223aea760bce52b872e46ca99b14c6fe_170.png)

![](img/223aea760bce52b872e46ca99b14c6fe_171.png)

![](img/223aea760bce52b872e46ca99b14c6fe_172.png)

![](img/223aea760bce52b872e46ca99b14c6fe_173.png)

![](img/223aea760bce52b872e46ca99b14c6fe_175.png)

![](img/223aea760bce52b872e46ca99b14c6fe_177.png)

![](img/223aea760bce52b872e46ca99b14c6fe_178.png)

![](img/223aea760bce52b872e46ca99b14c6fe_179.png)

![](img/223aea760bce52b872e46ca99b14c6fe_180.png)

![](img/223aea760bce52b872e46ca99b14c6fe_182.png)

![](img/223aea760bce52b872e46ca99b14c6fe_184.png)

![](img/223aea760bce52b872e46ca99b14c6fe_186.png)

![](img/223aea760bce52b872e46ca99b14c6fe_187.png)

![](img/223aea760bce52b872e46ca99b14c6fe_189.png)

![](img/223aea760bce52b872e46ca99b14c6fe_191.png)

![](img/223aea760bce52b872e46ca99b14c6fe_193.png)

其中：

![](img/223aea760bce52b872e46ca99b14c6fe_195.png)

![](img/223aea760bce52b872e46ca99b14c6fe_196.png)

![](img/223aea760bce52b872e46ca99b14c6fe_198.png)

![](img/223aea760bce52b872e46ca99b14c6fe_200.png)

![](img/223aea760bce52b872e46ca99b14c6fe_202.png)

![](img/223aea760bce52b872e46ca99b14c6fe_203.png)

![](img/223aea760bce52b872e46ca99b14c6fe_205.png)

![](img/223aea760bce52b872e46ca99b14c6fe_206.png)

![](img/223aea760bce52b872e46ca99b14c6fe_207.png)

![](img/223aea760bce52b872e46ca99b14c6fe_209.png)

![](img/223aea760bce52b872e46ca99b14c6fe_210.png)

![](img/223aea760bce52b872e46ca99b14c6fe_211.png)

![](img/223aea760bce52b872e46ca99b14c6fe_213.png)

* y 是预测的类别标签。
* W 是权重向量。
* x 是特征向量。
* b 是偏置项。

![](img/223aea760bce52b872e46ca99b14c6fe_214.png)

![](img/223aea760bce52b872e46ca99b14c6fe_216.png)

![](img/223aea760bce52b872e46ca99b14c6fe_217.png)

![](img/223aea760bce52b872e46ca99b14c6fe_218.png)

![](img/223aea760bce52b872e46ca99b14c6fe_220.png)

![](img/223aea760bce52b872e46ca99b14c6fe_222.png)

![](img/223aea760bce52b872e46ca99b14c6fe_224.png)

![](img/223aea760bce52b872e46ca99b14c6fe_225.png)

![](img/223aea760bce52b872e46ca99b14c6fe_227.png)

![](img/223aea760bce52b872e46ca99b14c6fe_229.png)

![](img/223aea760bce52b872e46ca99b14c6fe_231.png)

![](img/223aea760bce52b872e46ca99b14c6fe_232.png)

![](img/223aea760bce52b872e46ca99b14c6fe_233.png)

![](img/223aea760bce52b872e46ca99b14c6fe_234.png)

## 3. 感知器学习算法

![](img/223aea760bce52b872e46ca99b14c6fe_236.png)

![](img/223aea760bce52b872e46ca99b14c6fe_238.png)

![](img/223aea760bce52b872e46ca99b14c6fe_240.png)

![](img/223aea760bce52b872e46ca99b14c6fe_242.png)

![](img/223aea760bce52b872e46ca99b14c6fe_243.png)

![](img/223aea760bce52b872e46ca99b14c6fe_245.png)

![](img/223aea760bce52b872e46ca99b14c6fe_247.png)

![](img/223aea760bce52b872e46ca99b14c6fe_249.png)

![](img/223aea760bce52b872e46ca99b14c6fe_251.png)

![](img/223aea760bce52b872e46ca99b14c6fe_252.png)

![](img/223aea760bce52b872e46ca99b14c6fe_253.png)

![](img/223aea760bce52b872e46ca99b14c6fe_254.png)

![](img/223aea760bce52b872e46ca99b14c6fe_256.png)

![](img/223aea760bce52b872e46ca99b14c6fe_258.png)

![](img/223aea760bce52b872e46ca99b14c6fe_260.png)

![](img/223aea760bce52b872e46ca99b14c6fe_262.png)

![](img/223aea760bce52b872e46ca99b14c6fe_264.png)

![](img/223aea760bce52b872e46ca99b14c6fe_265.png)

感知器学习算法通过不断更新权重和偏置项来学习线性决策边界。以下是感知器学习算法的步骤：

![](img/223aea760bce52b872e46ca99b14c6fe_267.png)

![](img/223aea760bce52b872e46ca99b14c6fe_268.png)

![](img/223aea760bce52b872e46ca99b14c6fe_269.png)

![](img/223aea760bce52b872e46ca99b14c6fe_270.png)

![](img/223aea760bce52b872e46ca99b14c6fe_272.png)

![](img/223aea760bce52b872e46ca99b14c6fe_274.png)

![](img/223aea760bce52b872e46ca99b14c6fe_276.png)

![](img/223aea760bce52b872e46ca99b14c6fe_278.png)

![](img/223aea760bce52b872e46ca99b14c6fe_279.png)

![](img/223aea760bce52b872e46ca99b14c6fe_281.png)

![](img/223aea760bce52b872e46ca99b14c6fe_283.png)

![](img/223aea760bce52b872e46ca99b14c6fe_285.png)

![](img/223aea760bce52b872e46ca99b14c6fe_286.png)

![](img/223aea760bce52b872e46ca99b14c6fe_288.png)

![](img/223aea760bce52b872e46ca99b14c6fe_290.png)

![](img/223aea760bce52b872e46ca99b14c6fe_292.png)

![](img/223aea760bce52b872e46ca99b14c6fe_294.png)

![](img/223aea760bce52b872e46ca99b14c6fe_296.png)

![](img/223aea760bce52b872e46ca99b14c6fe_298.png)

![](img/223aea760bce52b872e46ca99b14c6fe_300.png)

![](img/223aea760bce52b872e46ca99b14c6fe_302.png)

1. 初始化权重和偏置项为0。
2. 对于每个数据点：
    * 使用当前权重和偏置项计算预测值。
    * 如果预测值与真实标签不符，则更新权重和偏置项。
3. 重复步骤2，直到模型收敛。

![](img/223aea760bce52b872e46ca99b14c6fe_304.png)

![](img/223aea760bce52b872e46ca99b14c6fe_306.png)

![](img/223aea760bce52b872e46ca99b14c6fe_308.png)

![](img/223aea760bce52b872e46ca99b14c6fe_309.png)

![](img/223aea760bce52b872e46ca99b14c6fe_311.png)

![](img/223aea760bce52b872e46ca99b14c6fe_313.png)

![](img/223aea760bce52b872e46ca99b14c6fe_314.png)

![](img/223aea760bce52b872e46ca99b14c6fe_316.png)

![](img/223aea760bce52b872e46ca99b14c6fe_318.png)

![](img/223aea760bce52b872e46ca99b14c6fe_319.png)

![](img/223aea760bce52b872e46ca99b14c6fe_321.png)

![](img/223aea760bce52b872e46ca99b14c6fe_323.png)

![](img/223aea760bce52b872e46ca99b14c6fe_325.png)

![](img/223aea760bce52b872e46ca99b14c6fe_326.png)

![](img/223aea760bce52b872e46ca99b14c6fe_328.png)

![](img/223aea760bce52b872e46ca99b14c6fe_330.png)

**公式**：W = W + y * x
**公式**：b = b + y

![](img/223aea760bce52b872e46ca99b14c6fe_332.png)

![](img/223aea760bce52b872e46ca99b14c6fe_333.png)

![](img/223aea760bce52b872e46ca99b14c6fe_335.png)

![](img/223aea760bce52b872e46ca99b14c6fe_337.png)

![](img/223aea760bce52b872e46ca99b14c6fe_339.png)

![](img/223aea760bce52b872e46ca99b14c6fe_340.png)

![](img/223aea760bce52b872e46ca99b14c6fe_341.png)

![](img/223aea760bce52b872e46ca99b14c6fe_343.png)

![](img/223aea760bce52b872e46ca99b14c6fe_345.png)

![](img/223aea760bce52b872e46ca99b14c6fe_346.png)

![](img/223aea760bce52b872e46ca99b14c6fe_348.png)

![](img/223aea760bce52b872e46ca99b14c6fe_349.png)

![](img/223aea760bce52b872e46ca99b14c6fe_350.png)

![](img/223aea760bce52b872e46ca99b14c6fe_352.png)

![](img/223aea760bce52b872e46ca99b14c6fe_354.png)

![](img/223aea760bce52b872e46ca99b14c6fe_356.png)

![](img/223aea760bce52b872e46ca99b14c6fe_358.png)

![](img/223aea760bce52b872e46ca99b14c6fe_359.png)

![](img/223aea760bce52b872e46ca99b14c6fe_361.png)

![](img/223aea760bce52b872e46ca99b14c6fe_363.png)

## 4. 在线学习

![](img/223aea760bce52b872e46ca99b14c6fe_365.png)

![](img/223aea760bce52b872e46ca99b14c6fe_367.png)

![](img/223aea760bce52b872e46ca99b14c6fe_369.png)

![](img/223aea760bce52b872e46ca99b14c6fe_371.png)

![](img/223aea760bce52b872e46ca99b14c6fe_373.png)

![](img/223aea760bce52b872e46ca99b14c6fe_374.png)

![](img/223aea760bce52b872e46ca99b14c6fe_376.png)

![](img/223aea760bce52b872e46ca99b14c6fe_378.png)

![](img/223aea760bce52b872e46ca99b14c6fe_380.png)

![](img/223aea760bce52b872e46ca99b14c6fe_381.png)

![](img/223aea760bce52b872e46ca99b14c6fe_382.png)

在线学习是一种机器学习范式，它允许模型在数据流中不断更新。与批量学习相比，在线学习可以更快地适应新数据，并减少对存储空间的需求。

![](img/223aea760bce52b872e46ca99b14c6fe_384.png)

![](img/223aea760bce52b872e46ca99b14c6fe_385.png)

![](img/223aea760bce52b872e46ca99b14c6fe_386.png)

![](img/223aea760bce52b872e46ca99b14c6fe_387.png)

![](img/223aea760bce52b872e46ca99b14c6fe_388.png)

![](img/223aea760bce52b872e46ca99b14c6fe_390.png)

![](img/223aea760bce52b872e46ca99b14c6fe_392.png)

![](img/223aea760bce52b872e46ca99b14c6fe_394.png)

![](img/223aea760bce52b872e46ca99b14c6fe_395.png)

![](img/223aea760bce52b872e46ca99b14c6fe_396.png)

![](img/223aea760bce52b872e46ca99b14c6fe_397.png)

![](img/223aea760bce52b872e46ca99b14c6fe_399.png)

![](img/223aea760bce52b872e46ca99b14c6fe_401.png)

![](img/223aea760bce52b872e46ca99b14c6fe_402.png)

![](img/223aea760bce52b872e46ca99b14c6fe_403.png)

![](img/223aea760bce52b872e46ca99b14c6fe_404.png)

![](img/223aea760bce52b872e46ca99b14c6fe_405.png)

![](img/223aea760bce52b872e46ca99b14c6fe_406.png)

![](img/223aea760bce52b872e46ca99b14c6fe_407.png)

![](img/223aea760bce52b872e46ca99b14c6fe_408.png)

![](img/223aea760bce52b872e46ca99b14c6fe_409.png)

## 5. 感知器在线学习

![](img/223aea760bce52b872e46ca99b14c6fe_411.png)

![](img/223aea760bce52b872e46ca99b14c6fe_412.png)

![](img/223aea760bce52b872e46ca99b14c6fe_413.png)

![](img/223aea760bce52b872e46ca99b14c6fe_415.png)

![](img/223aea760bce52b872e46ca99b14c6fe_417.png)

![](img/223aea760bce52b872e46ca99b14c6fe_419.png)

![](img/223aea760bce52b872e46ca99b14c6fe_420.png)

![](img/223aea760bce52b872e46ca99b14c6fe_421.png)

![](img/223aea760bce52b872e46ca99b14c6fe_423.png)

![](img/223aea760bce52b872e46ca99b14c6fe_425.png)

![](img/223aea760bce52b872e46ca99b14c6fe_426.png)

![](img/223aea760bce52b872e46ca99b14c6fe_428.png)

![](img/223aea760bce52b872e46ca99b14c6fe_430.png)

![](img/223aea760bce52b872e46ca99b14c6fe_432.png)

感知器可以用于在线学习场景。以下是感知器在线学习算法的步骤：

![](img/223aea760bce52b872e46ca99b14c6fe_434.png)

![](img/223aea760bce52b872e46ca99b14c6fe_436.png)

![](img/223aea760bce52b872e46ca99b14c6fe_437.png)

![](img/223aea760bce52b872e46ca99b14c6fe_438.png)

![](img/223aea760bce52b872e46ca99b14c6fe_440.png)

![](img/223aea760bce52b872e46ca99b14c6fe_442.png)

![](img/223aea760bce52b872e46ca99b14c6fe_443.png)

1. 初始化权重和偏置项为0。
2. 对于每个数据点：
    * 使用当前权重和偏置项计算预测值。
    * 如果预测值与真实标签不符，则更新权重和偏置项。
3. 重复步骤2，直到模型收敛。

![](img/223aea760bce52b872e46ca99b14c6fe_445.png)

![](img/223aea760bce52b872e46ca99b14c6fe_446.png)

![](img/223aea760bce52b872e46ca99b14c6fe_447.png)

![](img/223aea760bce52b872e46ca99b14c6fe_449.png)

![](img/223aea760bce52b872e46ca99b14c6fe_450.png)

![](img/223aea760bce52b872e46ca99b14c6fe_452.png)

![](img/223aea760bce52b872e46ca99b14c6fe_454.png)

![](img/223aea760bce52b872e46ca99b14c6fe_455.png)

![](img/223aea760bce52b872e46ca99b14c6fe_457.png)

![](img/223aea760bce52b872e46ca99b14c6fe_459.png)

## 6. 感知器的优势

![](img/223aea760bce52b872e46ca99b14c6fe_461.png)

![](img/223aea760bce52b872e46ca99b14c6fe_462.png)

![](img/223aea760bce52b872e46ca99b14c6fe_464.png)

![](img/223aea760bce52b872e46ca99b14c6fe_466.png)

![](img/223aea760bce52b872e46ca99b14c6fe_467.png)

![](img/223aea760bce52b872e46ca99b14c6fe_469.png)

![](img/223aea760bce52b872e46ca99b14c6fe_471.png)

![](img/223aea760bce52b872e46ca99b14c6fe_473.png)

![](img/223aea760bce52b872e46ca99b14c6fe_475.png)

* **简单**：感知器模型简单，易于实现和理解。
* **高效**：感知器学习算法收敛速度快。
* **鲁棒**：感知器对噪声和异常值具有鲁棒性。

![](img/223aea760bce52b872e46ca99b14c6fe_477.png)

![](img/223aea760bce52b872e46ca99b14c6fe_479.png)

![](img/223aea760bce52b872e46ca99b14c6fe_480.png)

![](img/223aea760bce52b872e46ca99b14c6fe_482.png)

![](img/223aea760bce52b872e46ca99b14c6fe_484.png)

![](img/223aea760bce52b872e46ca99b14c6fe_485.png)

![](img/223aea760bce52b872e46ca99b14c6fe_486.png)

![](img/223aea760bce52b872e46ca99b14c6fe_487.png)

![](img/223aea760bce52b872e46ca99b14c6fe_489.png)

![](img/223aea760bce52b872e46ca99b14c6fe_491.png)

## 7. 感知器的局限性

![](img/223aea760bce52b872e46ca99b14c6fe_493.png)

![](img/223aea760bce52b872e46ca99b14c6fe_495.png)

![](img/223aea760bce52b872e46ca99b14c6fe_497.png)

![](img/223aea760bce52b872e46ca99b14c6fe_499.png)

![](img/223aea760bce52b872e46ca99b14c6fe_500.png)

![](img/223aea760bce52b872e46ca99b14c6fe_501.png)

![](img/223aea760bce52b872e46ca99b14c6fe_502.png)

![](img/223aea760bce52b872e46ca99b14c6fe_504.png)

![](img/223aea760bce52b872e46ca99b14c6fe_506.png)

![](img/223aea760bce52b872e46ca99b14c6fe_507.png)

![](img/223aea760bce52b872e46ca99b14c6fe_509.png)

* **线性假设**：感知器假设数据是线性可分的，这可能不适用于所有数据集。
* **过拟合**：如果数据不是线性可分的，感知器可能会过拟合。

![](img/223aea760bce52b872e46ca99b14c6fe_511.png)

![](img/223aea760bce52b872e46ca99b14c6fe_512.png)

![](img/223aea760bce52b872e46ca99b14c6fe_513.png)

## 总结

![](img/223aea760bce52b872e46ca99b14c6fe_515.png)

![](img/223aea760bce52b872e46ca99b14c6fe_517.png)

![](img/223aea760bce52b872e46ca99b14c6fe_518.png)

![](img/223aea760bce52b872e46ca99b14c6fe_519.png)

![](img/223aea760bce52b872e46ca99b14c6fe_521.png)

![](img/223aea760bce52b872e46ca99b14c6fe_523.png)

![](img/223aea760bce52b872e46ca99b14c6fe_524.png)

![](img/223aea760bce52b872e46ca99b14c6fe_525.png)

![](img/223aea760bce52b872e46ca99b14c6fe_526.png)

在本节课中，我们介绍了感知器模型和在线学习。我们学习了感知器学习算法的步骤，并了解了在线学习在现实世界应用中的重要性。希望这节课能帮助你更好地理解机器学习中的感知器模型。