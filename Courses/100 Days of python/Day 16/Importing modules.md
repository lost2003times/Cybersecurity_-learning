```
from prettytable import PrettyTable
table = PrettyTable()
table.add_column("Pokemon Name",["Pikachu","Charlizard"])
table.add_column("Type",["Lighting","Fire"])
table.align = "l"
print(table)
```

pip install PrettyTable