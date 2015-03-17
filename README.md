# Migrator.NET
Database migrations for .NET. Based on the idea of Rails ActiveRecord Migrations.

##forked for this reason:

We work in 2 teams that share a single Database 
with a common shared part 
and 2 Team-specific sets of Tables.

##We like to set up 3 SchemaInfo-Tables to not disturb the other team where possible:
1. SchemaInfoShared
2. SchemaInfoProjectA
3. SchemaInfoProjectB


##With our Fork we've added a Parameter: SchemaTableInfo
...to MSBuild-Task
```
 <Migrate Provider="SqlServer" 
      SchemaInfoTableName="SchemaInfoPDB"	
      Connectionstring="the connection string comes here..."		
      Migrations="@(MigrationAssemblies)" To="$(SchemaVersion)"/> 
```

...to Console-Application (after the last required parameter)

```
usage:
Migrator.Console.exe provider connectionString migrationsAssembly [options]

        provider          The database provider (SqlServer, MySql, Postgre)
        connectionString  Connection string to the database
        migrationAssembly Path to the assembly containing the migrations
        schemaInfoTableName optional: Path to the DB-Table that stores Versions (SchemaInfo is default)
Options:
        -version NO       To specific version to migrate the database to
        -list             List migrations
        -trace            Show debug informations
        -dump FILE        Dump the database schema as migration code
        -dryrun           Simulation mode (don't actually apply/remove any migrations) 
```

Default value is still "SchemaInfo" but now it can be overwritten.

