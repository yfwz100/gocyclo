Gocyclo calculates cyclomatic complexities of functions in Go source code.

The cyclomatic complexity of a function is calculated according to the
following rules (like [Sonar][]):

     1 is the base complexity of a function
    +1 for each 'if', 'for', 'case', '&&' or '||' inside 'if', 'for'
    +1 for nested 'if', 'for', 'case', 'func'

Note: this is the fork from [fzipp/gocyclo][] but it caculate nested 
complexity as well.

To install, run

    $ go get github.com/yfwz100/gocyclo

and put the resulting binary in one of your PATH directories if
`$GOPATH/bin` isn't already in your PATH.

Usage:

    $ gocyclo [<flag> ...] <Go file or directory> ...

Examples:

    $ gocyclo .
    $ gocyclo main.go
    $ gocyclo -top 10 src/
    $ gocyclo -over 25 docker
    $ gocyclo -avg .

The output fields for each line are:

    <complexity> <package> <function> <file:row:column>

[Sonar]: https://www.sonarqube.org/
[fzipp/gocyclo]: https://github.com/fzipp/gocyclo/
