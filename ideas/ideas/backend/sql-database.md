# SQL database

Opensolar currently uses boltDB - a key value pair database with limited functionality and room for scalability. Migrating to a SQL database would help create relations between different entities on the platform \(eg between investors, users and recipients\), help create a good database structure, and be more scalable.

PostgreSQL or MySQL are ideal options to look at since they are designed to be used in production environments. Migrations requires the contruction of a detailed database architecture, with entities being linked to each other, the user entity being imported as a foreign key, etc. Migration would also require migration scripts which can successfully migrate data from boltDB without loss of information. Having a database architecture also enables easy audits of storage infrastructure, and one can easily understand how different parts of the backend interact with each other.

