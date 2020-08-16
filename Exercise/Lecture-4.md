# ADD & DROP CONSTRAINT IN SQL
---

The ALTER TABLE command is used to ADD, DROP or UPDATE column in an already created or existing table. You can also ADD & DROP various constraint using ALTER TABLE command. 

> Must use constraint name for easy to handle constraint 

### ADD CONSTRAINT
```
# syntax
ALTER TABLE Table_Name
ADD CONSTRAINT constraint_Name Constraint (Column_Name)
```
```SQL
ALTER TABLE Std_Info
ADD CONSTRAINT std_name_notnull_constraint NOT NULL (std_Name)
```

### DROP CONSTRAINT
```
ALTER TABLE Table_Name
DROP CONSTRAINT Constraint_Name
```
```SQL
ALTER TABLE Std_Info
DROP CONSTRAINT std_name_notnull_constraint
```
