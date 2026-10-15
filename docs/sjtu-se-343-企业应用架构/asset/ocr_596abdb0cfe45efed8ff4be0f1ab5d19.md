```
public interface Warehouse extends Remote
{
    double getPrice(String description) throws RemoteException;
    Product getProduct(List<String> keywords) throws RemoteException;
}
```

![](bbox=[0.24, 0.38, 0.82, 0.93])