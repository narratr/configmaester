# Config Maester

Service for providing versioned and hierarchical configurations (temporary title)

## Definitions

**Configuration** - The configuration is represented as a json document.

**Requestor** - Entity requesting for a configuration.

**Namespace** - Describes the type of the requestor in a hierarchical way, for example: `AppName.Region.Role` or `MyApp.WestUS.FrontEnd`.

**Requestor Name** - A unique name for the configuration requestor, for example: `FE_1` or `86d79a7a-015c-45c8-bb7b-114fe527b11d`.

**Full Name** - The namespace + the name, for example: `MyApp.WestUS.FrontEnd.FE_1` .

## API

### Get Configuration

    GET /config[/path]?name={fullName}&version={version}
    Get the configuration for a requestor with {fullName} and {version}

*path is optional, by default get the entire configuration otherwise path will determine a value inside the configuration*

*version is optional and by default is latest*

**Output**

    {
        config: {config},
        version: {version}
    }

### Replace Configuration

    PUT /config[/path]?namespace={namespace}
    Replace the configuration for a specific namespace or for all if not passed

*the configuration is a json document passed in the request body.*

*path is optional, by default will replace the entire configuration*

*can pass more than 1 namespace in a request for changing configurations for several namespaces*

**Output**

    {
        version: {the new version}
    }

