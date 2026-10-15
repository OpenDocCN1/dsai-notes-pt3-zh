# X.509 Certificate

+   - To take advantage of public key cryptography, the public keys must be distributed.
+     - One of the most common distribution formats is called X.509.

+   - The **keytool** program manages keystores, databases of certificates and private/public key pairs.
+     - Each entry in the keystore has an alias.
+     - Here is how Alice creates a keystore, alice.certs, and generates a key pair with alias alice.
+     - `keytool -genkeypair -keystore alice.certs -alias alice`