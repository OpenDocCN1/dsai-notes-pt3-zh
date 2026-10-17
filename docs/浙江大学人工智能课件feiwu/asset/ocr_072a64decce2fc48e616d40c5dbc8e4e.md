![](bbox=[0.279, 0.1, 0.64, 0.36])

$In_{h_1}=w_1*x_1+w_3*x_2$

$In_{h_2}=w_2*x_1+w_4*x_2$

$In_{o_1}=w_5*h_1+w_7*h_2$

$In_{o_2}=w_6*h_1+w_8*h_2$

$h_1=Out_{h_1}=Sigmoid(In_{h_1})$

$h_2=Out_{h_2}=Sigmoid(In_{h_2})$

$o_1=Out_{o_1}=Sigmoid(In_{o_1})$

$o_2=Out_{o_2}=Sigmoid(In_{o_2})$

$Error=\sum_{i=1}^{2}\frac{1}{2}(z_i-o_i)^2$