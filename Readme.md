# Goal

- [ ] **Data Structures**

  - [ ] Trees
    - [ ] **Binary Trees**
      - [ ] [Recursive preorder](#recursive-preorder), [inorder](), [postorder traversal]()
      - [ ] Iterative preorder, inorder, postorder traversal
      - [ ] Level-order traversal 
      - [ ] Recursive solutions
    - [ ] N-ary tree
    - [ ] Trie-tree

  - [ ] Hash tables
  - [ ] Heaps
  - [ ] Graphs

- [ ] **Sorting**
- [ ] **Recursion** 

## Theoretical Questions

- [ ] **Operating Systems**
- [ ] **Discrete Mathematics**

## Answers


# Resources

## Data Structures
So the number one thing you should remember about a given data structure is what operations it supports, and what is the running time you can expect from those operations.


### Trees

#### Binary Trees
  ```python
      # Definition for a binary tree node.
 class TreeNode:
     def __init__(self, val=0, left=None, right=None):
         self.val = val
         self.left = left
         self.right = right  
  ```

- **Pre-order traversal**
  ```python 
      def preorderIterative(root):
          if root is None:
              return
              
          stack = deque()
          stack.append(root)

          while stack:

              curr = stack.pop()
              print(curr.data, end=' ')

              if curr.right:
                  stack.append(curr.right)

              if curr.left:
                  stack.append(curr.left)
    ```
  Pre-order traversal is to visit the root first. Then traverse the left subtree. Finally, traverse the right subtree.
  - recursive-preorder

### Heaps

Куча — это особая древовидная структура, в которой каждый родительский узел меньше или равен своему дочернему узлу. Тогда это называется Min Heap. Если каждый родительский узел больше или равен своему дочернему узлу, он называется максимальной кучей. Это очень полезно при реализации приоритетных очередей, где элементу очереди с более высоким весом предоставляется больший приоритет при обработке.

Куча является максимально эффективной реализацией абстрактного типа данных, который называется очередью с приоритетом. Кучи имеют решающее значение в некоторых эффективных алгоритмах на графах, таких, как алгоритм Дейкстры на d-кучах и сортировка методом пирамиды.

В куче элементы хранятся в виде двоичного дерева, то есть у элементов есть два потомка - левый и правый. В вершине кучи находится один элемент, у него - два потомка на следующем уровне, у них, в свою очередь, по два потомка на третьем уровне (итого - 4 элемента на третьем уровне) и т. д. Уровни заполняются в порядке увеличения номера уровня, а сам уровень заполняется слева направо.

So basically, a heap supports two operations. There's some bells and whistles you can throw on. But the two things you gotta now is insertion and extract min.

#### Общие характеристики
Основные операции:
 1) Добавить элемент в структуру данных. Сложность O(log n)
 2) Извлечь из структуры данных наибольший (вариант - наименьший) элемент. Извлеченный элемент удаляется из структуры.
Все 

## Sorting 
- Primitive Sorting O(n^2)
  - Selection Sort (Сортировка выбором)
  
  ```python
  def selection_sort(nums):
    # This value of i corresponds to how many values were sorted
    for i in range(len(nums)):
        # We assume that the first item of the unsorted segment is the smallest
        lowest_value_index = i
        # This loop iterates over the unsorted items
        for j in range(i + 1, len(nums)):
            if nums[j] < nums[lowest_value_index]:
                lowest_value_index = j
        # Swap values of the lowest unsorted element with the first unsorted
        # element
        nums[i], nums[lowest_value_index] = nums[lowest_value_index], nums[i]
   ```
  
  - Insertion Sort (Сортровка вставками)
  
    **Insertion Sort** является _stable_ и _in-place_ алгоритмом, который действительно хорошо работает только для почти отсортированных или небольших массивов.
      
    in-place: Требует небольшого постоянного дополнительного пространства памяти (не зависит от n),он перезаписывает исходные ячейки памяти элементов в коллекции.  
    stable: вернет одинаковые элементы в том же относительном порядке
        
    > #### Характеристики:     
           Худшее и среднее время: O(n^2)
           Лучшее время для маленьких массивов (примерно 10 элементов): O(n)
        
      **Затраты времени:** O(n) основной, O(1) дополнительной 
        
      Сам по себе неэффективен, поэтому может использоваться либо когда массив мал или в комбинации с другими алгоритмами

      ```python 
            def InsertionSort(arr):
                for i in range(1, len(arr)):
                    key = arr[i]
                    j = i-1
                    while j >=0 and arr[j] > k :
                        arr[j+1] = arr[j]
                        j -= 1
                    arr[j+1] = key 
       ```
       
  - Bubble Sort (Сортировка Пузырьком)
  
      ```python 
        def bubble_sort(nums):
          # We set swapped to True so the loop looks runs at least once
          swapped = True
          while swapped:
              swapped = False
              for i in range(len(nums) - 1):
                  if nums[i] > nums[i + 1]:
                      # Swap the elements
                      nums[i], nums[i + 1] = nums[i + 1], nums[i]
                      # Set the flag to True so we'll loop again
                      swapped = True
       ```
  
