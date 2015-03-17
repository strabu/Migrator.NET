# Migrator.NET
Database migrations for .NET. Based on the idea of Rails ActiveRecord Migrations.

forked for this reason:

We work in 2 teams that share a single Database 
with a common shared part 
and 2 Team-specific sets of Tables.

We like to set up 3 SchemaInfo-Tables to not disturb the other team where possible:
1) SchemaInfoShared
2) SchemaInfoProjectA
3) SchemaInfoProjectB


With our Fork we've added a Parameter: SchemaTableInfo
1) to MSBuild-Task
2) to Console-Application (after the last required parameter)

Default value is still "SchemaInfo" but now it can be overwritten.

