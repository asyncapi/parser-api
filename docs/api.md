# AsyncAPI Parser API v2.0.0

## AsyncAPIDocument
- version(): `string`
- info(): `Info`
- hasDefaultContentType(): `boolean`
- defaultContentType(): `string` | `undefined`
- servers(): `Servers`
- channels(): `Channels`
- operations(): `Operations`
- messages(): `Messages`
- schemas(): `Schemas`
- securitySchemes(): `SecuritySchemes`
- allServers(): `Servers`
- allChannels(): `Channels`
- allOperations(): `Operations`
- allMessages(): `Messages`
- allSchemas(): `Schemas`
- components(): `Components`
- extensions(): `Extensions`

## Binding
- protocol(): `string`
- version(): `string`
- value(): `any`
- extensions(): `Extensions`

## Bindings
- all(): `Binding[]`
- isEmpty(): `boolean`
- filterBy(filter: `(binding: Binding) => boolean`): `Binding[]`
- get(id: `string`): `Binding` | `undefined`
- has(id: `string`): `boolean`
- extensions(): `Extensions`

## Channel
- id(): `string`
- address(): `string`
- servers(): `Servers`
- operations(): `Operations`
- messages(): `Messages`
- parameters(): `ChannelParameters`
- hasTitle(): `boolean`
- title(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- bindings(): `Bindings`
- extensions(): `Extensions`

## Channels
- all(): `Channel[]`
- isEmpty(): `boolean`
- filterBy(filter: `(channel: Channel) => boolean`): `Channel[]`
- filterBySend(): `Channel[]`
- filterByReceive(): `Channel[]`
- filterByTags(tags: `string[]`): `Channel[]`
- get(id: `string`): `Channel` | `undefined`
- has(id: `string`): `boolean`

## ChannelParameter
- id(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- hasSchema(): `boolean`
- schema(): `Schema` | `undefined`
- hasLocation(): `boolean`
- location(): `string` | `undefined`
- extensions(): `Extensions`

## ChannelParameters
- all(): `ChannelParameter[]`
- isEmpty(): `boolean`
- filterBy(filter: `(parameter: ChannelParameter) => boolean`): `ChannelParameter[]`
- get(id: `string`): `ChannelParameter` | `undefined`
- has(id: `string`): `boolean`

## Components
- servers(): `Servers`
- channels(): `Channels`
- messages(): `Messages`
- operations(): `Operations`
- schemas(): `Schemas`
- channelParameters(): `ChannelParameters`
- serverVariables(): `ServerVariables`
- operationTraits(): `OperationTraits`
- messageTraits(): `MessageTraits`
- replies(): `OperationReplies`
- replyAddresses(): `OperationReplyAddresses`
- correlationIds(): `CorrelationIds`
- securitySchemes(): `SecuritySchemes`
- tags(): `Tags`;
- externalDocs(): `ExternalDocumentations`;
- serverBindings(): `Map<string, Bindings>`
- channelBindings(): `Map<string, Bindings>`
- operationBindings(): `Map<string, Bindings>`
- messageBindings(): `Map<string, Bindings>`
- isEmpty(): `boolean`

## Contact
- hasName(): `boolean`
- name(): `string` | `undefined`
- hasUrl(): `boolean`
- url(): `string` | `undefined`
- hasEmail(): `boolean`
- email(): `string` | `undefined`
- extensions(): `Extensions`

## CorrelationId
- location(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- extensions(): `Extensions`

## CorrelationIds
- all(): `CorrelationId[]`
- isEmpty(): `boolean`
- filterBy(filter: `(correlationId: CorrelationId) => boolean`): `CorrelationId[]`
- get(id: `string`): `CorrelationId` | `undefined`
- has(id: `string`): `boolean`

## Extension
- id(): `string`
- value(): `any`

## Extensions
- all(): `Extension[]`
- isEmpty(): `boolean`
- filterBy(filter: `(extension: Extension) => boolean`): `Extension[]`
- get(id: `string`): `Extension` | `undefined`
- has(id: `string`): `boolean`

## ExternalDocumention
- id(): `string` | `undefined`
- url(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- extensions(): `Extensions`

## Info
- title(): `string`
- version(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- hasId(): `boolean` 
- id(): `string` | `undefined`
- hasTermsOfService(): `boolean`
- termsOfService(): `string` | `undefined`
- hasContact(): `boolean`
- contact(): `Contact` | `undefined`
- hasLicense(): `boolean`
- license(): `License` | `undefined`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- extensions(): `Extensions`

## License
- name(): `string`
- hasUrl(): `boolean`
- url(): `string` | `undefined`
- extensions(): `Extensions`

## Message
- id(): `string`
- hasSchemaFormat(): `boolean`
- schemaFormat(): `string` | `undefined`
- hasMessageId(): `boolean`
- hasCorrelationId(): `boolean`
- correlationId(): `CorrelationId` | `undefined`
- hasContentType(): `boolean`
- contentType(): `string` | `undefined`
- hasPayload(): `boolean`
- payload(): `Schema` | `undefined`
- hasHeaders(): `boolean`
- headers(): `Schema` | `undefined`
- hasTitle(): `boolean`
- title(): `string` | `undefined`
- hasName(): `boolean`
- name(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- examples(): `MessageExamples`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- servers(): `Servers`
- channels(): `Channels`
- operations(): `Operations`
- traits(): `MessageTraits`
- bindings(): `Bindings`
- extensions(): `Extensions`

## Messages
- all(): `Message[]`
- isEmpty(): `boolean`
- filterBy(filter: `(message: Message) => boolean`): `Message[]`
- filterBySend(): `Message[]`
- filterByReceive(): `Message[]`
- filterByTags(tags: `string[]`): `Message[]`
- get(id: `string`): `Message` | `undefined`
- has(id: `string`): `boolean`

## MessageExample
- hasName(): `boolean`
- name(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- headers(): `Map<string, any>` | `undefined`
- payload(): `Map<string, any>` | `undefined`
- extensions(): `Extensions`

## MessageExamples
- all(): `MessageExample[]`
- isEmpty(): `boolean`
- filterBy(filter: `(messageExample: MessageExample) => boolean`): `MessageExample[]`
- get(name: `string`): `MessageExample` | `undefined`
- has(name: `string`): `boolean`

## MessageTrait
- id(): `string`
- hasSchemaFormat(): `boolean`
- schemaFormat(): `string` | `undefined`
- hasMessageId(): `boolean`
- hasCorrelationId(): `boolean`
- correlationId(): `CorrelationId` | `undefined`
- hasContentType(): `boolean`
- contentType(): `string` | `undefined`
- hasHeaders(): `boolean`
- headers(): `Schema` | `undefined`
- hasTitle(): `boolean`
- title(): `string` | `undefined`
- hasName(): `boolean`
- name(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- examples(): `MessageExamples`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- bindings(): `Bindings`
- extensions(): `Extensions`

## MessageTraits
- all(): `MessageTrait[]`
- isEmpty(): `boolean`
- filterBy(filter: `(messageTrait: MessageTrait) => boolean`): `MessageTrait[]`
- get(id: `string`): `MessageTrait` | `undefined`
- has(id: `string`): `boolean`

## OAuthFlow
- hasAuthorizationUrl(): `boolean`
- authorizationUrl(): `string` | `undefined`
- hasTokenUrl(): `boolean`
- tokenUrl(): `string` | `undefined`
- hasRefreshUrl(): `boolean`
- refreshUrl(): `string` | `undefined`
- scopes(): `Map<string, string>`
- extensions(): `Extensions`

## OAuthFlows
- hasImplicit(): `boolean`
- implicit(): `OAuthFlow` | `undefined`
- hasPassword(): `boolean`
- password(): `OAuthFlow` | `undefined`
- hasClientCredentials(): `boolean`
- clientCredentials(): `OAuthFlow` | `undefined`
- hasAuthorizationCode(): `boolean`
- authorizationCode(): `OAuthFlow` | `undefined`
- extensions(): `Extensions`

## Operation
- id(): `string`
- action(): `enum{'send', 'receive', 'publish', 'subscribe'}`
- isSend(): `boolean`
- isReceive(): `boolean`
- hasOperationId(): `boolean`
- operationId(): `string` | `undefined`
- hasTitle(): `boolean`
- title(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- security(): `SecurityRequirements[]`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- servers(): `Servers`
- channels(): `Channels`
- messages(): `Messages`
- reply(): `OperationReply` | `undefined`
- traits(): `OperationTraits`
- bindings(): `Bindings`
- extensions(): `Extensions`

## Operations
- all(): `Operation[]`
- isEmpty(): `boolean`
- filterBy(filter: `(operation: Operation) => boolean`): `Operation[]`
- filterBySend(): `Operation[]`
- filterByReceive(): `Operation[]`
- filterByTags(tags: `string[]`): `Operation[]`
- get(id: `string`): `Operation` | `undefined`
- has(id: `string`): `boolean`

## OperationReply
- id(): `string` | `undefined`
- hasAddress(): `boolean`
- address(): `OperationReplyAddress` | `undefined`
- hasChannel(): `boolean`
- channel(): `Channel` | `undefined`
- messages(): `Messages`
- extensions(): `Extensions`

## OperationReplies
- all(): `OperationReply[]`
- isEmpty(): `boolean`
- filterBy(filter: `(reply: OperationReply) => boolean`): `OperationReply[]`
- get(id: `string`): `OperationReply` | `undefined`
- has(id: `string`): `boolean`

## OperationReplyAddress
- id(): `string` | `undefined`
- location(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- extensions(): `Extensions`

## OperationReplyAddresses
- all(): `OperationReplyAddress[]`
- isEmpty(): `boolean`
- filterBy(filter: `(address: OperationReplyAddress) => boolean`): `OperationReplyAddress[]`
- get(id: `string`): `OperationReplyAddress` | `undefined`
- has(id: `string`): `boolean`

## OperationTrait
- id(): `string`
- hasOperationId(): `boolean`
- operationId(): `string` | `undefined`
- hasTitle(): `boolean`
- title(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- security(): `SecurityRequirements[]`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- bindings(): `Bindings`
- extensions(): `Extensions`

## OperationTraits
- all(): `OperationTrait[]`
- isEmpty(): `boolean`
- filterBy(filter: `(operationTrait: OperationTrait) => boolean`): `OperationTrait[]`
- get(id: `string`): `OperationTrait` | `undefined`
- has(id: `string`): `boolean`

## Schema
- $id(): `string` | `undefined`
- additionalItems(): `boolean` | `Schema`
- additionalProperties(): `boolean` | `Schema`
- allOf(): `Schema[]` | `undefined`
- anyOf(): `Schema[]` | `undefined`
- const(): `any`
- contains(): `Schema` | `undefined`
- contentEncoding(): `string` | `undefined`
- contentMediaType(): `string` | `undefined`
- default(): `any`
- definitions(): `Map<string, Schema>` | `undefined`
- description(): `string` | `undefined`
- dependencies(): `Map<string, Schema | string[]>` | `undefined`
- deprecated(): `boolean`
- discriminator(): `string` | `undefined`
- else(): `Schema` | `undefined`
- extensions(): `Extensions`
- enum(): `any[]` | `undefined`
- examples(): `any[]` | `undefined`
- exclusiveMaximum(): `number` | `undefined`
- exclusiveMinimum(): `number` | `undefined`
- format(): `string` | `undefined`
- id(): `string`
- isBooleanSchema(): `boolean`
- if(): `Schema` | `undefined`
- isCircular(): `boolean`
- items(): `Schema` | `Schema[]` | `undefined`
- maximum(): `number` | `undefined`
- maxItems(): `number` | `undefined`
- maxLength(): `number` | `undefined`
- maxProperties(): `number` | `undefined`
- minimum(): `number` | `undefined`
- minItems(): `number` | `undefined`
- minLength(): `number` | `undefined`
- minProperties(): `number` | `undefined`
- multipleOf(): `number` | `undefined`
- not(): `Schema` | `undefined`
- oneOf(): `Schema[]` | `undefined`
- pattern(): `string` | `undefined`
- patternProperties(): `Map<string, Schema>` | `undefined`
- properties(): `Map<string, Schema>` | `undefined`
- property(name: `string`): `Schema`
- propertyNames(): `Schema` | `undefined`
- readOnly(): `boolean` | `undefined`
- required(): `string[]` | `undefined`
- schemaFormat(): `string`
- then(): `Schema` | `undefined`
- title(): `string` | `undefined`
- type(): `string` | `string[]` | `undefined`
- uniqueItems(): `boolean` | `undefined`
- writeOnly(): `boolean` | `undefined`

## Schemas
- all(): `Schema[]`
- isEmpty(): `boolean`
- filterBy(filter: `(schema: Schema) => boolean`): `Schema[]`
- get(id: `string`): `Schema` | `undefined`
- has(id: `string`): `boolean`

## SecurityRequirement
- scheme(): `SecurityScheme`
- scopes(): `string[]`

## SecurityRequirements
- all(): `SecurityRequirement[]`
- filterBy(filter: `(securityRequirement: SecurityRequirement) => boolean`): `SecurityRequirement[]`
- get(name: `string`): `SecurityRequirement` | `undefined`
- has(name: `string`): `boolean`
- isEmpty(): `boolean`

## SecurityScheme
- id(): `string`
- type(): `enum{'userPassword', 'apiKey', 'X509', 'symmetricEncryption', 'asymmetricEncryption', 'httpApiKey', 'http', 'oauth2', 'openIdConnect', 'plain', 'scramSha256', 'scramSha512', 'gssapi'}`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- hasName(): `boolean`
- name(): `string` | `undefined`
- hasIn(): `boolean`
- in(): `enum{'user', 'password', 'query', 'header', 'cookie'}` | `undefined`
- hasScheme(): `boolean`
- scheme(): `string` | `undefined`
- hasBearerFormat(): `boolean`
- bearerFormat(): `string` | `undefined`
- hasFlows(): `boolean`
- flows(): `OAuthFlows` | `undefined`
- hasOpenIdConnectUrl(): `boolean`
- openIdConnectUrl(): `string` | `undefined`
- extensions(): `Extensions`

# SecuritySchemes
- all(): `SecurityScheme[]`
- isEmpty(): `boolean`
- filterBy(filter: `(securityScheme: SecurityScheme) => boolean`): `SecurityScheme[]`
- get(id: `string`): `SecurityScheme` | `undefined`
- has(id: `string`): `boolean`

## Server
- id(): `string`
- url(): `string`
- host(): `string`
- protocol(): `string`
- hasPathname(): `boolean`
- pathname(): `string` | `undefined`
- hasProtocolVersion(): `boolean`
- protocolVersion(): `string` | `undefined`
- hasTitle(): `boolean`
- title(): `string` | `undefined`
- hasSummary(): `boolean`
- summary(): `string` | `undefined`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- variables(): `ServerVariables`
- security(): `SecurityRequirements[]`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- tags(): `Tags`
- channels(): `Channels`
- operations(): `Operations`
- messages(): `Messages`
- bindings(): `Bindings`
- extensions(): `Extensions`

## Servers
- all(): `Server[]`
- isEmpty(): `boolean`
- filterBy(filter: `(server: Server) => boolean`): `Server[]`
- filterBySend(): `Server[]`
- filterByReceive(): `Server[]`
- filterByTags(tags: `string[]`): `Server[]`
- get(id: `string`): `Server` | `undefined`
- has(id: `string`): `boolean`

## ServerVariable
- id(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- hasDefaultValue(): `boolean`
- defaultValue(): `string` | `undefined`
- hasAllowedValues(): `boolean`
- allowedValues(): `string[]`
- examples(): `string[]`
- extensions(): `Extensions`

## ServerVariables
- all(): `ServerVariable[]`
- isEmpty(): `boolean`
- filterBy(filter: `(serverVariable: ServerVariable) => boolean`): `ServerVariable[]`
- get(id: `string`): `ServerVariable` | `undefined`
- has(id: `string`): `boolean`

## Tag
- id(): `string` | `undefined`
- name(): `string`
- hasDescription(): `boolean`
- description(): `string` | `undefined`
- hasExternalDocs(): `boolean`
- externalDocs(): `ExternalDocumention` | `undefined`
- extensions(): `Extensions`

## Tags
- all(): `Tag[]`
- isEmpty(): `boolean`
- filterBy(filter: `(tag: Tag) => boolean`): `Tag[]`
- get(name: `string`): `Tag` | `undefined`
- has(name: `string`): `boolean`
