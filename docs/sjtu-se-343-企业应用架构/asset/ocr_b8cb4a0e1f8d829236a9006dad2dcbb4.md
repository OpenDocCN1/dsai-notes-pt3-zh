# Custom Permission

```
public String getActions() { return action; }

public boolean equals(Object other)
{
    if (other == null) return false;
    if (!getClass().equals(other.getClass())) return false;
    WordCheckPermission b = (WordCheckPermission) other;
    if (!action.equals(b.action)) return false;
    if (action.equals("insert"))
        return getName().equals(b.getName());
    else if (action.equals("avoid"))
        return badWordSet().equals(b.badWordSet());
    else return false;
}
```