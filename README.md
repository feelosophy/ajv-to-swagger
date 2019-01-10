# Convert form AJV to Swagger

Small module that converts from ajv schemas to Swagger doc

Api functions can throw following errors:

* `Error` for all problems

## Install

```bash
npm i -E swagger-ajv-converter
```

## Usage

```ecmascript 6
const Swagger = require('swagger-ajv-converter');

const myBaseSchema = require('./myBaseSchema.json');
const methodSchema = require('./methodSchema.json');

const name = 'My awesome module'; // module name
const swaggerData = {
  title: 'some title', // overall module title
  description: 'someDescr', // Description
}
const swaggerOptions = {
  type: 'API', //types from schema
  baseSchema: Object.assign({}, Swagger.base, myBaseSchema),
}

const swagger = new Swagger(name, swaggerData, swaggerOptions);

const methods = [
{
  path: '/one/',
  methods: {
    POST: {
      schema: methodSchema,
      swagger: {
        summary: 'Info',
        description: 'descr'
      }
    },
  },
}
]

```

## Example of AJV schema

```json
{
  "type": "object",
  "properties": {
    "body": {},
    "cookies": {},
    "query": {},
    "headers": {}
  }
}
```

## Module docs

If you update this module, please support JSDOC and run `npm run docs` - docs will be auto generated.

Do not edit `README.md` directly!



## Coverage

File        |  % Stmts | % Branch |  % Funcs |  % Lines | Uncovered Line #s |
------------|----------|----------|----------|----------|-------------------|
All files   |    97.37 |    86.11 |      100 |    97.37 |                   |
 Swagger.js |    97.37 |    86.11 |      100 |    97.37 |           174,180 |