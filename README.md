# Config Maester

Service for providing versioned and hierarchical configurations (temporary title)

## API

** Requestor ** - Entity requesting for a configuration.

** Namespace ** - Describes the type of the requestor in a hierarchical way, for example: `AppName.Region.Role` or `MyApp.WestUS.FrontEnd`.

** Requestor Name ** - A unique name for the configuration requestor, for example: `FE_1` or `86d79a7a-015c-45c8-bb7b-114fe527b11d`.

** Full Name ** - The namespace + the name, for example: `MyApp.WestUS.FrontEnd.FE_1` .

### Config

    GET /config?name={fullName}&version={version}
    Get the entire configuration for a requestor with {fullName} and {version}

** Version is optional and by default is latest **

** Output **

    {
        config: {config},
        version: {version}
    }

