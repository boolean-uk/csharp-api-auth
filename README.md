# C# Jwt Authentication Repo

A repository to demonstrate how you might add Jwt authentication to a Webapi

## Before running

- You need to examine the DatabaseContext.cs class and choose your database.  For convenience the 
  project has the EntityFramework InMemoryDatabase configured or you could choose the PostGres option  
  ensuring you update your credentials in the appsettings.json / appsettings.Development.json.
- 
## Creating the config files
```
touch appsettings.json
touch appsettings.Development.json
```
- You then need to add the following contents to both files, updating the DefaultConnectionString with your credentials:  
```
{
  "AppSettings": {
    "Token": "any secret passphrase goes here but make sure that the passphrase is really big in size"
  },
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
   "ConnectionStrings": {
    "DefaultConnectionString": "Host=HOST; Database=DATABASE; Username=USENAME; Password=PASSWORD; "
  }
}

```

# Migration (don't need this for the InMemoryDatabase option)
Now you can run a migration to create the User table:
```
add-migration FirstMigration
update-database
```


## Packages

The following versions of packages have been installed: 

bcrypt.net-core -version 4.0.3
Microsoft.AspNetCore.Authentication.Jwtbearer   -version 7.0.13
Microsoft.AspNetCore.OpenApi                    -version 7.0.13
Microsoft.EntityFrameworkCore                   -version 7.0.13
Microsoft.EntityFrameworkCore.Design            -version 7.0.13
Microsoft.EntityFrameworkCore.InMemory          -version 7.0.13
Microsoft.EntityFrameworkCore.Tools             -version 7.0.13
NpgSql.EntityFrameworkCore.PostGreSql          -version 7.0.11
Swashbuckle.AspNetCore                          -version 6.5.0
System.IdentityModel.Tokens.Jwt                 -version 7.0.3





