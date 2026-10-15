# When to Use Enterprise Beans?

+   - You should consider using enterprise beans if your application has any of the following requirements.
+     - The application must be scalable.
+     - Transactions must ensure data integrity.
+     - The application will have a variety of clients.
+   - Types of Enterprise Beans
+     - Session
+       - Performs a task for a client; optionally, may implement a web service
+     - Message-driven
+       - Acts as a listener for a particular messaging type, such as the Java Message Service API