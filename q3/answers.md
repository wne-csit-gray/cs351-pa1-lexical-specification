# Question 3: Conceptual Understanding

## 3.1 Token vs Non-terminal

In the rule `<stmt> ::= IF <expr> THEN <stmt>`, explain the difference between:

- Items in angle brackets (like `<expr>`)
- Items in all caps (like `IF`, `THEN`)

**Your answer:** Items in angle brackets (`<expr>`, `<stmt>`) are non-terminals - they represent grammatical structures that must be further expanded by other rules. Items in all caps (`IF`, `THEN`) are terminals/tokens - they are actual keywords that appear literally in the input and cannot be further expanded.

## 3.2 Skip vs Token

What's the practical difference between these two lexical rules?

```
skip SPACE '\s+'
token SPACE '\s+'
```

**Your answer:** `skip SPACE` tells the scanner to recognize whitespace but ignore it completely - it won't create any tokens. `token SPACE` tells the scanner to recognize whitespace and create SPACE tokens that get passed to the parser. Using `skip` for whitespace is typical since you usually don't want spaces to affect parsing.

## 3.3 Pattern Precedence

If you have these two token definitions:

```
token IF 'if'
token ID '[a-zA-Z]+'
```

What token will the scanner produce for the input "if"? Why?

**Your answer:** The scanner will produce an IF token. PLCC uses a "first longest match" algorithm - when multiple patterns can match the same input, the first pattern defined in the grammar file wins. Since `token IF 'if'` appears before `token ID '[a-zA-Z]+'`, the IF token takes precedence even though "if" would also match the ID pattern.
