To return all successful results from a Decision table, you select the Evaluate all rows
```sql
	SELECT * FROM table_name WHERE ...
```
If this is not selected it returns the first instance that it finds.

## Conflict tests

Checking for conflicts identifies if your Decision Rule prevents one or more of its rows or branches from ever being used. Show conflicts verifies incorrect Conditions.
## Completeness tests

Show completeness identifies a Decision table that has missing Conditions or a Decision tree that has missing branches. The system adds rows to indicate tests that are missing in the original Decision Rule.

