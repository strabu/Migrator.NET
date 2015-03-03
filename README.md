# Migrator.NET
Database migrations for .NET. Based on the idea of Rails ActiveRecord Migrations.

forked for this reason:

We work in 2 teams that share a single Database 
with a common shared part 
and 2 Team-specific sets of Tables.

We like to set up 3 SchemaInfo-Tables to not disturb the other team where possible:
1) SharedSchemaInfo
2) ProjectASchemaInfo
3) ProjectBSchemaInfo

The idea is to add a Meta-Attribute that defines the name of the used SchemaInfo-Table 
or an optional parameter at [Migration()]
that defines the Name of the SchemaInfo-Table
