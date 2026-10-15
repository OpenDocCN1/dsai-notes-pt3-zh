# Transferring Nonremote Objects

```
```java
public class WarehouseClient
{
    public static void main(String[] args) throws NamingException, RemoteException
    {
        Context namingContext = new InitialContext();

        System.out.print("RMI registry bindings: ");
        NamingEnumeration<NameClassPair> e = namingContext.list("rmi://localhost/");
        while (e.hasMore())
            System.out.println(e.next().getName());

        String url = "rmi://localhost:1099/central_warehouse";
        Warehouse centralWarehouse = (Warehouse) namingContext.lookup(url);

        Scanner in = new Scanner(System.in);
        System.out.print("Enter keywords: ");
        List<String> keywords = Arrays.asList(in.nextLine().split("\\s+"));
        Product prod = centralWarehouse.getProduct(keywords);

        System.out.println(prod.getDescription() + ": " + prod.getPrice());
    }
}
```
```