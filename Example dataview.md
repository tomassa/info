
```dataview
    LIST
    FROM #read
```

```dataview
    table L.text
    where file.lists
    flatten file.lists as L
    where contains(L.text, [[read]])
```