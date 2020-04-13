# C++ Note

## Index
* [Container](#container)
  * [priority_queue](#priority_queue)
  * [map](#map)
  * [tuple](#tuple)
  * [array](#array)
* [Snippet](#snippet)
  * [String casting](#string-casting)
  * [Randomization](#randomization)
  * [Overload << for a class](#overload-<<-for-a-class)
* [Other](#other)
  * [C++ pre-defined max and min value](#c++-pre-defined-max-and-min-value)
* [Memo](#memo)

*** 

## Container
### priority_queue
header file: `<queue>` <br>
class template: `template <class T, class Container = vector<T>, class Compare = less<typename Container::value_type> > class priority_queue;` <br>
***
The type `T` should be comparable. <br>
* `priority_queue<int> pq` <br>
  In this situation, `pq` is a `max heap`. That is to say that the top element of `pq` is always the biggest element. <br>
  Why? According to the class template above, we know that `less<T>` is the default comparator. When it does the down-heap operation, we swap the current element with its smaller child(if exists) when the current element is `less` than its smaller child.
* `priority_queue<int, vector<int>, greater<int>> pq` <br>
  In this situation, we use the `greater<T>` as the comparator, so now `pq` is a `min heap`.
* A priority queue with a customized class
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
### map
header file: `<map>` </br>
class template: `template<class Key, class T, class Compare = less<Key>, class Alloc = allocator<pair<const Key,T>>> class map;`
***
I often use the map to store the original indexes before sorting an array. However, when the elements in an array **may have the same value**, please **DON'T USE THIS**, since it will bring bugs which are really hard to find. In this case, just consider using `pair<...>`, `<tuple>` or `array`.
### tuple
header file: `<tuple>` `C++11`</br>
class template: `template <class... Types> class tuple;`
***
A tuple can have many elements with different types.
* Create a tuple
  ```cpp
  tuple<int, char> foo(10, 'x');
  tuple<int, char> bar = make_tuple(10, 'x');
  ```
* Access and modify elements in a tuple
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
### array
header file: `<array>` `C++11` </br>
class template: `template < class T, size_t N > class array;`
***
This can be used with `vector`. This is a better option when you want to use a tuple to store a set of values **with the same type**, since you can use the index to access each element instead of using `get<...>()` function.

## Snippet
### String casting
```cpp
// int, double to string 
to_string(x);
// string to int
stoi(s);
stod(s);
```
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
### Overload << for a class
```cpp
ostream& operator<<(ostream& out, T& t) {
  out << "\n"; // move content to out stream
}
```

## Other
### C++ pre-defined max and min value
header file: `<climits>`
***
| type | max | min
|------|-----|----
|int|INT_MAX: 32767(2<sup>15</sup> - 1)|INT_MIN:-32767(-2<sup>15</sup> + 1)
|long long|LLONG_MAX: 9.2e18(2<sup>63</sup> - 1)|LLONG_MIN: -9.2e18(-2<sup>63</sup> + 1)

## Memo
* C++ is a strongly typed, weakly checked programming language.