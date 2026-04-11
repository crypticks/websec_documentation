Literally just use parametrised queries.

```
PreparedStatement statement = connection.prepareStatement("SELECT * FROM products WHERE category = ?"); 
statement.setString(1, input); 
ResultSet resultSet = statement.executeQuery();
```

Don't use string concatenation. However, this does not work in table/column names, ORDER BY, etc. For those, whitelisting or a substitute logic might be needed to give the same funcitonality.