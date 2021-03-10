# Flow.js
Flow.js, future node.js library for database manipulation and database description

```

        const db = new Flow.Database('./db.flow');

        class Users extends db.Table {

            Structure = {
                
                id: Number,
                name: String,
                char: Flow.Char

            };
            
            Encoding = Flow.UTF8;

            Scripts = {

                getAllData(table, ...args) {

                    return table;

                },

                deleteTable(table) {

                    return db.Drop(table); //null

                }

            };

        }


        const allDataFromTable = Users.getAllData();        

        db.Read(({ Users }) => result => {

            result.name = "Philip"; //overwrite

            return result;

        });
        
        db.Add(({ Users }) => ({

            name: "John",
            id: 0

        }));

        db.Remove(({ Users }) => ({

            name: "John"

        }));


        Flow.DestroyDatabase(db);

```
