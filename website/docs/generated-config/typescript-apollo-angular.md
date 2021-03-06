This plugin generates Apollo services (`Query`, `Mutation` and `Subscription`) with TypeScript typings.

It will generate a strongly typed Angular service for every defined query, mutation or subscription. The generated Angular services are ready to inject and use within your Angular component.

It extends the basic TypeScript plugins: `@graphql-codegen/typescript`, `@graphql-codegen/typescript-operations` - and thus shares a similar configuration.

To shed some more light regards this template, it's recommended to go through the this article: http://apollographql.com/docs/angular/basics/services.html , and to read the Code Generation with Apollo Angular: https://the-guild.dev/blog/apollo-angular-12

## Installation

:::shell Using `yarn`

    $ yarn add -D @graphql-codegen/typescript-apollo-angular

:::

## API Reference

### `ngModule`

type: `string`

Allows to define `ngModule` as part of the plugin's config so it's globally available.

#### Usage Examples

```yml
config:
  ngModule: ./path/to/module#MyModule
```

### `namedClient`

type: `string`

Defined the global value of `namedClient`.

#### Usage Examples

```yml
config:
  namedClient: 'customName'
```

### `serviceName`

type: `string`

Defined the global value of `serviceName`.

#### Usage Examples

```yml
config:
  serviceName: 'MySDK'
```

### `serviceProvidedInRoot`

type: `boolean`

Defined the global value of `serviceProvidedInRoot`.

#### Usage Examples

```yml
config:
  serviceProvidedInRoot: false
```

### `sdkClass`

type: `boolean`
default: `false`

Set to `true` in order to generate a SDK service class that uses all generated services.


### `querySuffix`

type: `string`
default: `GQL`

Allows to define a custom suffix for query operations.

#### Usage Examples

```yml
config:
  querySuffix: 'QueryService'
```

### `mutationSuffix`

type: `string`
default: `GQL`

Allows to define a custom suffix for mutation operations.

#### Usage Examples

```yml
config:
  mutationSuffix: 'MutationService'
```

### `subscriptionSuffix`

type: `string`
default: `GQL`

Allows to define a custom suffix for Subscription operations.

#### Usage Examples

```yml
config:
  subscriptionSuffix: 'SubscriptionService'
```

### `apolloAngularPackage`

type: `string`
default: `'apollo-angular'`

Allows to define a custom Apollo-Angular package to import types from.


### `noGraphQLTag`

type: `boolean`



### `gqlImport`

type: `string`



### `noExport`

type: `boolean`



### `dedupeOperationSuffix`

type: `boolean`



### `omitOperationSuffix`

type: `boolean`



### `operationResultSuffix`

type: `string`



### `documentVariablePrefix`

type: `string`



### `documentVariableSuffix`

type: `string`



### `fragmentVariablePrefix`

type: `string`



### `fragmentVariableSuffix`

type: `string`



### `documentMode`

type: `DocumentMode`



### `importOperationTypesFrom`

type: `string`



### `importDocumentNodeExternallyFrom`

type: `string`



### `scalars`

type: `ScalarsMap`

Extends or overrides the built-in scalars and custom GraphQL scalars to a custom type.

#### Usage Examples

```yml
config:
  scalars:
    DateTime: Date
    JSON: "{ [key: string]: any }"
```

### `namingConvention`

type: `NamingConvention`
default: `pascal-case#pascalCase`

Allow you to override the naming convention of the output.
You can either override all namings, or specify an object with specific custom naming convention per output.
The format of the converter must be a valid `module#method`.
Allowed values for specific output are: `typeNames`, `enumValues`.
You can also use "keep" to keep all GraphQL names as-is.
Additionally you can set `transformUnderscore` to `true` if you want to override the default behavior,
which is to preserves underscores.

#### Usage Examples

##### Override All Names
```yml
config:
  namingConvention: lower-case#lowerCase
```

##### Upper-case enum values
```yml
config:
  namingConvention:
    typeNames: pascal-case#pascalCase
    enumValues: upper-case#upperCase
```

##### Keep names as is
```yml
config:
  namingConvention: keep
```

##### Remove Underscores
```yml
config:
  namingConvention:
    typeNames: pascal-case#pascalCase
    transformUnderscore: true
```

### `typesPrefix`

type: `string`
default: ``

Prefixes all the generated types.

#### Usage Examples

```yml
config:
  typesPrefix: I
```

### `skipTypename`

type: `boolean`
default: `false`

Does not add __typename to the generated types, unless it was specified in the selection set.

#### Usage Examples

```yml
config:
  skipTypename: true
```

### `nonOptionalTypename`

type: `boolean`
default: `false`

Automatically adds `__typename` field to the generated types, even when they are not specified
in the selection set, and makes it non-optional

#### Usage Examples

```yml
config:
  nonOptionalTypename: true
```