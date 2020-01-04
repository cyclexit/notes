# C++ Note

## Index
* [Container](#Container)
  * [priority_queue](#priority_queue)
  * [tuple](#tuple)
* [Function](#Function)
  * [Randomization](#Randomization)
  * [String casting](#String-casting)

## Container

### priority_queue
header file: `<queue>` <br>
class template: `template <class T, class Container = vector<T>, class Compare = less<typename Container::value_type> > class priority_queue;` <br>
***
The type `T` should be comparable. <br>
1. `priority_queue<int> pq` <br>
  In this situation, `pq` is a `max heap`. That is to say that the top element of `pq` is always the biggest element. <br>
  Why? According to the class template above, we know that `less<T>` is the default comparator. When it does the down-heap operation, we swap the current element with its smaller child(if exists) when the current element is `less` than its smaller child.
2. `priority_queue<int, vector<int>, greater<int>> pq` <br>
  In this situation, we use the `greater<T>` as the comparator, so now `pq` is a `min heap`.
3. A priority queue with a customized class
  ```cpp
  class Edge {
    int u, v, w;
    
    Edge() = default;
    Edge(int _u, int _v, int _w) : u(_u), v(_v), w(_w) {}

    inline bool operator<(const Edge& other) const {
      return w < other.w;
    }
  };

  priority_queue<Edge> pq;
  ```
  If we want to create a priority queue with a customized class. The class needs to override the `<` operator. <br>
  In this example, the top element of `pq` is an `Edge` object with the max `w` value. If you change `w < other.w` to `w > other.w`, then the top element of `pq` is an `Edge` object with the min `w` value.

### tuple
header file: <tuple>
class template: `template <class... Types> class tuple;`
***
A tuple can have many elements with different types.
1. Create a tuple
```cpp
tuple<int, char> foo(10, 'x');
tuple<int, char> bar = make_tuple(10, 'x');
```
2. Access and modify elements in a tuple
```cpp
#include <tuple>
#include <iostream>

using namespace std;

int main() {
  tuple<int, char> foo(10, 'x');
  cout << get<0>(foo) << " ";
  get<0>(foo) = 20;
  cout << get<0>(foo) << '\n';
  return 0;
}
// Output: 10 20
```

## Function

### Randomization
header file: `<random>` <br>
***
This method can only generate random integers inside `int` range.
```cpp
srand((unsigned)time(NULL));
rand() % (b - a) + a; // Generate the integers between [a,b)
rand() % (b - a + 1) + a; // Generate the integers between [a, b]
rand() % (b - a) + a + 1; // Generate the integers between (a, b]
```

### String casting
* int -> string 
  ```cpp 
  int x = 0;
  to_string(x);
  ```
  string -> int
  ```cpp
  string s = "0";
  stoi(s);
  ```
* double -> string
  ```cpp
  double x = 0.0;
  to_string(x);
  ```
  string -> double
  ```cpp
  string s = "0.0"
  stod(s);
  ```