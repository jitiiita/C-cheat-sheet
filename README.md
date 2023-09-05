
# STL algorithms
## 1. Searching algorithms
  - find
    - Description: Searches for a specified element in a range defined by two iterators.
    - Example:
        ```c
        std::vector<int> vec = {1, 2, 3, 4, 5};
        auto it = std::find(vec.begin(), vec.end(), 3);
        if (it != vec.end()) {
            // Element found
        } else {
            // Element not found
        }
        ```
  - find_if
    - Description: Searches for the first element in a range that satisfies a specified condition.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5};
      auto it = std::find_if(vec.begin(), vec.end(), [](int x) { return x > 3; });
      if (it != vec.end()) {
          // Element satisfying the condition found
      } else {
          // Element not found
      }
      ```
  - find_first_of
    - Description: Search for the first occurrence of any element from a specified set of elements within a given range
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5};
      std::vector<int> targets = {3, 6, 7};
      auto it = std::find_first_of(vec.begin(), vec.end(), targets.begin(), targets.end());
      if (it != vec.end()) {
          std::cout << "First element from 'targets' found at position: " << std::distance(vec.begin(), it) << std::endl;
      } else {
          std::cout << "No element from 'targets' found in 'vec'" << std::endl;
      }
      ```
  - adjacent_find
    - Description: Search for the first pair of adjacent elements in a specified range that satisfy a specified condition.
    - Example:
      ```c
      auto it = std::adjacent_find(vec.begin(), vec.end(), [](int a, int b) { return b > a; });
      if (it != vec.end()) {
          std::cout << "First pair of adjacent equal elements found at position: " << std::distance(vec.begin(), it) << std::endl;
      } else {
          std::cout << "No adjacent equal elements found in 'vec'" << std::endl;
      }
      ```
  - search
      - Description: Searches for a subsequence within a range.
      - Example:
        ```c
        std::vector<int> haystack = {1, 2, 3, 4, 5, 6};
        std::vector<int> needle = {3, 4, 5};
        auto it = std::search(haystack.begin(), haystack.end(), needle.begin(), needle.end());
        if (it != haystack.end()) {
            // Subsequence found
        } else {
            // Subsequence not found
        }
        ```
  - search_n
  - binary_search
    - Description: Determines if a sorted range contains a specific element.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5};
      bool found = std::binary_search(vec.begin(), vec.end(), 3);
      ```
  - equal_range
  - lower_bound
  - upper_bound

## 2. Sorting algorithms
  - sort
    ```c
        int arr[N] = {4, 2, 6, 5, 8, 1, 7, 9};
        sort(arr, arr + N);
    ```
    ```c
        vector<int> v = {1,2,3,4,5,6,7,8,9};
        sort(v.begin(), v.end(), compare);
      ```
  - stable_sort
  - partial_sort_copy 
  - partial_sort

## 3. Reversing
  - reverse
  - reverse_copy
    
## 4. Rotating
  - rotate
  - rotate_copy

## 5. Minimum & Maximum
  - Min
  - Max
  - Min_Element
  - Max_Element

## 6. Merge
  - Merge
  - In-place merge

## 7. nth element
  - Nth element

## 8. Partition and Stable partition
  - partition and stable partition
  - stable partition

## 9. Removing algorithms
  - remove
  - remove_if
  - remove_copy
  - remove_copy_if

## 10. Replacing algorithms
  - replace
  - replace_if
  - replace_copy
  - replace_copy_if

## 11. for each
  - for_each

## 12. Numeric algorithms
  - Accumulate
  - Adjacent difference
  - Inner product
  - Partial sum 
  - Power

## 13. Generate algorithms
  - generate
  - generate_n

## 14. Filling algorithms
  - fill
  - fill_n

## 15. Copying algorithms
  - copy
  - copy_backward
  - copy_n

## 16. Heap algorithms
  - push_heap
  - pop_heap
  - make_heap
  - sort_heap
  - is_heap

## 17. Counting algorithms
  - count
    - Description: Counts the number of occurrences of a specified element in a range.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 2, 3, 2, 4};
      int count = std::count(vec.begin(), vec.end(), 2);
        ```
  - count_if
    - Description: Counts the number of elements in a range that satisfy a given condition.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5};
      int count = std::count_if(vec.begin(), vec.end(), [](int x) { return x % 2 == 0; });
      ```
## 18. Randomizing algorithms
  - Random shuffle

## 19. Comparing algorithms
  - Lexicographical compare
  - Equal and mismatch

## 20. Mismatch
  - Mismatch

## 21. Set algorithms
  - includes 
  - set difference 
  - set intersection 
  - set symmetric difference
  - set union

## 22. Swapping algorithms
  - iter swap
  - swap
  - swap_ranges

## 23. transform
  - Transform

## 24. unique
  - unique
  - unique_copy
