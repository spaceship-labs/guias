# Crear roles para usuario

```
use yourDB 

db.createRole( { 
  role: "ReadUpdate", 
  privileges: [ { resource: { db: "yourDB", collection: "" }, 
  actions: ["find","update","insert"] } ], roles: [] 
} ) 

db.revokeRolesFromUser( 
  "userDev", 
  [ { role: "dbOwner", db: "yourDB" } ] 
) 
  
db.grantRolesToUser( 
  "userDev", 
  [ { role: "ReadUpdate", db: "yourDB" } ] 
)

```
