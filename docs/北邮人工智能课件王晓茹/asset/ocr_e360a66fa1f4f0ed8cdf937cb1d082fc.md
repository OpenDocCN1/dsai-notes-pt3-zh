# Image Features

![](bbox=[0.064, 0.089, 0.442, 0.193])

Rectangle filters

Feature Value = ∑(Pixel in white area) − ∑(Pixel in black area)

# Image Features

![](bbox=[0.563, 0.089, 0.938, 0.231])

Rectangle filters

Feature Value = ∑(Pixel in white area) − ∑(Pixel in black area)

# Size of Feature Space

![](bbox=[0.064, 0.341, 0.233, 0.444])

Rectangle filters

+   - How many number of possible rectangle features for a 24×24 detection region?
+   - A+B: 2, 3, 4, ...
+   - C: ...
+   - D: ...
+   - **160,000**

# Feature Selection

![](bbox=[0.563, 0.342, 0.732, 0.422])

+   - How many number of possible rectangle features for a 24×24 detection region?
+   - A+B: ...
+   - C: ...
+   - D: ...
+   - **160,000**

What features are good for face detection?

# Feature Selection

![](bbox=[0.064, 0.591, 0.239, 0.67])

+   - How many number of possible rectangle features for a 24×24 detection region?
+   - A+B: ...
+   - C: ...
+   - D: ...
+   - **160,000**

+   - Can we create a good classifier using just a small subset of all possible features?
+   - How to select such a subset?

# Integral images

+   - The integral image computes a value at each pixel (x, y) that is the sum of the pixel values above and to the left of (x, y), inclusive.

![](bbox=[0.766, 0.59, 0.957, 0.702])

# Computing the Integral Image

+   - The integral image computes a value at each pixel (x, y) that is the sum of the pixel values above and to the left of (x, y), inclusive.
+   - This can quickly be computed in one pass through the image.

![](bbox=[0.266, 0.836, 0.454, 0.958])

s(x,y) = s(x−1,y) + i(x,y)
ii(x,y) = ii(x−1,y) + s(x,y)

# Computing Sum within a Rectangle

![](bbox=[0.557, 0.839, 0.955, 0.956])

Only 3 additions are required for any size of rectangle!