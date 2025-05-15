`grep` command in Linux is a powerful tool for searching text or patterns in files and outputs.
There are lots of options for complete usage see <u>man grep</u>.
### Basic Usage
```bash
grep [OPTIONS] PATTERN [FILE...]
```
* **`PATTERN`**: The text or regular expression to search for.
* **`FILE`**: The file(s) to search in. If omitted, `grep` reads from standard input.
### Options for Matching
##### 1. Options for Matching

| Option                       | Description                                             |
| ---------------------------- | ------------------------------------------------------- |
| **`-i`** (Ignore Case)       | Matches patterns regardless of case (case-insensitive). |
| **`-v`** (Invert Match)      | Displays lines that **do not** match the pattern.       |
| **`-w`** (Word Match)        | Matches only whole words (not substrings).              |
| **`-x`** (Exact Match)       | Matches entire lines that exactly match the pattern.    |
| **`-e`** (Multiple Patterns) | Specifies multiple patterns to match                    |
| **`-f`** (FILE)              | Reads patterns from a file, one per line.               |

----
##### 2. Output Control

| Option                           | Description                                                                  |
| -------------------------------- | ---------------------------------------------------------------------------- |
| **`-c`** (Count Matches)         | Displays the number of matching lines instead of the actual matches          |
| **`-o`** (Only Matching)         | Prints only the matched part of the lines.                                   |
| **`-q`** (Quiet Mode)            | Suppresses output and exits with a status code (0 for match, 1 for no match) |
| **`-L`** (Files Without Matches) | Lists files that **do not** contain matches.                                 |
| **`-l`** (Files With Matches)    | Lists files that contain matches.                                            |
| **`-m NUM`** (Limit Matches)     | Stops reading after finding a specified number of matches.                   |

----
##### 3. Line Numbers and Context

| Option                        | Description                                                          |
| ----------------------------- | -------------------------------------------------------------------- |
| **`-n`** (Line Numbers)       | Shows the line number of each match                                  |
| **`-H`** (Show File Name)     | Shows the file name for each match (useful for multiple files)       |
| **`-A NUM`** (After Context)  | Displays the specified number of lines **after** a match.            |
| **`-B NUM`** (Before Context) | Displays the specified number of lines **before and after** a match  |
| **`-C NUM`** (Context)        | Displays the specified number of lines **before and after** a match. |

----
##### 4. Regular Expression Options

| Option                    | Description                                                   |
| ------------------------- | ------------------------------------------------------------- |
| **`-E`** (Extended Regex) | Enables extended regular expression (ERE)                     |
| **`-F`** (Fixed String)   | Treats the pattern as fixed string, not a regular expression. |
| **`-P`** (Perl Regex)     | Enables Perl-compatible regular expressions (PCRE).           |

----
##### 5. Binary File Handling

| Option                    | Description                                    |
| ------------------------- | ---------------------------------------------- |
| **`--binary-files=TYPE`** | Specifies how to handle binary files. Options: |
|                           | - `binary`: Searches binary files (default).   |
|                           | - `text`: Treats binary files as text.         |
|                           | - `without-match`: Ignores binary files.       |
| `-I`                      | Ignores binary files automatically             |


----
##### 6. Miscellaneous Options

| Option                  | Description                                                  |
| ----------------------- | ------------------------------------------------------------ |
| **`--color=auto`**      | Highlights matching text in the output                       |
| **`--exclude=PATTERN`** | Exclude files that match the specified pattern.              |
| **`--include=PATTERN`** | Searches only in the files that match the specified pattern. |
| **`-r`**                | Searches recursively in directories                          |
| **`--exclude-dir=DIR`** | Exclude directories from recursive searches.                 |

----

```run-bash
grep -P '\bapple\b' @vault_path/Assets/fruits.md
```
