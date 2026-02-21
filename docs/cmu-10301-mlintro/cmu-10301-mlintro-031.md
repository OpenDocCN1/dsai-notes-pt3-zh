# CMU《机器学习导论｜Fall 2023 10-301⧸601 Introduction to Machine Learning》中英字幕教程

![](img/74f78ddb043deb17b7f3fc9a435697a6_1.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_2.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_4.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_5.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_6.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_7.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_9.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_11.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_12.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_13.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_15.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_17.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_19.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_21.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_23.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_25.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_27.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_29.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_31.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_32.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_33.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_35.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_36.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_38.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_40.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_42.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_44.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_46.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_48.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_50.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_52.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_54.png)

## 1. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_56.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_57.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_59.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_61.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_62.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_64.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_66.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_68.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_70.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_72.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_74.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_76.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_78.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_80.png)

**公式**： 
$$
\text{output\_size} = \frac{\text{input\_size} + 2 \times \text{padding} - \text{filter\_size}}{\text{stride}} + 1
$$

![](img/74f78ddb043deb17b7f3fc9a435697a6_82.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_84.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_86.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_88.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_90.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_92.png)

## 2. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_94.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_96.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_98.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_100.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_102.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_104.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_106.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_107.png)

**代码**：
```python
def calculate_output_size(input_size, filter_size, stride, padding):
    return (input_size + 2 * padding - filter_size) // stride + 1
```

![](img/74f78ddb043deb17b7f3fc9a435697a6_109.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_110.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_112.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_114.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_116.png)

## 3. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_118.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_120.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_122.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_124.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_126.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_128.png)

**公式**：
$$
\text{output\_size} = \frac{\text{input\_size} + 2 \times \text{padding} - \text{filter\_size}}{\text{stride}} + 1
$$

![](img/74f78ddb043deb17b7f3fc9a435697a6_130.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_131.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_133.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_134.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_136.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_138.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_140.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_142.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_144.png)

## 4. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_146.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_147.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_148.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_150.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_152.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_153.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_154.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_156.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_158.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_160.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_162.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_163.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_164.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_165.png)

**代码**：
```python
def calculate_output_size(input_size, filter_size, stride, padding):
    return (input_size + 2 * padding - filter_size) // stride + 1
```

![](img/74f78ddb043deb17b7f3fc9a435697a6_167.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_168.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_169.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_171.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_173.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_175.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_177.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_178.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_180.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_182.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_183.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_184.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_186.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_187.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_189.png)

## 5. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_191.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_193.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_195.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_197.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_198.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_200.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_202.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_203.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_205.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_207.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_209.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_210.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_212.png)

**公式**：
$$
\text{output\_size} = \frac{\text{input\_size} + 2 \times \text{padding} - \text{filter\_size}}{\text{stride}} + 1
$$

![](img/74f78ddb043deb17b7f3fc9a435697a6_214.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_216.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_218.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_220.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_222.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_223.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_225.png)

## 6. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_227.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_228.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_230.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_232.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_233.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_235.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_237.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_238.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_239.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_240.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_242.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_244.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_245.png)

**代码**：
```python
def calculate_output_size(input_size, filter_size, stride, padding):
    return (input_size + 2 * padding - filter_size) // stride + 1
```

![](img/74f78ddb043deb17b7f3fc9a435697a6_247.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_248.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_250.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_252.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_253.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_254.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_256.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_257.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_259.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_261.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_262.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_264.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_266.png)

## 7. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_268.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_270.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_272.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_274.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_275.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_277.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_278.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_279.png)

**公式**：
$$
\text{output\_size} = \frac{\text{input\_size} + 2 \times \text{padding} - \text{filter\_size}}{\text{stride}} + 1
$$

![](img/74f78ddb043deb17b7f3fc9a435697a6_281.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_282.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_284.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_286.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_288.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_290.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_291.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_293.png)

## 8. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_295.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_296.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_298.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_299.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_301.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_303.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_305.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_307.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_309.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_311.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_313.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_315.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_316.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_318.png)

**代码**：
```python
def calculate_output_size(input_size, filter_size, stride, padding):
    return (input_size + 2 * padding - filter_size) // stride + 1
```

![](img/74f78ddb043deb17b7f3fc9a435697a6_320.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_322.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_323.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_325.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_327.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_328.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_330.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_332.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_334.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_336.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_338.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_340.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_341.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_342.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_344.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_345.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_346.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_348.png)

## 9. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_350.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_352.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_354.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_355.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_356.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_358.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_360.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_362.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_364.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_366.png)

**公式**：
$$
\text{output\_size} = \frac{\text{input\_size} + 2 \times \text{padding} - \text{filter\_size}}{\text{stride}} + 1
$$

![](img/74f78ddb043deb17b7f3fc9a435697a6_368.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_370.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_372.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_374.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_375.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_376.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_378.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_380.png)

## 10. 核心概念

![](img/74f78ddb043deb17b7f3fc9a435697a6_382.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_384.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_385.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_387.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_389.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_390.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_392.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_394.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_396.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_398.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_400.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_402.png)

![](img/74f78ddb043deb17b7f3fc9a435697a6_404.png)

**代码**：
```python
def calculate_output_size(input_size, filter_size, stride, padding):
    return (input_size + 2 * padding - filter_size) // stride + 1
```