# Some bash commands I've found useful

## Looking recursively in current directory for files with certain words
#### Cleaning node modules
###### List all unique x's where x is in require('x'), capturing x
`grep -r --exclude-dir=./node_modules require\(\'[^\.] . | sed -E "s/.*require\('(.+)'\).*/\1/" | sort | uniq`

###### same for import x from y, capture y's:
`grep -r --exclude-dir=./node_modules "^import.*from\s\'[^\.\/]" . | sed -E "s/.*from '(.+)'.*/\1/" | sort | uniq`
