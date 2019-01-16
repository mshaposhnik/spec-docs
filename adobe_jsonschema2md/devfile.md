
# The Root Schema of DevFile object Schema

```
```


| Abstract | Extensible | Status | Identifiable | Custom Properties | Additional Properties | Defined In |
|----------|------------|--------|--------------|-------------------|-----------------------|------------|
| Can be instantiated | Yes | Experimental | No | Forbidden | Permitted | [devfile.json](devfile.json) |

# The Root Schema of DevFile object Properties

| Property | Type | Required | Defined by |
|----------|------|----------|------------|
| [commands](#commands) | `object[]` | Optional | The Root Schema of DevFile object (this schema) |
| [name](#name) | `string` | **Required** | The Root Schema of DevFile object (this schema) |
| [projects](#projects) | `object[]` | Optional | The Root Schema of DevFile object (this schema) |
| [specVersion](#specversion) | `string` | **Required** | The Root Schema of DevFile object (this schema) |
| [tools](#tools) | `object[]` | **Required** | The Root Schema of DevFile object (this schema) |
| `*` | any | Additional | this schema *allows* additional properties |

## commands
### The Commands Schema

`commands`

* is optional
* type: `object[]`
* defined in this schema

### commands Type


Array type: `object[]`

All items must be of the type:
`object` with following properties:


| Property | Type | Required |
|----------|------|----------|
| `actions`| array | **Required** |
| `attributes`|  | Optional |
| `name`| string | **Required** |



#### actions
##### The Command Actions Schema

undefined

`actions`

* is **required**
* type: `object[]`


##### actions Type


Array type: `object[]`

All items must be of the type:
`object` with following properties:


| Property | Type | Required |
|----------|------|----------|
| `command`| string | **Required** |
| `tool`| string | **Required** |
| `type`| string | **Required** |
| `workdir`| string | Optional |



#### command

The actual action command-line string

`command`

* is **required**
* type: `string`

##### command Type


`string`






##### command Example

```json
mvn package
```




#### tool

Describes tool to which given action relates

`tool`

* is **required**
* type: `string`

##### tool Type


`string`






##### tool Example

```json
mvn-stack
```




#### type

Describes action type

`type`

* is **required**
* type: `string`

##### type Type


`string`






##### type Example

```json
exec
```




#### workdir

Working directory where the schema should be executed

`workdir`

* is optional
* type: `string`

##### workdir Type


`string`






##### workdir Example

```json
/projects/spring-petclinic
```











#### attributes

undefined

`attributes`

* is optional
* type: reference

##### attributes Type


* []() – `#/definitions/attributes`







#### name

Describes the name of the command. Should be unique per commands set.

`name`

* is **required**
* type: `string`

##### name Type


`string`






##### name Example

```json
build
```









## name
### Devfile Name

`name`

* is **required**
* type: `string`
* defined in this schema

### name Type


`string`






### name Example

```json
"petclinic-dev-environment"
```


## projects
### The Projects Schema

Description of the project sources location and type

`projects`

* is optional
* type: `object[]`
* defined in this schema

### projects Type


Array type: `object[]`

All items must be of the type:
`object` with following properties:


| Property | Type | Required |
|----------|------|----------|
| `name`| string | **Required** |
| `source`| object | **Required** |



#### name

undefined

`name`

* is **required**
* type: `string`

##### name Type


`string`






##### name Example

```json
petclinic
```




#### source
##### The Project Source Schema

undefined

`source`

* is **required**
* type: `object`

##### source Type

Unknown type `object`.

```json
{
  "type": "object",
  "title": "The Project Source Schema",
  "required": [
    "type",
    "location"
  ],
  "properties": {
    "type": {
      "type": "string",
      "description": "Project-s source type.",
      "examples": [
        "git",
        "github",
        "zip"
      ]
    },
    "location": {
      "type": "string",
      "description": "Project-s source location address. Should be URL for git and github located projects, and file:// for zip.",
      "examples": [
        "git@github.com:spring-projects/spring-petclinic.git"
      ]
    }
  },
  "simpletype": "`object`"
}
```












## specVersion
### Devfile Schema Specification Version

`specVersion`

* is **required**
* type: `string`
* defined in this schema

### specVersion Type


`string`






### specVersion Example

```json
"0.0.1"
```


## tools
### The Tools Schema

`tools`

* is **required**
* type: `object[]`
* defined in this schema

### tools Type


Array type: `object[]`

All items must be of the type:
`object` with following properties:


| Property | Type | Required |
|----------|------|----------|
| `id`| string | Optional |
| `local`| string | Optional |
| `name`| string | **Required** |
| `type`| string | **Required** |



#### id

Describes the tool FQN

`id`

* is optional
* type: `string`

##### id Type


`string`






##### id Example

```json
eclipse/maven-jdk8:1.0.0
```




#### local

Describes location of Kubernetes list yaml file. Applicable only for 'kubernetes' and 'openshift' type tools.

`local`

* is optional
* type: `string`

##### local Type


`string`






##### local Example

```json
petclinic-app.yaml
```




#### name

Describes the name of the tool. Should be unique per tool set.

`name`

* is **required**
* type: `string`

##### name Type


`string`






##### name Example

```json
mvn-stack
```




#### type

Describes type of the tool, e.g. whether it is an plugin or editor or other type

`type`

* is **required**
* type: `string`

##### type Type


`string`






##### type Examples

```json
chePlugin
```

```json
cheEditor
```









