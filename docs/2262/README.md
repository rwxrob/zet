# Insert JSON directly into PostgreSQL rows

Today I learned that PostgreSQL has added the `::json` notation that be appended to an existing JSON string to facilitate inserts into SQL rows (properly):

```sql
with customer_json (doc) as (
   values
    ('[
      {
        "id": 23635,
        "name": "Jerry Green",
        "comment": "Imported from facebook."
      },
      {
        "id": 23636,
        "name": "John Wayne",
        "comment": "Imported from facebook."
      }
    ]'::json)
)
insert into customer (id, name, comment)
select p.*
from customer_json l
  cross join lateral json_populate_recordset(null::customer, doc) as p
on conflict (id) do update
  set name = excluded.name,
      comment = excluded.comment;
```

It's been some time since I worked with PostgreSQL (even though I learned it in 2001 to create the entire data schema for our audit compliance data store at IBM for which I actually printed all the PostgreSQL manuals). Great to see it is just as good as it has always been. I fucking love PostreSQL when a database is actually needed. This reminds me we really do need to add a data-related mentored-learning series to go with the others.

* sql - How can I import a JSON file into PostgreSQL? - Stack Overflow  
  <https://stackoverflow.com/questions/39224382/how-can-i-import-a-json-file-into-postgresql>
