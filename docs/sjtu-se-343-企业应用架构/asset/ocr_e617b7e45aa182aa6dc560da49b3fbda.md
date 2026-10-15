+   - The RMI Registry
+     - The first remote object is a bootstrap registry service.
+     - RMI URLs :
+       rmi://regserver.mycompany.com:1099/central_warehouse

+   - Here is the code for
+     - registering a WarehouseImpl object with the RMI registry on the same server:

```
WarehouseImpl centralWarehouse = new WarehouseImpl();
Context namingContext = new InitialContext();
namingContext.bind("rmi:central_warehouse",
    centralWarehouse);
```