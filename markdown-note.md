# Markdown Note

## Index
* [Anchor](#Anchor)
* [Font style](#Font-Style)
* [List](#List)
  * [Bullet](#Bullet)
    * [Single layer](#Single-layer)
    * [Multiple layer](#Multiple-layer)
* [Table](#Table)
* [Block](#Block)

## Achor
|Grammar|Effect
|-------|------
|`[Back to the top](#Markdown-Note)`|[Back to the top](#Markdown-Note)

## Font Style
|Grammar|Effect
|-------|------
|\*italic\*|*italic*
|\*\*bold\*\*|**bold**
|\~\~strike\~\~|~~strike~~
|\`highlight\`|`hightlight`

## List
### Bullet
#### Single layer
Grammar
```
* item1
* item2
```
Effect
* item1
* item2
#### Multiple layer
Just use the indentation to seperate different layers. <br>
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