# Prefer migrations over monolith DDL for database design

Well, there you have it. ChatGPT calls out what I suspected has taken a very strong position in the database design best practices canon: using migrations over monolithic DDLs (like I did in 2001). (For better or worse, we can blame Ruby on Rails for this.) 

## ChatGPT had this to say

Migrations are generally preferred in database design now over the monolith DDL format.

Migrations provide a more flexible and scalable approach to managing database changes. With
migrations, developers can incrementally apply changes to the database schema, allowing for
easier collaboration, continuous integration, and deployment.

Furthermore, migrations offer version control and tracking. Each migration script represents a
specific database state, making it easier to rollback problematic changes or modify existing
ones.

On the other hand, monolith DDL (Data Definition Language) formats tend to be static, as they
define the database schema in a single, fixed script. This can make it difficult to manage
changes, especially in collaborative environments where multiple developers are working on the
same project simultaneously.

Overall, migrations provide a more agile and maintainable approach to database design, allowing
for iterative development and efficient management of database schema changes.

## Script to manage

Since migrations are additive, the shell script isn't too hard for it. Just come up with a naming convention that is assured to lexicographically sort correctly and apply it in a loop with `set -e` on in case something fails. Unlike the monolith DDL approach there doesn't need to be a DROP anywhere. In fact, leaving that to be an explicit action seems prudent.

Something like the following could be placed in the same directory as the migration SQL code:

```sh
#!/bin/sh

FILES=$(ls )
```






