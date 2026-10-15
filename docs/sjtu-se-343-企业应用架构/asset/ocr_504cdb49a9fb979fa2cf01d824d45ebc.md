+   - An Example: SimpleLoginModule.
+     - SimpleCallbackHandler.java
+   
+     import javax.security.auth.callback.*;
+   
+     /**
+      * This simple callback handler presents the given user name and password.
+      */
+     public class SimpleCallbackHandler implements CallbackHandler
+     {
+         /**
+          * Constructs the callback handler.
+          * @param username the user name
+          * @param password a character array containing the password
+          */
+         public SimpleCallbackHandler(String username, char[] password)
+         {
+             this.username = username;
+             this.password = password;
+         }
+     }