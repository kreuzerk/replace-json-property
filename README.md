[![code style: prettier](https://img.shields.io/badge/code_style-prettier-ff69b4.svg?style=flat-square)](https://github.com/prettier/prettier)
[![codecov](https://codecov.io/gh/kreuzerk/replace-json-property/branch/master/graph/badge.svg)](https://codecov.io/gh/kreuzerk/replace-json-property)

# replace-json-property
This module allows you to replace a specific property in a JSON.
You can use this via the following command:

```
replace-json-property pathToFile property value
```

This command replaces all occurences of the matching property. It also replaces
occurences in nested objects or objects in arrays.

The following command would replace all values of the `foo` property with 'test' inside the `test.json`.
```
replace-json-property ./test.json foo test,
```
Executing the command above on the given JSON
```
{
    foo: 'bar',
    a: {
        b: 1,
        foo: 'bar',
        c: [
            {d: 1, foo: 'bar'},
            {d: 2, foo: 'bar'},
            {d: 3, foo: 'bar'},
        ]
    }
}
```
results in:

```
{
    foo: 'test',
    a: {
        b: 1,
        foo: 'test',
        c: [
            {d: 1, foo: 'test'},
            {d: 2, foo: 'test'},
            {d: 3, foo: 'test'},
        ]
    }
}
```
## Short form
All commands explained above can also be run with the shortcut version `rjp`.
```
rjp ./test.json foo test,
```
## Help command
You can always run the help command to see how the signature looks
```
replace-json-property -h
```
or
```
replace-json-property --help
```
To get the current version use the --version or -v command.

