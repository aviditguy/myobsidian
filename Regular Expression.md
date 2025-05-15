Powerful tool for text manipulation (search and replace)
### 1. Matching Single Character
dot **`(.)`** matches any single character

----
### 2. Character Sets
**`[ns]`** matches either `'n'` or `'s'`.
**`[a-zA-Z0-9_]`** matches any character only 1 from character set.

**Negate Set**: **`[^0-9]`** matches anything that is not a digit.

#### Special Classes

| Class    | Meaning      |     | Class    | Meaning        |
| -------- | ------------ | --- | -------- | -------------- |
| **`\d`** | [0-9]        |     | **`\D`** | [\^0-9]        |
| **`\w`** | [a-zA-Z0-9_] |     | **`\W`** | [\^a-zA-Z0-9_] |
| **`\s`** | [\t\n\r\f\v] |     | **`\S`** | [\^\t\n\r\f\v] |
**`\s`** matches any whitespace character.
**`\S`** matches ant non-whitespace character.

#### Posix Character Classes

| POSIX Class     | Meaning      |     | POSIX Class      | Meaning     |
| --------------- | ------------ | --- | ---------------- | ----------- |
| **`[:lower:]`** | [a-z]        |     | **`[:upper:]`**  | [A-Z]       |
| **`[:word:]`**  | [a-zA-Z0-9_] |     | **`[:xdigit:]`** | [a-fA-F0-9] |
| **`[:alpha:]`** | [a-zA-Z]     |     | **`[:alnum:]`**  | [a-zA-Z0-9] |
| **`[:digit:]`** | [0-9]        |     | **`[:space:]`**  | whitespace  |
There are more ....
To use them do like : **`[[:digit:]]`** in 2 square bracket.

----
### 3. Repeating Matches

| Pattern     | Meaning                                     |
| ----------- | ------------------------------------------- |
| **`*`**     | 0 or more matches                           |
| **`+`**     | 1 or more matches                           |
| **`?`**     | 0 or 1 match                                |
| **`{n}`**   | exactly `n` matches                         |
| **`{n,m}`** | min `n` and max `m` matches                 |
| **`{n,}`**  | atleast `n` matches, min `n` max `infinite` |
| **`{,m}`**  | atmost `m` matches, min `0` max `m`         |
##### Greedy Matches
`*`, `+`, `{n,m}` and `{n,}` are greedy by default i.e. they look for the longest possible match.

```run-bash
echo "<b>bold</b> and <b>strong</b>" | grep -Po '<b>.*</b>'
```
##### Lazy Matches
`*?`, `+?`, `{n,m}?` and `{n,}?` are lazy equivalent they looks for the shortest possible match.

```run-bash
echo "<b>bold</b> and <b>strong</b>" | grep -Po '<b>.*?</b>'
```

----
### 4. Word Boundary
* **`\b`** matches word boundary position between **`\w - \W`**
* **`\B`** matches non-word boundary between **`\w - \w`** and **`\W - \W`**

----
### 5. String Boundary
* **`^`** matches start of string
* **`$`** matches end of string

```run-bash
echo -e "hello my world\nhello sam" | grep -P '^hello .*? world$'
```

----
### 6. Subexpressions
Grouping together expression.
Lets say we want to match `HelloHello` 2 occurrences of `Hello`
* If we do **`Hello{2}`** this will look for `Helloo`.      ❌
* Correct way to do this is **`(Hello){2}`**.                ✅

```run-bash
echo -e "Hello\nHelloo\nHelloHello" | grep -P '(Hello){2}'
```

----
### 7. Alteration
Alteration (`|`) means "match this OR that". It applies to the **entire expression on either side, unless limited by parenthesis**.
* ***`I like cat | dog`** it matches either `"I like cat"` or `"dog"`
* not what we want so better way to do would be -
* **`I like (cat | dog)`** it matches `"I like cat"` or `"I like dog"`.

```run-bash
echo -e "I like cat\nI like dog\nI like bird" | grep -P 'I like (cat|dog)'
```

----
### 8. Backreferences
These refer back to previous subexpressions. Note **subexpression** they only work with subexpressions.
Let's say we have this **`<h2>Incorrect Heading Tag in HTML</h3>`**
we want to only match correct heading tag in HTML.
**`<(h[1-6])>.*?<\/\1>`**

Here **`\1`** refers to first subexpression, **`\2`** to second **`\3`** and so on ...

```run-bash
echo -e "<h1>Correct</h1>\n<h2>Incorrect</h3" | grep -P '<(h[1-6])>.*?<\/\1>'
```

----
### 9. Lookaround
#### Lookahead (?=pattern) and Lookbehind (?<=pattern)
**Lookahead**  Returns matched text only if pattern exists ahead of it.
**Lookbehind** Returns matched text only if pattern exists before it.

It uses **pattern** only as position marker and do not return with result.
##### Example
In HTML we have **`<title>Shitty Page Title</title>`** i just want to get page's title content.
➤  **`(?<=<title>).*?(?=<\/title>)`**

```run-bash
echo "<title>Shitty Page Title</title>" | grep -Po '(?<=<title>).*?(?=<\/title>)'
```

#### <u>Positive Lookaround</u>
Match text to specify location of text to be returned.
#### <u>Negative Lookaround</u>
Looks ahead and behind for text that does not match specified pattern.
* **Negative Lookahead** **`(?!pattern)`**
* **Negative Lookbehind** **`(?<!pattern)`**

##### Example
**`We only paid ₹30 for 100 apples`** match only apple quantity not the price.
➤  **`\b(?<!₹)\d+`**

```run-bash
echo "We only paid ₹30 for 100 apples" | grep -Po '\b(?<!₹)\d+'
```

----
### 10. Conditional Matching
#### Conditional Processing based on Backreferences
**`(?(backreference)true|false)`**
##### Example
Match `img` tag and if its inside `a` tag then also match the `a` tag.

```run-bash
echo -e '
<a href="/home"><img src="img.png"></a>\n
<img src="home.png">' | grep -P '((<a.*?>)?<img.*?>(?(1)<\/a>))'
```

Breakdown of expression:
* **`(<a.*?>)?`** checks if opening `a` tag exists or not we put this in subexpression
* **`(?(1)<\/a>)`** here the conditional processing is working
* we check if **`?(1)`** exists if subexpression **`\1`** exists then match closing `a` tag.
#### Lookaround Conditioning
Its based on whether a lookaround condition succeeds or not.
**`(?(lookaround)true|false)`**

##### Example
Match valid zip codes, which are `11111`, `44444-4444`.

```run-bash
echo -e '
11111\n
33333-\n
44444-4444' | grep -P '\d{5}(?(?=-)-\d{4})'
```

Breakdown of expression:
* **`\d{5}`** matches 5 digit
* **`(?=-)`** looks ahead for `-`
* **`(?(?=-)-\d{4})`** if `-` occurs after `\d{5}` then loo for `-\d{4}`
