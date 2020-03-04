# Go Note

## Index
* [Syntax](#Syntax)
  * [Slice](#Slice)
* [Code snippet](#Code-snippet)
  * [Read files](#Read-files)
  * [Get command-line arguments](#Get-command-line-arguments)
* [Other](#Other)
  * [build vs install](#build-vs-install)
  * [Visual Studio Code](Visual-Studio-Code)

## Syntax
### Slice
1. Create slice </br>
    Take examples of `int`.
    ```go 
    slice := []int{...}
    ```
    ```go
    slice := make([]int, len, cap)
    ``` 
    ```go
    slice := arr[i:j] // arr is an array, and slice contains elements from arr[i] to arr[j - 1]
    ```
2. append function
    ```go
    func append(slice []Type, elems ...Type) []Type
    ```
    If len(slice) < cap(slice), `append` just add the new element to the slice and make len(slice) increase 1. </br>
    If len(slice) == cap(slice), `append` will create a new slice with bigger capacity, and copy the elements from the old slice.
3. Passed as an argument </br>
When passing a slice as an argument, *Go* actually just passes the pointer of the slice. </br>
In the function which is called, *Go* creates a new pointer by copying the address of the slice. </br> 
If the second situation of the append function happens, the result of the append function will not appear in the calling function. 

## Code snippet
### Read files
```go
file, err := os.Open("example.txt")
defer file.Close()
if err != nil {
  panic(err)
}
scanner := bufio.NewScanner(file)
for scanner.Scan() {
  info := scanner.Text()
}
if scanner.Err() != nil {
  panic(scanner.Err())
}
```
### Get command-line arguments
`import "os"` </br>
`os.Args[0]` is the path of the executable file.</br>
`os.Args[1]` is the first argument you add in the command line.

## Other
### build vs install
Go `build` just compile the executable file and move it to destination.</br>
</br>
Go `install` do a little more. It move the executable file to `$GOPATH/bin` and cache all non-main packages which imported to `$GOPATH/pkg`. the cache will be use in the next compile if it not changed yet.

### Visual Studio Code
In `setting.json`, set the `go.gopath`.