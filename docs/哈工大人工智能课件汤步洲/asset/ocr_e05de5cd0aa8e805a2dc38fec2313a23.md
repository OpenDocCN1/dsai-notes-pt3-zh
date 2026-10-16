# Inference by Enumeration: Procedural Outline

+   - Track objects called factors
+   - Initial factors are local CPTs (one per node)

P(R)
| +r | 0.1 |
| -r | 0.9 |

P(T|R)
| +r | +t | 0.8 |
| +r | -t | 0.2 |
| -r | +t | 0.1 |
| -r | -t | 0.9 |

P(L|T)
| +t | +l | 0.3 |
| +t | -l | 0.7 |
| -t | +l | 0.1 |
| -t | -l | 0.9 |

+   - Any known values are selected
+     - E.g. if we know L = +ℓ , the initial factors are

P(R)
| +r | 0.1 |
| -r | 0.9 |

P(T|R)
| +r | +t | 0.8 |
| +r | -t | 0.2 |
| -r | +t | 0.1 |
| -r | -t | 0.9 |

P(+ℓ|T)
| +t | +l | 0.3 |
| -t | +l | 0.1 |

+   - Procedure: Join all factors, then eliminate all hidden variables

![](bbox=[0.64, 0.22, 0.99, 0.88])