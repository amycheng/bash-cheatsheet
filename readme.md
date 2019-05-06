# Useful BASH Snippets
Frequently Google'd bash snippets. I don't use these often enough to have them
memorized.

add `#!/bin/bash` to the top of bash scripts or else you can run them with `bash [filename].sh`

## Arrays
- see [For Loops](#for-loops)

## Conditionals
```bash
if [ ! -d "node_modules" ]; then
  echo "node_modules directory exists"
fi
```

## For Loops
```bash
array=( one two three )
for i in "${array[@]}"
do
	echo $i
done
# one
# two
# tree
```

## Variables
```bash
FOO="bar"
BAZ="${FOO}baz"

echo "${BAZ}"
# barbaz
```

- don't add spaces before/after `equal`, it will throw an error

## While loops and STDIN
```bash
 while read line
  do
    echo "${line}"
    if [[ "$line" =~ "$LINT_DIR" ]]; then
        BUILD_RULES=true
        break
    fi
  done < "${1:-/dev/stdin}"
```
- can't set `stdin` as a var!
