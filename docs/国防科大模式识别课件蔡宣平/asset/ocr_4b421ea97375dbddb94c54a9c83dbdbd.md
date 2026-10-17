R_j(\vec{x}) = \sum_{i=1}^{c} \lambda_{ij} p(\vec{x}|\omega_i) P(\omega_i) / p(\vec{x}) = \sum_{i=1}^{c} \lambda_{ij} p(\vec{x}|\omega_i) P(\omega_i) / \sum_{i=1}^{c} p(\vec{x}|\omega_i) P(\omega_i)

求上式R_j(x)关于x的数学期望：

R = \int_{\Omega} R_j(\vec{x}) p(\vec{x}) d\vec{x} = \sum_{j=1}^{c} \int_{\Omega_j} R_j(\vec{x}) p(\vec{x}) d\vec{x}

= \sum_{j=1}^{c} \int_{\Omega_j} \sum_{i=1}^{c} \lambda_{ij} p(\vec{x}|\omega_i) P(\omega_i) d\vec{x}

= \sum_{i=1}^{c} \sum_{j=1}^{c} \int_{\Omega_j} \lambda(\alpha_j(\vec{x}) | \omega_i) p(\vec{x}|\omega_i) P(\omega_i) d\vec{x}

= \sum_{i=1}^{c} P(\omega_i) \int_{\Omega} \lambda(\alpha(\vec{x}) | \omega_i) p(\vec{x}|\omega_i) d\vec{x}

= \sum_{i=1}^{c} P(\omega_i) E_i[\lambda(\alpha(\vec{x}) | \omega_i)] = E[\lambda(\alpha(\vec{x}))]

平均损失