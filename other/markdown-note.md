# Markdown Note

## Index
* [Anchor](#anchor)
* [Title](#title)
* [Font style](#font-style)
* [Dividing line](#dividing-line)
* [List](#list)
  * [Single layer bullet list](#single-layer-bullet-list)
  * [Multi-layer bullet list](#multi-layer-bullet-list)
  * [Single layer number list](#single-layer-number-list)
  * [Multi-layer number list](#multi-layer-number-list)
* [Table](#table)
* [Block](#block)
* [Picture](#picture)

## Anchor
|Grammar|Effect
|-------|------
|`[Back to the top](#Markdown-Note)`|[Back to the top](#Markdown-Note)

## Hyperlink
|Grammar|Effect
|-------|------
|`[GitHub](https://github.com)`|[GitHub](https://github.com)

## Title
Use `#`. You can use up to 6 `#` to get 6-level titles.

## Font style
|Grammar|Effect
|-------|------
|\*italic\*|*italic*
|\*\*bold\*\*|**bold**
|\~\~strike\~\~|~~strike~~
|\`highlight\`|`hightlight`
|H\<sub\>2\<\/sub\>O|H<sub>2</sub>O
|2\<sup\>18\<\/sup\>|2<sup>18</sup>

## Dividing line
Use `***` or `___`. </br>
`<hr>` also works.

## List
### Single layer bullet list
**Grammar**
```
* item1
* item2
```
**Effect**
* item1
* item2
### Multi-layer bullet list
Just use the indentation to seperate different layers. </br>

**Grammar**
```
* item1
    * item1_1
* item2
    * item2_1
```
**Effect**
* item1
    * item1_1
* item2
    * item2_1
### Single layer number list
Just type `1. ` which is a number, a dot and a space right after the dot. </br>

**Grammar**
```
1. item1
2. item2
```
**Effect**
1. item1
2. item2
### Multi-layer number list
The same as the bullet list, just use the indentation. </br>

**Grammar**
```
1. item1
    1. item1_1
        1. item1_1_1
2. item2
    1. item2_1
        1. item2_1_1
```
**Effect**
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

Make sure that the line before the first line of the list is empty. Otherwise, you can not get a list on GitHub.

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

## Picture
|Grammar|Effect
|-------|------
|`![GitHub](https://github.com/fluidicon.png)`|![GitHub](https://github.com/fluidicon.png) 

Inside the parenthesis, you can also put a repo directory as well as a link.