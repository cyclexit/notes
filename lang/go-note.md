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