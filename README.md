# CS351 - Lexical Specification

**Due Date:** Sep 15 by 11:59 PM

## Overview

This assignment focuses on lexical specification in PLCC. You will:

1. Skip patterns (whitespace, comments)
2. Token definitions
3. Regular expressions in PLCC
4. Lexical error handling


By completing this assignment, you'll gain hands-on experience with the first phase of language implementation: tokenization and lexical analysis.

---

## QUESTION 1: Token Recognition and Classification

In the `q1/` directory, you'll find these starter files:

- `grammar` - An empty file for your lexical specification
- `input` - Sample input to test your scanner (do not modify)
- `expected` - Expected scanner output (do not modify)

**Task:** Write a lexical specification in the `grammar` file that:

1. **Skips** whitespace characters
2. **Skips** comments from '#' to end of line
3. **Recognizes** these specific keyword tokens:
   - `this` → THIS token
   - `that` → THAT token
   - `the` → THE token
   - `other` → OTHER token
   - `thing` → THING token
4. **Captures** all other alphanumeric identifiers (letters, digits, underscores) as ID tokens
5. **Reports** errors for any other characters

The `input` file contains:

```
# example input
this that # the other thing
otherwise the thing
that is another thing
other#other#other#other
thisthat the end99 12345xxx _!
```

Your scanner should produce the output shown in `expected`.

**Development Steps:**

```bash
cd q1
plccmk -c grammar    # Compile your grammar
scan < input         # Test the scanner
# Compare output with expected file
```

**Hints:**

- Use a skip rule to ignore whitespace
- Comments can be matched with a pattern from '#' to line end
- Specific tokens should be matched before the general ID pattern
- The ID pattern should match letters, digits, and underscores

---

## QUESTION 2: Meta-Lexical Specification

In `q2/`, create a lexical specification that can tokenize PLCC's own lexical specification language.

**Task:** Your scanner should recognize:

- Keywords: `skip`, `token`
- Token names (all uppercase letters/digits/underscores): NAME
- Patterns (quoted strings): PATTERN
- Comments (# to end of line): skip

**Test Input (`q2/input`):**

```
token HI 'hi'
skip BYE 'bye'
# comments are ignored
WORD '[a-zA-Z]+'
skip WS '\s+'
```

This is "going meta" - you're building a scanner that could scan PLCC grammar files!

---

## QUESTION 3: Conceptual Understanding

Complete the conceptual questions about PLCC grammar rules in the file `q3/answers.md`.

**Instructions:**
- Open `q3/answers.md` to find the questions
- Write your answers directly in that file
- Keep the question text intact - only replace `[write your answer here]` placeholders

---

## Submission Requirements

Your repository should contain:

```
q1/
├── grammar        # Your lexical specification
├── input         # (provided - do not modify)
└── expected      # (provided - do not modify)

q2/
├── grammar        # Your meta-lexical specification
└── input         # (provided - do not modify)

q3/
└── answers.md    # Your conceptual answers
```

**To Submit:**

1. Complete all questions in their respective directories
2. Test your scanners to ensure they work correctly
3. From inside your container: `tar -czf /workspace/pa1-YOURNAME.zip /workspace` From outside your container, right click on the assignment folder and compress.
4. Download and submit the zip file to Kodiak

**Grading Criteria:**

- **Submission (33.3%):** Files are properly named and located as specified
- **Completeness (33.3%):** All questions attempted (incomplete = incorrect)
- **Correctness (33.3%):** Solutions demonstrate understanding of lexical specification

**Late Policy:** 10% per day, maximum 5 days late

---

## Getting Help

- **Office Hours:** Wednesday 12:30-1:30 PM (Herman 207), Tuesday 12:30-1:30 PM (Herman 207)
- **Discord:** Post questions in #help channel
- **Email:** declan.gray-mullen@wne.edu for private concerns

**Resources:**

- PLCC Reference Manual (Slides 1a)
- Lecture slides on Tokens and Lexical Analysis (Slides 0)

---

_Course content developed by Declan Gray-Mullen for WNEU with Claude_
