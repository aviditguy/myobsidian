`grep` is a command line utility used to search for text patterns within files.
- by default it prints matching lines.
- it's only used for searching patterns not edit files.

always use Perl Compatible Regex Option `-P`, better put this in your `~/.bashrc`:
```bash
alias grep='grep -P --color=auto'
```
## Basic Usage
```bash
grep [OPTIONS] PATTERN [FILE....]
```
- **PATTERN**: The text or regular expression to search for.
- **FILE**: The file(s) to search in. If omitted, `grep` reads from standard input.
## Common Useful Options that i use mostly:

| Option | Description                                                |
| ------ | ---------------------------------------------------------- |
| `-P`   | Use Perl-compatible regex (PCRE) - powerful regex engine   |
| `-o`   | Print only the matched portion (great for extracting data) |
| `-i`   | Ignore case                                                |
| `-v`   | Invert match (show lines that don't match)                 |
| `-n`   | Show line numbers where matches occur                      |
| `-r`   | Recursive search through directories                       |
| `-H`   | Always print the filename(useful in recursive search)      |
### Common Examples:
#### 1. `-P -o` – extract emails from a string
```run-bash
echo 'contact: user@email.com ot admin@site.org' | grep -Po '[\w._]+@[\w._]+'
```
#### 2. `-P -i -o` – case insensitive word extract
```run-bash
echo "The Quick brown fox" | grep -Pio "quick"
```
#### 3. `-P -v` – invert: exclude lines with digits
```run-bash
echo -e "apple\nbanana42\ncherry" | grep -Pv "\d"
```
#### 4. `-P -n` – show line numbers where match occurs
```run-bash
echo -e "cat\nbat\nrat" | grep -Pn "b.t"
```
