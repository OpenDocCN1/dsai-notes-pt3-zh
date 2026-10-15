+   - Operations checked by the security manager include the following:
+     - Creating a new class loader
+     - Exiting the virtual machine
+     - Accessing a field of another class by using reflection
+     - Accessing a file
+     - Opening a socket connection
+     - Starting a print job
+     - Accessing the system clipboard
+     - Accessing the AWT event queue
+     - Bringing up a top-level window

```
public void exit(int status) {
    SecurityManager security = System.getSecurityManager();
    if (security != null)
        security.checkExit(status);
    exitInternal(status);
}
```