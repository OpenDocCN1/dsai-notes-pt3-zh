# Web Service Client - A

+   - Create a plain java project
+   - Generate the necessary files for client and add them to the project
+     `wsimport -keep -p warehouse.server`
+     `http://localhost:8080/WebServices/warehouse?wsdl`
+   - Write a Web Service Client

```
public class WarehouseClient
{
    public static void main(String[] args) throws NamingException, RemoteException
    {
        WarehouseService service = new WarehouseService();
        Warehouse port = service.getPort(Warehouse.class);

        String descr = "ZapXpress Microwave Oven";
        double price = port.getPrice(descr);
        System.out.println(descr + ": " + price);
    }
}
```

![](bbox=[0.72, 0.06, 0.95, 0.42])