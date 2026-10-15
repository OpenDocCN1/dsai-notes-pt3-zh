```
String cname = name.replace('.', '/') + ".caesar";
FileInputStream in = null;
in = new FileInputStream(cname);
try {
    ByteArrayOutputStream buffer = new ByteArrayOutputStream();
    int ch;
    while ((ch = in.read()) != -1) {
        byte b = (byte) (ch - key);
        buffer.write(b);
    }
    in.close();
    return buffer.toByteArray();
}
finally
{
    in.close();
}
private int key;
```