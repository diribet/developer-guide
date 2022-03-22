# General rules applied to all languages

**Optimize for the reader, not the writer**

Our codebase is expected to continue for quite some time. 
As a result, more time will be spent reading most of our code than writing it. 
We explicitly choose to optimize for the experience of our software engineer reading, maintaining, and debugging code 
in our codebase rather than ease when writing said code. 

"Leave a trace for the reader" is a particularly common sub-point of this principle: 
When something surprising or unusual is happening in a snippet of code, leaving textual hints for the reader 
at the point of use is valuable. These hints don't need to be in form of comments, proper function name can do the same.

Avoid surprising or dangerous constructs.

Avoid constructs that an average programmer would not understand at first glance.

As always, common sense should prevail. The goal is consistent and readable code, our rules are not a dogma.

## Formatting

Coding style and formatting are pretty arbitrary, but a project is much easier to follow if everyone uses the same style. 
Individuals may not agree with every aspect of the formatting rules, and some of the rules may take some 
getting used to, but it is important that all project contributors follow the style rules so that they can 
all read and understand everyone's code easily.

To help you format code correctly, we've created a `.editorconfig` file with settings for auto-formatter. 

### Line length

Each line of text in your code should be at most 120 characters long.

### Encoding

All files should have UTF-8 encoding.

### Whitespace

Never put trailing whitespace at the end of a line.

Use of horizontal whitespace depends on location and should be used to separate logical blocks of code.
Always think about readability.

### Variables

Place a function's variables in the narrowest scope possible, and initialize variables in the declaration.

```java
int count;
count = countItems(); // Bad -- initialization separate from declaration.
```

```java
int count = countItems(); // Good -- declaration has initialization.
```

## Naming

The most important consistency rules are those that govern naming.
The pattern-matching engine in our brains relies a great deal on these naming rules.

Naming rules are pretty arbitrary, but we feel that consistency is more important than individual 
preferences in this area, so regardless of whether you find them sensible or not, the rules are the rules.

Here are the general naming rules that apply to all languages. 
In addition, each language has its own set of naming rules described in language-specific guides.  

### General naming rules

**Optimize for readability** using names that would be clear even to people on a different team.

Use names that describe the purpose or intent of the object.
Do not worry about saving horizontal space as it is far more important to make your code immediately 
understandable by a new reader. 
Minimize the use of abbreviations that would likely be unknown to someone outside your project 
(especially acronyms and initialisms). 
Do not abbreviate by deleting letters within a word. 
As a rule of thumb, an abbreviation is probably OK if it's listed in Wikipedia.
Note that certain universally-known abbreviations are OK, such as `i` for an iteration variable.

### Language

The code should be written in the English language. 

Some legacy parts of the codebase are written in the Czech language. 
These parts of the code should be rewritten in English when we will touch them. 
The code should continuously evolve to be entirely written in English.

### Comments

Do not state the obvious. 
In particular, don't literally describe what code does, unless the behavior is non-obvious to a reader 
who understands the language well. 
Instead, provide higher-level comments that describe why the code does what it does, or make the code self-describing.
Wrapping code in a properly named function is better than writing inline comments.


### TODO and FIXME comments

`TODO`s can be used for code that is a short-term solution or good enough but not perfect. 
Also, they can mark code that should be changed at a specific time or event (e.g. Remove this after we upgrade library xxx to version yyy.)

`FIXME`s can be used for code that should be changed / fixed as soon as possible. 
They should be used only on feature branches and resolved before merging to the `main` branch.

Both `TODO` and `FIXME` should contain the date when they were written and the name of the person who created them in this format:

```
// TODO: 2022/03/22 - vlasta: some comment
```

You can use this Live Template in JetBrains IDEs:

```
// TODO: $date$ - $user$:
```

