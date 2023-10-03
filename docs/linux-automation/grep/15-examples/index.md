---
sidebar_position: 1
---

# 15 Examples

See **article** **[15 Practical Grep Command Examples In Linux / UNIX](https://www.thegeekstuff.com/2009/03/15-practical-unix-grep-command-examples/)**.

## Commands
```bash
grep "this" demo_file
grep "this" demo_*
grep -i "the" demo_file
grep "lines.*empty" demo_file
grep -i "is" demo_file
grep -A 3 -i "example" demo_text
grep -B 2 "single WORD" demo_text
grep -C 2 "Example" demo_text

export GREP_OPTIONS='--color=auto' GREP_COLOR='100;8'
grep this demo_file

grep -r "ramesh" *
grep -v "go" demo_text
grep -v -e "a" -e "b" -e "c" test-file.txt
grep -c "go" demo_text
grep -c this demo_file
grep -v -c this demo_file
grep -l this demo_*
grep -o "is.*line" demo_file
grep -o -b "3" temp-file.txt
grep -n "go" demo_text
```