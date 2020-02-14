# Go Note

## Index
* [build vs install](#build-vs-install)
* [Visual Studio Code](Visual-Studio-Code)

## build vs install
Go `build` just compile the executable file and move it to destination.</br>
</br>
Go `install` do a little more. It move the executable file to `$GOPATH/bin` and cache all non-main packages which imported to `$GOPATH/pkg`. the cache will be use in the next compile if it not changed yet.

## Visual Studio Code
In `setting.json`, set the `go.gopath`.

## Read files
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

## Get command-line arguments
`os.Args[0]` is the path of the executable file.</br>
`os.Args[1]` is the first argument you add in the command line.