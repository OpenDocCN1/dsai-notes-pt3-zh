# Byte Verification

+   - Here are some of the checks that the verifier carries out:
+     - Variables are initialized before they are used.
+     - Method calls match the types of object references.
+     - Rules for accessing private data and methods are not violated.
+     - Local variable accesses fall within the runtime stack.
+     - The runtime stack does not overflow.
+   - `java -noverify Hello`