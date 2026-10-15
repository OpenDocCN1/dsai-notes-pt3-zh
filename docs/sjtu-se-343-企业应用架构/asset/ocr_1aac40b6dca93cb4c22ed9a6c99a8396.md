```
grant principalClass "principalName"

PrivilegedAction action = new
    PrivilegedAction()
    {
        public Object run()
        {
            // run with permissions of subject principals
            ...
        }
    };
Subject.doAsPrivileged(subject, action, null);
// or doAs(subject, action)
```