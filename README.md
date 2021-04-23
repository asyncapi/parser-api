# parser-api
Global API definition for all AsyncAPI Parser implementations.

The API follows an Intent-driven design approach, based on user intents rather than technical mechanics.

An **Intent** represents a user intention of performing an action that solves a clear use case. 

For example, `Buy five watermelons` is the intent for `Going to the fruit shop, grab five watermelons, go to the counter, pay with cash, put the watermelon in a bag, exit the shop`.

Based on this principle, we have built an API based on the intents of the end-users, hiding the complexity of the tasks (do not care about going to the fruit shop, we do that for you) and providing better usability.
We tried to cover most use cases; however, we cannot think of every use case, so if you feel like the API is missing an intent, please create a feature request with it.

Find all Parser API versions and definitions [here](docs).

## Design

Intents are wrapped in models. Models are spec-independent but based on AsyncAPI concepts that will always exist regardless of the specification version. 

The upsides of using this approach are:
- Better user experience. Intents are much simple to use and do not force users to know about all spec internals.
- Improves resiliency to breaking changes on the final user code. Most of the time, users will **only** need to upgrade to the latest version of the parser to be up-to-date with the latest spec.

All individual parsers are following the intent API. Even though that the individual parsers maintain an individual release cycle, changes to the intent API will force the individual parsers to update as well.
> Say we release a new spec version and we are forced to create a breaking change and force a major version change for the intent API (say from version 2 -> 3) the individual parsers are then forced to make a major version change as well (say JS parser go from version 1 -> 2).

Each parser will therefore maintain its own compatibility matrix between which specification and intent API versions are supported in which parser version.

### Models 

These are the models in the intent API:
- **AsyncAPI** is the root model. Most of the intents are here, so users don't need to navigate through the object hierarchy.
- **Channel** describes a `topic`/`channel` a Message is transmitted over by some Operation.
- **Contact** contains Contact information of the Application or Client API.
- **Correlation Id** specifies an identifier at design time that can used for message tracing and correlation.
- **Info** contains defined information about your Application.
- **License** contains License information of the Application or Client API.
- **Message** represents a message in your message-driven architecture. They can relate to Operations and Channels, but the relationship is not mandatory. 
- **OauthFlow** holds configuration details for a supported OAuth Flow.
- **OauthFlows** allows configuration of the supported OAuth Flows.
- **Operation** describes an action performed by the Application or the Client. It links messages with channels.
- **Schema** is a superset of the [JSON Schema Specification Draft 07](https://json-schema.org/understanding-json-schema/basics.html). Beside the adjustments estated in https://www.asyncapi.com/docs/specifications/2.0.0#schemaObject, there is also a new method `name()` and `hasName()` for handling the name of the schema in case it has one.
- **SecurityScheme** represents security specifications for servers.
- **Server** represents a Server in your message-driven architecture. Application or Client always want to connect to some server.
- **ServerVariable** represents a Server Variable for server URL template substitution.
- **Tag** contains metadata.

## Development
To avoid polluting the API with intents that have no apparent use case or can be replaced by a call to another model, we have defined the following rule:

Intents at the root model (`AsyncAPI`) **SHOULD** never return properties of other models but instead answer questions, return the model itself or a collection of models.
