# `rg`

* `-i` & `--ignore-case`: Ignore case
* `-s` & `--case-sensitive`: Case sensitive
* `-F`: Literal (no regular expression) search
* `--null`: Use `NUL` byte terminator

## Filenames

* `-l` & `--files-with-matches`: List files with matches
* `-g` or `--glob`: Filter by filename
	* To match multiple file extensions, use a character group:
		* `rg -g '*.[hm]'`
		* `-g "*.{m,h,swift}"`
	* To do a negative glob, precede with `!`, e.g., `rg -g "\!*.html" import`
	* An example of the above techniques being combined:
		* `rg -s executable -g "\!{handlers,fixers}/*"`
* `--files`: Print each file but don't search
* `--files -g`: Search for files matching glob.

## Examples

- `rg -U --multiline-dotall "string1.*string2" -g "*.m"`
    - `-U`: Enable multiline search
    - `--multiline-dotall`: Allow `.` to match newlines

## Special Characters

### ASCII Character Classes

* `[[:alnum:]]`: Alphanumeric
* `[[:alpha:]]`: Alphabetic
* `[[:ascii:]]`: Ascii
* `[[:blank:]]`: Blank
* `[[:cntrl:]]`: Control
* `[[:digit:]]`: Digits
* `[[:graph:]]`: Graphical
* `[[:lower:]]`: Lower case
* `[[:print:]]`: Printable
* `[[:punct:]]`: Punctuation
* `[[:space:]]`: Whitespace
* `[[:upper:]]`: Upper case
* `[[:word:]]`: Word characters
* `[[:xdigit:]]`: Hex digit

### Perl Character Classes

* `\d`: Digit
* `\D`: Not digit
* `\s`: Whitespace
* `\S`: Not whitespace
* `\w`: Word character
* `\b`: Not word character
* `\W`: Not word character

### Empty Matches

* `^`: The beginning of text (or start-of-line with multi-line mode)
* `$`: The end of text (or end-of-line with multi-line mode)
* `\A`: Only the beginning of text (even with multi-line mode enabled)
* `\z`: Only the end of text (even with multi-line mode enabled)
* `\b`: A Unicode word boundary
* `\B`: Not a Unicode word boundary
