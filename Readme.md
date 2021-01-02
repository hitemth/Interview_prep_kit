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

### Trees

- **Pre-order traversal**

  Pre-order traversal is to visit the root first. Then traverse the left subtree. Finally, traverse the right subtree.
  - recursive-preorder


### Sorting 
- Primitive Sorting O(n^2)
  - Selection Sort (Сортировка выбором)
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
Эффективна
  - Bubble Sort (Сортировка Пузырьком)
