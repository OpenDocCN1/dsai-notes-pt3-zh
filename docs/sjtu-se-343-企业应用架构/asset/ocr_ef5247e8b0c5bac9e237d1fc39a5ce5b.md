# Cipher Streams

+   - The JCE library provides a convenient set of stream classes that automatically encrypt or decrypt stream data.
+   - Decryption
+     Cipher cipher = ...;
+     cipher.init(Cipher.DECRYPT_MODE, key);
+     CipherInputStream in = new CipherInputStream(new FileInputStream(inputFileName), cipher);
+     byte[] bytes = new byte[BLOCKSIZE];
+     int inLength = in.read(bytes);
+     while (inLength != -1) {
+       putData(bytes, inLength); // put data to destination
+       inLength = in.read(bytes);
+     }