# stl vectors

## Initialising a std::vector

- There are different ways to initialise a vector. The simplest one is as follows:

  ```cpp
  #include <iostream>
  #include <vector>
  #include <algorithm>

  int main() {
      std::vector<int> vec1{ 21, 56, 104 };
      std::cout << vec1.front() << std::endl;
      std::cout << vec1.back() << std::endl;
  }

  //21
  //104
  ```

<br>
<br>
<br>

# Useful Functions

## size(), max_size() and capacity()

- size() returns the current size of the vector.
- max_size() returns the max size that the vector can hold. (it's a really big number).
- capacity() returns the size of the vector after which it'll rellocate extra contigous memory.

  ```cpp
  #include <iostream>
  #include <vector>
  #include <algorithm>

  int main() {
      std::vector<int> vec1{ 21, 56, 104 };
      std::cout << vec1.size() << std::endl;
      std::cout << vec1.max_size() << std::endl;
      std::cout << vec1.capacity() << std::endl;
  }

  //3
  //1073741823
  //3
  ```

<br>
<br>

## push_back()

- Adds an element to the back of the vector.

  ```cpp
  #include <iostream>
  #include <vector>
  #include <algorithm>

  void print(int value) {
      std::cout << value << " ";
  }

  void display(std::vector<int> vec) {
      std::for_each(vec.begin(), vec.end(), print);		//for_each is a stl algorithm
      std::cout << std::endl;
  }

  int main() {
      std::vector<int> vec1{ 21, 56, 104 };
      vec1.push_back(1000);
      display(vec1);
  }

  //21 56 104 1000
  ```

<br>
<br>

## pop_back()

- Removes the last element from the back.

  ```cpp
  #include <iostream>
  #include <vector>
  #include <algorithm>

  void print(int value) {
      std::cout << value << " ";
  }

  void display(std::vector<int> vec) {
      std::for_each(vec.begin(), vec.end(), print);		//for_each is a stl algorithm
      std::cout << std::endl;
  }

  int main() {
      std::vector<int> vec1{ 21, 56, 104 };
      vec1.pop_back();
      display(vec1);
  }

  //21 56
  ```

<br>
<br>

## erase()

- removes elements from the vector

  ```cpp
  #include <iostream>
  #include <vector>
  #include <algorithm>

  void print(int value) {
      std::cout << value << " ";
  }

  void display(std::vector<int> vec) {
      std::for_each(vec.begin(), vec.end(), print);		//for_each is a stl algorithm
      std::cout << std::endl;
  }

  int main() {
      std::vector<int> vec1{ 1, 56, 104, 2, 3, 4, 5  };
      vec1.erase(vec1.begin() + 1, vec1.begin() + 3);		//not inclusive of the second arg
      display(vec1);
  }

  //1 2 3 4 5
  ```

<br>
<br>

## emplace_back()

<br>
<br>

## empty()

- Returns true if vector is empty else returns false.

<br>
<br>

## swap()

<br>
<br>

## begin() and end()

<br>
<br>

## insert()

    ```cpp
    #include <iostream>
    #include <vector>
    #include <algorithm>

    void display(std::vector<int> vec) {
        std::for_each(vec.begin(), vec.end(), [](int value) {std::cout << value << " "; });		//for_each is a stl algorithm
        std::cout << std::endl;
    }

    int main() {
        std::vector<int> vec1{ 1,2,3,4,5,6,7 };
        std::vector<int> vec2{ 100,200,300 };

        auto iter = std::find(vec1.begin(), vec1.end(), 5);	//finds the value 5 and returns an iterator
        if (iter != vec1.end()) {
            vec1.insert(iter, vec2.begin(), vec2.end());
        }

        display(vec1);
    }


    //1 2 3 4 100 200 300 5 6 7
    ```

<br>
<br>
