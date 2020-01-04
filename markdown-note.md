# Markdown Note

## Index
* [Anchor](#Anchor)
* [Title](#Title)
* [Font style](#Font-style)
* [Dividing line](#Dividing-line)
* [List](#List)
  * [Single layer bullet list](#Single-layer-bullet-list)
  * [Multi-layer bullet list](#Multi-layer-bullet-list)
  * [Single layer number list](#Single-layer-number-list)
  * [Multi-layer number list](#Multi-layer-number-list)
* [Table](#Table)
* [Block](#Block)

## Anchor
|Grammar|Effect
|-------|------
|`[Back to the top](#Markdown-Note)`|[Back to the top](#Markdown-Note)

## Title
Use `#`. You can use up to 6 `#` to get 6-level titles.

## Font style
|Grammar|Effect
|-------|------
|\*italic\*|*italic*
|\*\*bold\*\*|**bold**
|\~\~strike\~\~|~~strike~~
|\`highlight\`|`hightlight`

## Dividing line
Use `***` or `___`.

## List
### Single layer bullet list
Grammar
```
* item1
* item2
```
Effect
* item1
* item2
### Multi-layer bullet list
Just use the indentation to seperate different layers.
******************************************************
Grammar
```
* item1
    * item1_1
* item2
    * item2_1
```
Effect
* item1
    * item1_1
* item2
    * item2_1
### Single layer number list
Just type `1. ` which is a number, a dot and a space right after the dot.
*************************************************************************
Grammar
```
1. item1
2. item2
```
Effect
1. item1
2. item2
### Multi-layer number list
The same as the bullet list, just use the indentation.
******************************************************
Grammar
```
1. item1
    1. item1_1
        1. item1_1_1
2. item2
    1. item2_1
        1. item2_1_1
```
Effect
1. item1
    1. item1_1
        1. item1_1_1
2. item2
    1. item2_1
        1. item2_1_1

## Table
Grammar
```
|Number|Item
|------|----
|1|item1
|2|item2
```
Effect
|Number|Item
|------|----
|1|item1
|2|item2

## Block
Use a pair of ` ``` `. <br>
You can specify the language after the first ` ``` `. For emxample: <br>
`cpp`
```cpp
#include <iostream>

using namespace std;

int main() {
  cout << "Hello world!" << '\n';
  return 0;
}
```
`java`
``` java
public class HelloWorld {
  public static void main(String[] args) {
    System.out.println("Hello world!");
  }
}
```