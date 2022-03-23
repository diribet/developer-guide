
## Formatting

### Code Indentation
Always use 4 spaces for indentation of code blocks.

### Spaces Around Operators
Always put spaces around operators ( = + - * / ), and after commas:

```js
let x = y + z;
const myArray = ["Volvo", "Saab", "Fiat"];
```

### Semicolons
Always end a simple statement with a semicolon.

### One statement per line
Each statement is followed by a line-break.

### Braces
Braces are required for all control structures (i.e. if, else, for, do, while, as well as any others), even if 
the body contains only a single statement. The first statement of a non-empty block must begin on its own line.

### Array and Object literals: optionally block-like
Any array or object literal may optionally be formatted as if it were a “block-like construct”.

```js
const a = [
    0,
    1,
    2,
];

const b = [0, 1, 2];

const c = {
    a: 0,
    b: 1,
};

const d = {a: 0, b: 1};
```

## Naming

Variable, parameter and function names written as camelCase

Constants and [Enum](#enum) properties written in UPPERCASE

Class names and Enum names written in PascalCase

## Language features

### Use const and let
Declare all local variables with either const or let. Use const by default, unless a variable needs to be reassigned. 
The var keyword must not be used.

### One variable per declaration
Every local variable declaration declares only one variable: declarations such as `let a = 1, b = 2;` are not used.

### Enum
JavaScript doesn't have Enum construct. We use frozen object with string properties as a replacement. 
Usually, when we send data from server to client, enum values are encoded as strings. These strings can be 
compared to the Enum property values.

```js
const ParserType = Object.freeze({
    SCRIPTED: "scripted",
    CSV: "csv",
    JSON: "json-simple"
});

if (parser.type === ParserType.JSON) {
	
}
```