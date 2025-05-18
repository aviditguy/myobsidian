## echo command in Linux
`echo` is a simple command-line utility used to display lines of text or strings to the standard output.

```bash
echo [OPTIONS] [STRING...]
```
### Common Use Cases:
#### 1. Print plain text:
```run-bash
echo "Hello, World!"
```
#### 2. Enable interpretation of escape characters:
```run-bash
echo -e "Line1\nLine2"
```
#### 3. Avoid trailing newline:
```run-bash
echo -n "No newline at the end"
```
----
## printf command in Linux
`printf` is a format-controlled output command in Linux that prints formatted text like `printf()` function in C.

```bash
printf FORMAT [ARGUMENT]...
```

**Key Differences vs `echo`**
- `printf` does not automatically adds a new line
- It offers consistent behavior across different environments
- Supports formatted output (e.g., integers, strings, floats)

### Common Use Cases:
#### 1. Print a string with a newline:
```run-bash
printf "Hello, World\n"
```
#### 2. Formatted integer and string:
```run-bash
printf "User: %s, Age: %d\n" "alice" 26
```
#### 3. Print floating point with precision:
```run-bash
printf "PI: %.2f\n" 3.14159
```
#### 4. Print with padding and alignment:
```run-bash
printf "|%10s|%-10d|%010d|\n" "Score" 100 42
```
- `%10s` right align string in a field 10 characters wide
- `%-10d` left align integer in a field 10 characters wide
- `%010d` zero padded right align integer in a field 10 characters wide
#### 5. Simulating centered effect:
There is no built-in center alignment, but we can simulate -
```run-bash
printf "|%*s%*s|\n" 10 "hi" 8 ""
```
- `%*s` means print a string `s` with a field width specified at runtime `*`
- in printf format string, `*` is a placeholder for a number that you provide as an argument
- first `%*s` specified right-aligned `hi` in a width of `10` so that makes `8` spaces to the left
- second `%*s` specified `8` width and `""` string
- so `hi` is entered with before and after `8` spaces
