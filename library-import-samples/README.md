# Email Type Object Type 

The sample JSON file for importing the Object Type Library consists of a list of object types. 

### Description of various fields in the json file:

**objectTypeList** (JSON Array) 
- Mandatory
- Array of object types, each represented by a JSON object

<hr>

>ObjectType JSON fields

**name** (String)
- Mandatory
- Identifies the display name of the ObjectType
- Ex: "name": "Email Address"

**symbolicName** (String)
- Mandatory
- Immutable name for the object type
- Once created, it can't be edited again by the user
- Unique across all object types inside the same scope
- Restrictions:
    - Rule 1: Value must begin with a letter (a-zA-Z)
    - Rule 2: Shall contain the following characters only: A to Z, a to z, 0 to 9, and _ (underscore)
    - Rule 3: Spaces and symbols are not allowed
- Ex: "symbolicName": "EmailAddress"

**scope** (String)
- Mandatory
- name of the ObjectTypeLibrary the current objectType belongs to
- Ex: "scope": "sample"

**description** (String)
- Optional
- Description for the type
- Ex: "description": "This is an email address",

**extractor** (JSON Object)
- Optional
- contains an "implementationList" which is array of pattern(regular expression) implementations

**validator** (JSON Object)
- Optional
- contains an "implementationList" which is array of pattern(regular expression) and/or dictionary implementations


<br>

>implementationList JSON fields

**implementationList** (JSON Array)
- Array of implementations


<br>

>implementation JSON fields

**name** (String)
- Mandatory
- Identifies the display name of the implementation
- Ex: "name": "Email Address Regex Validator"

**symbolicName** (String)
- Mandatory
- Immutable name for the implementation
- Once created, it can't be edited again by the user
- Unique across all implementation inside the same scope
- Restrictions:
    - Rule 1: Value must begin with a letter (a-zA-Z)
    - Rule 2: Shall contain the following characters only: A to Z, a to z, 0 to 9, and _ (underscore)
    - Rule 3: Spaces and symbols are not allowed
- Ex: "symbolicName": "emailRegexValidator"

**description** (String)
- Optional
- Description for the implementation
- Ex: "description": "Regex to validate the value for an email"

**namespace** (String)
- Mandatory
- For an extractor, the value should be "valueExtractor"
- For a validator, the value should be "validator"
- Ex: "namespace": "valueExtractor" (OR) "namespace": "validator"

**extractionTool** (String)
- Mandatory
- For a pattern (regular expression) implementation, the value should be "regex"
- For a dictionary implementation, the value should be "dict"
- Ex: "extractionTool": "regex" (OR) "extractionTool": "dict"

**pattern** (String)
- Mandatory and valid only for pattern (regular expression) implementation
- Ex: "pattern": "[a-zA-Z]+@[a-zA-Z]+.com"

**wordList** (JSON Array)
- Mandatory and valid only for dictionary implementation
- Array of words
- Ex: 
```
"wordList": [
                "test@gmail.com",
                "build@gmail.com",
                "admin@gmail.com"
                ]
```
