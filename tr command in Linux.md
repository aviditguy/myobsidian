`tr` command in Linux is a text-processing utility used to translate, delete or squeeze characters from stdin and write result to stdout.
```bash
tr [OPTIONS] SET1 [SET2]
```
- **SET1**: Specifies the set of characters to be replaced or manipulated
- **SET2**: Specifies the set of characters to replace SET1 characters.
### Options and Their Descriptions

| Options | Description                                         |
| ------- | --------------------------------------------------- |
| `-c`    | Complement the set of characters in SET1            |
| `-d`    | Delete characters in SET1                           |
| `-s`    | Squeeze repeated characters into a single character |
| `-t`    | Truncate SET1 to the length of SET2                 |
#### Special Characters in SET1 and SET2
- **Ranges**: `a-z` matches all lowercase letters.
- **Classes**: `[:digit:]`, `[:lower:]`, `[:upper:]`, `[:alnum:]`, etc.
### Common Usage and Examples:
#### 1. Convert lowercase to uppercase and remove digits
```run-bash
echo 'Hello World 123' | tr 'a-z' 'A-Z' | tr -d '0-9'
```
#### 2. Remove all the whitespace
```run-bash
echo 'Hell   o   Wor ld' | tr -s ' ' | tr -d ' '
```
#### 3. Remove all non alphanumeric characters
```run-bash
echo 'user_123@linux!' | tr -cd '[:alnum:]'
```
#### 4. ROT13 cipher
```run-bash
echo 'hello world' | tr 'a-z' 'n-za-m'
```
#### 5. Decrypt ROT13 cipher
```run-bash
echo 'uryyb jbeyq' | tr 'n-za-m' 'a-z'
```