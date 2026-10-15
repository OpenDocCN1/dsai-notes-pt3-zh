# User Authentication

+   - Jaas.config

```
Login1
{
  com.sun.security.auth.module.UnixLoginModule required;
  com.whizzbang.auth.module.RetinaScanModule sufficient;
};
Login2
{
  ...
};
```