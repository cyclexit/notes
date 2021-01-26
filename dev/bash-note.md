# Bash Note

## Index
* [printf vs echo](#printf-vs-echo)
* [Redirect Output to Multiple Files](#redirect-output-to-multiple-files)
* [Variable](#variable)
* [Command-line Argument](#command-line-argument)
* [String](#String)

***

## printf vs echo
`prinf` has much more consistent behavior than `echo` since `echo` has multiple versions.

## Redirect Output to Multiple Files
Use `tee`:
```bash
printf "Hello" | tee {1..10}.txt
```

## Variable
* Create variable </br>
    ```bash
    var="variable"
    ```
* Access variable
    ```bash
    var="variable"
    echo $var
    ```

## Command-line Argument
* `$0`: Name used to invoke the script
* `$1`-`$9`: Names for each of first 9 arguments
* `$#`: The number of arguments
* `$*`: The list of args, but `"$*"` joins them together
* `$@`: The list of args, but `"$@"` acts like an array </br>
  `$@` is different from `"$@"`, and `$@` acts like `$*`.

## String
* Remove prefix and suffix
    ```bash
    string="hello-world"
    prefix="hell"
    suffix="ld"

    foo=${string#"$prefix"} # remove prefix
    foo=${foo%"suffix"} # remove suffix
    echo $foo # Output: o-wor
    ```
* Concatenation
    ```bash
    VAR1="Hello, "
    VAR2="world!"
    VAR3="$VAR1$VAR2"
    echo $VAR3 # Output: Hello, world!
    VAR4="${VAR1}, world!"
    echo $VAR4 # Output: Hello, world!
    ```