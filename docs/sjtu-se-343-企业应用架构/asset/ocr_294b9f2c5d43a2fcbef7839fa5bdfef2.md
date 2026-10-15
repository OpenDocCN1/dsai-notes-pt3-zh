# Cipher

```
Cipher cipher = Cipher.getInstance(algorithmName);
```

+   - or

```
Cipher cipher = Cipher.getInstance(algorithmName, providerName);
```

+   - The JDK comes with ciphers by the provider named "SunJCE".
+   - The algorithm name is a string such as "AES" or "DES/CBC/PKCS5Padding".

```
int mode = ...; Key key = ...; cipher.init(mode, key);
```

+   - The mode is one of

```
Cipher.ENCRYPT_MODE
Cipher.DECRYPT_MODE
Cipher.WRAP_MODE
Cipher.UNWRAP_MODE
```