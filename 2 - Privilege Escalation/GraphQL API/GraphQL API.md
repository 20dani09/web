____

# Introspection

In Repeater, right-click anywhere within the **Request** panel of the message editor, then select **GraphQL > Set introspection query** to insert an introspection query into the request body.

```json
{
  "query": "query IntrospectionQuery {\n  __schema {\n    queryType {\n      name\n    }\n    mutationType {\n      name\n    }\n    subscriptionType {\n      name\n    }\n    types {\n      ...FullType\n    }\n    directives {\n      name\n      description\n      args {\n        ...InputValue\n      }\n    }\n  }\n}\n\nfragment FullType on __Type {\n  kind\n  name\n  description\n  fields(includeDeprecated: true) {\n    name\n    description\n    args {\n      ...InputValue\n    }\n    type {\n      ...TypeRef\n    }\n    isDeprecated\n    deprecationReason\n  }\n  inputFields {\n    ...InputValue\n  }\n  interfaces {\n    ...TypeRef\n  }\n  enumValues(includeDeprecated: true) {\n    name\n    description\n    isDeprecated\n    deprecationReason\n  }\n  possibleTypes {\n    ...TypeRef\n  }\n}\n\nfragment InputValue on __InputValue {\n  name\n  description\n  type {\n    ...TypeRef\n  }\n  defaultValue\n}\n\nfragment TypeRef on __Type {\n  kind\n  name\n  ofType {\n    kind\n    name\n    ofType {\n      kind\n      name\n      ofType {\n        kind\n        name\n      }\n    }\n  }\n}"
}
```

# Accessing private GraphQL posts

```json
{
  "query": "query getBlogPost($id: Int!) {\n  getBlogPost(id: $id) {\n    image\n    title\n    author\n    date\n    paragraphs\n    postPassword\n    isPrivate\n  }\n}",
  "operationName": "getBlogPost",
  "variables": {
    "id": 3
  }
}
```

![[Pasted image 20240913053720.png]]

