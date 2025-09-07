# Question 3: Conceptual Understanding

## 3.1 Token vs Non-terminal

In the rule `<stmt> ::= IF <expr> THEN <stmt>`, explain the difference between:

- Items in angle brackets (like `<expr>`)
- Items in all caps (like `IF`, `THEN`)

**Your answer:** [write your answer here]

## 3.2 Skip vs Token

What's the practical difference between these two lexical rules?

```
skip SPACE '\s+'
token SPACE '\s+'
```

**Your answer:** [write your answer here]

## 3.3 Pattern Precedence

If you have these two token definitions:

```
token IF 'if'
token ID '[a-zA-Z]+'
```

What token will the scanner produce for the input "if"? Why?

**Your answer:** [write your answer here]
