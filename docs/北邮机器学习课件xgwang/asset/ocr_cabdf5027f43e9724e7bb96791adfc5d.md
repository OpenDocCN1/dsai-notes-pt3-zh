# Multimodal deep auto-encoder

+   - In (a), the deep auto-encoder is trained to reconstruct both modalities when given only video data and thus discovers correlations across the modalities.
+   - Initialize the deep autoencoder with the bimodal DBN weights and discard any weights that are no longer present. The middle layer can be used as the new feature representation.
+   - Model (a) is used when only a single modality is present at supervised training and testing

![](bbox=[0.08, 0.52, 0.48, 0.85])

![](bbox=[0.52, 0.5, 0.95, 0.85])