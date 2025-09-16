# Question 3: Conceptual Understanding

## 3.1 Token vs Non-terminal

In the rule `<stmt> ::= IF <expr> THEN <stmt>`, explain the difference between:

- Items in angle brackets (like `<expr>`)
- Items in all caps (like `IF`, `THEN`)

Items in angle brackets like  are non-terminals representing grammar rules to be expanded in parsing.
Items in all caps are tokens recognized by the lexer.

## 3.2 Skip vs Token

What's the practical difference between these two lexical rules?

```
skip SPACE '\s+'
token SPACE '\s+'
```

Skip Space tells the lexer to ignore whitespace.
token Space would create token instances for whitespace.

## 3.3 Pattern Precedence

If you have these two token definitions:

```
token IF 'if'
token ID '[a-zA-Z]+'
```

What token will the scanner produce for the input "if"? Why?

The scanner will produce the IF token for input "if" because token patterns are matched in order, and keywords like IF have priority.
