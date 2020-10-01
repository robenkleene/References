# Bash Equality

These are equivalent:

    [[ $x == "$y" ]]
    [[ $x = "$y" ]]
    [ "$x" == "$y" ]
    [ "$x" = "$y" ]

## String Comparison

This compares `$PWD` to a string with wildcards, this isn't comparing files, just strings:

    [[ $PWD/ = $HOME/*/* ]]

This exits `1` in `~` and `/`, but exits `0` in `~/Desktop`.