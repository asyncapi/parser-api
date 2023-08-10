# parser-api

Global API definition for all AsyncAPI Parser implementations.

The API follows an Intent-driven design approach based on user intents rather than technical mechanics.

An **Intent** represents a user's intention of performing an action that solves a clear use case. 

For example, `Buy five watermelons` is the intent for `Going to the fruit shop, grab five watermelons, go to the counter, pay with cash, put the watermelon in a bag, exit the shop`.

Based on this principle, we have built an API based on the intents of the end-users, hiding the complexity of the tasks (do not care about going to the fruit shop, we do that for you) and providing better usability.
We tried to cover most use cases; however, we cannot think of every use case, so if you feel the API is missing an intent, please create a feature request with it.

Find the documentation for the current Parser API in [docs/api.md](docs/api.md).

## Design

Intents are wrapped in models. Models are spec-independent but based on AsyncAPI concepts that will always exist regardless of the specification version. 

The upsides of using this approach are:
- Better user experience. Intents are simple and do not force users to know about all spec internals.
- Improves resiliency to breaking changes on the final user code. Most of the time, users will **only** need to upgrade to the latest version of the parser to be up-to-date with the latest spec.

All individual parsers follow the intent API. Even though the individual parsers maintain an individual release cycle, changes to the intent API will force the individual parsers to update as well.
> Say we release a new spec version, and we are forced to create a breaking change and, therefore, force a major version release for the intent API (say from version 2 -> 3). Then, the individual parsers will be forced to release a major version as well (i.e. parser-go from version 1 -> 2).

Each parser will therefore maintain its own compatibility matrix between which specification and intent API versions are supported in which parser version.

### Models 

These are the most important models in this API:

- **AsyncAPIDocument** is the root model. Most of the intents are here, so users don't need to navigate through the object hierarchy.
- **Binding** is a mechanism to define protocol-specific information.
- **Channel** describes a `topic`/`channel` a Message is transmitted over by some Operation.
- **ChannelParameter** represents a Channel Parameter for channel address template substitution.
- **Components** holds a set of reusable objects for different aspects of the AsyncAPI specification. 
- **Contact** contains Contact information of the Application or Client API.
- **CorrelationId** specifies an identifier at design time that can be used for message tracing and correlation.
- **Extension** represents the value of a single object extensions.
- **ExternalDocumention** contains external documentation source described by External Documentation.
- **Info** contains defined information about the Application or Client API.
- **License** contains License information of the Application or Client API.
- **Message** represents a message in your message-driven architecture. They can relate to Operations and Channels, but the relationship is not mandatory.
- **MessageExample** defines sample payload and headers examples of the described Message.
- **MessageTrait** defines reusable Message parts.
- **OAuthFlow** holds configuration details for a supported OAuth Flow.
- **OAuthFlows** allows configuration of the supported OAuth Flows.
- **Operation** describes an action performed by the Application or the Client. It links messages with channels.
- **OperationReply** describes the reply characteristic in a request-reply Operation.
- **OperationReplyAddress** defines the address for the Operation Reply.
- **OperationTrait** defines reusable Operation parts.
- **Schema** is a superset of the [JSON Schema Specification Draft 07](https://json-schema.org/understanding-json-schema/basics.html). See https://www.asyncapi.com/docs/specifications/latest#schemaObject.
- **SecurityRequirement** represents used Security Scheme as security mechanism for Server and Operation with possible scopes.
- **SecurityScheme** represents security specification for Server and Operation.
- **Server** represents a Server in your message-driven architecture. Application or Client always wants to connect to some server.
- **ServerVariable** represents a Server Variable for server URL template substitution.
- **Tag** contains metadata described by Tag.

> **Note**
> Each model described has its corresponding collection model (except **AsyncAPIDocument**), such as **Servers**.

## Development

To avoid polluting the API with intents that have no clear use case or can be replaced by a call to another model, we have defined the following rule:

Intents at the root model (`AsyncAPI`) **SHOULD** never return properties of other models but instead answer questions, return the model itself or a collection of models.
