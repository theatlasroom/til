# Parse arguments in bash script
Arguments can be passed to a bash script either positionally or with flags.

## Positional arguments
Arguments are stored in an 0 based array and can be read via index prepended with a `$`.

Argument `$0` is the name of the script

Using the `$@` symbol, we can iterate over the arguments
```
#!/bin/bash

# store the first argument in variable a
a=$1
# store the second argument in variable b
b=$2

# print a response
echo "Ryu's signature move is the $a$b"

for ARG in "$@"
do
echo "parsed: $ARG"
done
```

Then call the script with 2 parameters
```
$ sh ./cool-script.sh 'hadou' 'ken'
```

## Flags
Flags are key / value pairs passed along to the script
```
#!/bin/bash
move=''

while getopts 'm:v' flag; do
  case "${flag}" in
    m) move="${OPTARG}" ;;
    *) error "Unexpected option ${flag}" ;;
  esac

  echo "Ryu's signature move is the $move"
done
```

Then call the script as so
```
$ sh ./cool-script.sh -m 'hadouken'
```

## Links
* [getopts tutorial](http://wiki.bash-hackers.org/howto/getopts_tutorial)
* [How to pass arguments to a bash script](https://www.lifewire.com/pass-arguments-to-bash-script-2200571)
