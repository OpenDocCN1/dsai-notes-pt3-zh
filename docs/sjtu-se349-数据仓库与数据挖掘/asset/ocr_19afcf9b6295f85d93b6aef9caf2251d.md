# 小波变换 Wavelet transform（续）

# 哈尔函数（Haar小波）

# 非标准分解(nonstandard decomposition)

+   用一维小波交替地对每一行和每一列像素值进行变换。

+   对每一行计算像素对的均值和差值，然后对每一列计算像素对的均值和差值

+   对包含均值的1/4像素计算行和列的均值和差值，依此类推

```
procedure NonstandardDecomposition(C: array[1...h, 1...h] of reals)
  C ← C/h    (normalize input coefficients)
  while h > 1 do
    for row 1 to h do
      DecompositionStep(C[row, 1...h])
    end for
    for col 1 to h do
      DecompositionStep(C[1...h, col])
    end for
    h ← h/2
  end while
end procedure
```