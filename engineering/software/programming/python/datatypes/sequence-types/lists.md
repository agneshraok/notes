[← Back to sequence-types](./contents.md)

# Contents

- [Lists](#lists)
  - [Creating lists](#creating-lists)
  - [Methods](#methods)
    - [Insert an element](#insert-an-element)
    - [Insert at the end](#insert-at-the-end)
    - [Extend](#extend)
    - [Access element](#access-element)
    - [Access elements](#access-elements)
    - [Delete element](#delete-element)
    - [Delete last element](#delete-last-element)
    - [Delete all elements](#delete-all-elements)
    - [Sort](#sort)
    - [Get index](#get-index)
    - [Reverse](#reverse)
    - [Get max element](#get-max-element)
  - [Unpacking list](#unpacking-list)
  - [List comphrehension](#list-comphrehension)
  - [List replication](#list-replication)

<br>
<br>
<br>



# Lists

- lists are mutable.
- lists items can be of different data types.

<br/>
<br/>
<br/>

## Creating lists

```python
myList = [1, 'all', {'a':1}, ('a','b',1)]
print(myList)

#>[1, 'all', {'a': 1}, ('a', 'b', 1)]
```

<br/>
<br/>
<br/>

## Methods

| Operation           | Method               | Example                 | Time complexity |
| ------------------- | -------------------- | ----------------------- | --------------- |
| Insert an element   | insert(index, value) | nums.insert(2,"apple")  | $O(n)$          |
| Insert at the end   | append(value)        | nums.append("banana")   | $O(1)$          |
| Extend              | extend(list)         | nums.extend([4,5,6])    | $O(k)$          |
| Access element      | [] operator          | nums[0]                 | $O(1)$          |
| Access elements     | [] opertor           | nums[1:5]               | $O(k)$          |
| Delete element      | remove(index)        | nums.remove(2)          | $O(n)$          |
|                     | del keyword          | del nums[2]             | $O(n)$          |
| Delete last element | pop()                | nums.pop()              | $O(1)$          |
| Delete all elements | clear()              | nums.clear()            | $O(n)$          |
| Sort                | sort()               | nums.sort()             | $O(n*log(n))$   |
|                     | sorted()             | new_nums = sorted(nums) | $O(n*log(n))$   |
| Get index           | index(value)         | nums.index(2)           | $O(n)$          |
| Reverse             | reverse()            | nums.reverse()          | $O(n)$          |
| Get max element     | max(list)            | max(nums)               | $O(n)$          |

<br/>
<br/>

### Insert an element

`insert()` : Inserts a given element at a given index in a list.

```python
myList = [1,2,3,4,5,6]
myList.insert(0, 'Zero')
print(myList)

#>['Zero', 1, 2, 3, 4, 5, 6]
```

<br/>
<br/>

### Insert at the end

`append()` : Insertion to the end of the list.

```python
myList = [1,2,3,4,5,6]
myList.append(7)
print(myList)

#>[1, 2, 3, 4, 5, 6, 7]
```

<br/>
<br/>

### Extend

`extend()`: extend the list

```python
list1 = [1,2,3]
list2 = ['a','b','c']

list1.extend(list2)

print(list1)

#>[1, 2, 3, 'a', 'b', 'c']
```

<br/>
<br/>

### Access element

Accessing a single item using index

```python
myList = [1, 'all', {'a':1}, ('a','b',1)]
print(myList[1])

#>'all'
```

<br/>
<br/>

### Access elements

Accesing multiple items using range notation

```python
myList = [1, 'all', {'a':1}, ('a','b',1)]
print(myList[0:1])

#>[1]
```

- We can use out of index numbers with this notation,

  ```python
  arr = [1,2,3,4]
  print(arr[6:])
  print(arr[:10])

  #>[]
  #>[1,2,3,4]
  ```

<br/>
<br/>

### Delete element

- `remove()` : Used to remove a specific item from a list.

  ```python
  myList = [1,2,3,4,5,6]
  myList.remove(3)
  print(myList)

  #>[1, 2, 4, 5, 6]
  ```

- `del` keyword : Used to remove a specific item at a specific index.

  ```python
  myList = [1,2,3,4,5,6]
  del myList[1]
  print(myList)

  #[1, 3, 4, 5, 6]
  ```

<br/>
<br/>

### Delete last element

- `pop()` : Used to remove the last item or a specific item at a specific index

  ```python
  myList = [1,2,3,4,5,6]
  myList.pop()
  myList.pop(0)
  print(myList)

  #>[2, 3, 4, 5]
  ```

<br/>
<br/>

### Delete all elements

`clear()` : to clear the entire list.

```python
myList = [1,2,3,4,5,6]
myList.clear()
print(myList)
#>[]
```

<br/>
<br/>

### Sort

- Using `sort()` method.

  ```python
  myList = [6,4,5,1,2,3]
  myList.sort()   # sort() method is inplace
  print(myList)

  #>[1, 2, 3, 4, 5, 6]
  ```

- Using `sorted()` function

  ```python
  myList = [6,4,5,1,2,3]
  sortedList = sorted(myList)    #sorted() function is not in place
  print(sortedList)

  #>[1, 2, 3, 4, 5, 6]
  ```

<br/>
<br/>

### Get index

`index()` : Returns the lowest index where the element appears.

```python
myList = [1,2,3,4,5,6]
print(myList.index(2))

#>1
```

<br/>
<br/>

### Reverse

`reverse()` : To reverse the list.

```python
myList = [1,2,3,4,5,6]
myList.reverse()
print(myList)

#>[6, 5, 4, 3, 2, 1]
```

<br/>
<br/>

### Get max element

`max()` : get the item with maximum value

```python
myList = [6,4,5,1,2,3]
res = max(myList)
print(res)

#>6
```

<br/>
<br/>
<br/>

## Unpacking list

If all items of a list were tuples of same len.

```python
myList = [('A',1),('B',2),('C',3),('D',4)]

for item1, item2 in myList:
    print(item1, item2)

#>A 1
#>B 2
#>C 3
#>D 4
```

```python
myList = [[1,2,3],['a','b','c']]

for i,j,k in myList:
    print(i,j,k)

#>1 2 3
#>a b c
```

<br/>
<br/>
<br/>

## List comphrehension

- The template for list comprehension is:

  ```
  new_list = [new_item for item in list]    #no conditions
  new_list = [new_item for item in list if condition]   #if condition only
  new_list = [new_item if condition else another_item for item in list ]   #if else condition
  ```

* An example of a simple list comprehension. (no condition)

  ```python
  var = [x for x in range(10)]
  print(var)

  #>[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
  ```

- An example of a list comprehension with if condition. _The if statement should follow the for statement._

  ```python
  evenNums = [x for x in range(5) if x%2 ==0]
  print(evenNums)

  #>[0, 2, 4]
  ```

- An example of a list comprehension with if-else condition. _The if-else statement should lead the for statement._

  ```python
  evenNums = [x if x%2 ==0 else 'Odd' for x in range(5)]
  print(evenNums)

  #>[0, 'Odd', 2, 'Odd', 4]
  ```

* An example of a complex nested list comprehension. The outermost for loop appears furthest to the right in the list comprehension.

  ```python
  #The conventional way

  keyPlayers = ['Raze', 'Viper']
  teamCombinations = [['Omen','KillJoy','Neon'],['Raze', 'Breach'], ['Raze','Reyna']]

  res = []

  for team in teamCombinations:
      for player in team:
          if player in keyPlayers:
              res.append(player)

  print(res)

  #>['Raze', 'Raze']
  ```

  ```python
  # The same thing using list comprehension

  keyPlayers = ['Raze', 'Viper']
  teamCombinations = [['Omen','KillJoy','Neon'],['Raze', 'Breach'], ['Raze','Reyna']]

  res = [player for team in teamCombinations for player in team  if player in keyPlayers]
  orint(res)

  # See that the order of for statements is similar to the conventional way!

  #>['Raze', 'Raze']
  ```

<br/>
<br/>
<br/>

## List replication

```py
arr = [0] * 26
print(arr)

#[0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0]
```

- It is to be noted that replication is shallow, meaning it copies the references to the inner object, not the inner object itself.

  ```py
  arr_2d = [[]]*2
  arr_2d[0].append(100)
  print(arr_2d)

  #[[100], [100]]
  ```
