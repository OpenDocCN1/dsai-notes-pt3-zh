# ConvNet Architecture

# In practice: Common to zero pad the border

A 9×9 grid illustrating a 7×7 input with a one-pixel zero-padded border. The border cells are marked `0`.

e.g. input 7x7  
**3x3 filter**, applied with **stride 1**  
**pad with 1 pixel border** => what is the output?

**7x7 output!**

in general, common to see CONV layers with stride 1, filters of size FxF, and zero-padding with (F-1)/2. (will preserve size spatially)

+   - e.g. F = 3 => zero pad with 1
+   - F = 5 => zero pad with 2
+   - F = 7 => zero pad with 3