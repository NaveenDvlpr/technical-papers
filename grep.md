# GREP - Global Regular Expression Print

**grep** is command line utility to search text using regular expression(pattern). It ouputs the original lines showing the matches.

A utility is a small and specialized program to perform a specific task related to managing, maintaining, or optimizing the operation system.

### Syntax
```
grep [FLAGS...] PATTERNS [FILES..]

```
It is a good practice to keep the pattern in double quotes when using the grep in a shell command.

### Flags
* -i, --ignore-case: Searches the file to match the patten ignoring the case.
* -v, --invert-match: Selects the non matching lines.
* -n, --line-number: Adds a line number infront of the matching lines
* -w: find the exact matching word in the file or string
* -c: Count the number of occurence of the provided pattern

### Examples
```
# Sample.txt
Sample test for the examples:
Round and round, the wheels go round,
Down and down, without a sound.
Bright and bright, the stars all glow,
Slow and slow, the night winds blow.
```

##### Basic
```bash
grep "the" sample.txt
```
```bash
grep "low" sample.txt
```
##### Ignore-case(-i)
```bash
grep -i "bright" sample.txt
```
##### Ivert-match(-v)
```bash
grep -iv "bright" sample.txt
```
##### Line-number(-n)
```bash
grep -n "stars" sample.text
```
##### Exact-match(-w)
```bash
grep -w "a" sample.txt
```
##### Output-line count(-c)
```bash
grep -iwc "Round" sample.txt
```
##### Only-matching(-o)
This command prints all the matchings in text in seperate lines instead of regular output
```bash
grep -io "Round" sample.txt
```
##### Number of matches in a text using <span>wc</span>
```bash
grep -io "Round" sample.txt | wc -l
```

### -E Extended regular expression
-E flag helps us to include advanced regular expression like or(|), character sets and wild characters(+,*,?)
##### or(|)
```bash
grep -E "glow|blow" sample.txt
```
#### character set
```bash
grep -E "[A-Z][a-z]*" sample.txt
```
Selects words starting with a capital letter and following with zero or more small letters.

##### Ouputs image
![Outputs image](img/grep1.png)
