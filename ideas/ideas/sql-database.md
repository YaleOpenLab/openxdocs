# SQL database

Opensolar currently uses boltDB - a key value pair database with limited functionality and room for scalability. Migrating to a SQL database would help create relations between different entities on the platform \(eg between investors, users and recipients\), help create a good database structure, and be more scalable. PostgreSQL or MySQL would be ideal options to look at for migration since they are designed to be used in production environments. This step would require the construction of a suitable database architecture along with scripts assisting in migration.

