# ArangoDB

To create a new database *test* and user *test*, run Arango shell as root and type:

```js
arangosh> db._createDatabase("test");
arangosh> var users = require("@arangodb/users");
arangosh> users.save("test@test", "test");
arangosh> users.grantDatabase("test@test", "test");
```

You can access the web interface at <http://127.0.0.1:8529>.
