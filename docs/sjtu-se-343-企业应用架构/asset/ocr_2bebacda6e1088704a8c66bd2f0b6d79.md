+   - An Example: SimpleLoginModule.
+     - SimpleLoginModule.java

```
in.close();
return false;
}
catch (IOException e)
{
LoginException e2 = new LoginException("Can't open password file");
e2.initCause(e);
throw e2;
}
}
```

```
public boolean logout() { return true; }
public boolean abort() { return true; }
public boolean commit() { return true; }
```

```
private Subject subject;
private CallbackHandler callbackHandler;
private Map<String, ?> sharedState;
private Map<String, ?> options;
}
```