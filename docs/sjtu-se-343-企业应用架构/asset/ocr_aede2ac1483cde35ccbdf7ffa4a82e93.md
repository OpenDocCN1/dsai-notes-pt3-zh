# Custom Permission

```
if (b.action.equals("avoid"))
    return b.badWordSet().containsAll(badWordSet());
else if (b.action.equals("insert"))
{
    for (String badWord : badWordSet())
        if (b.getName().indexOf(badWord) >= 0)
            return false;
    return true;
}
else return false;
}
else return false;
}
```