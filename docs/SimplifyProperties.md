# Determining the properties for the model

In order to determine all the possible properties a schema can be, we both infer and use existing definitions, however we need to define a precedence for JSON Schema keywords for in which order the properties are inferred or determined.

## Precedence
The precedence of keywords are in which order we infer or determine properties in. The following are the precedence for determining types:

`properties` --> `allOf` --> `oneOf` --> `anyOf` --> `then` --> `else`

# Properties
All properties are recursively simplified using the main simplification wrapper `simplifyRecursive` which ensures if it come across a schema of type object it splits them out into a reference and new instance of the common model.

### Non-mentioned keywords
Any keywords not mentioned as a title are all cumulating the properties.