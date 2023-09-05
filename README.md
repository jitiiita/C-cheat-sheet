
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
      auto it = std::adjacent_find(vec.begin(), vec.end());
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
    - Description: Search for a specific subsequence of elements within a specified range.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 2, 3, 2, 4, 2, 5};
      
      int target_value = 2;
      size_t consecutive_count = 3;
  
      auto it = std::search_n(vec.begin(), vec.end(), consecutive_count, target_value);
  
      if (it != vec.end()) {
          std::cout << "Found a subsequence of " << consecutive_count << " consecutive " << target_value << " starting at position: " << std::distance(vec.begin(), it) << std::endl;
      } else {
          std::cout << "No subsequence of " << consecutive_count << " consecutive " << target_value << " found in 'vec'" << std::endl;
      }
      ``` 
  - binary_search
    - Description: Determines if a sorted range contains a specific element.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5};
      bool found = std::binary_search(vec.begin(), vec.end(), 3);
      ```
  - equal_range
    - Description: Find a range of elements in a sorted sequence that match a specified value or satisfy a given binary predicate
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 2, 3, 3, 3, 4, 5};
      auto range = std::equal_range(vec.begin(), vec.end(), 3);
      std::cout << "Occurrences of 3 in the range: [" << std::distance(vec.begin(), range.first) << ", " << std::distance(vec.begin(), range.second) << ")" << std::endl;
      ```
  - lower_bound
    - Description: Find the first element in a sorted sequence that is not less than a specified value or that satisfies a given binary predicate
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5, 6, 7};

      // Find the first element not less than 4 in 'vec'
      auto it = std::lower_bound(vec.begin(), vec.end(), 4);
  
      if (it != vec.end()) {
          std::cout << "First element not less than 4: " << *it << std::endl;
      } else {
          std::cout << "No element not less than 4 found in 'vec'" << std::endl;
      }
      ```
  - upper_bound
    - Description: Find the first element in a sorted sequence that is greater than a specified value or that satisfies a given binary predicate.
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 3, 4, 5, 6, 7};
  
      // Find the first element greater than 4 in 'vec'
      auto it = std::upper_bound(vec.begin(), vec.end(), 4);
  
      if (it != vec.end()) {
          std::cout << "First element greater than 4: " << *it << std::endl;
      } else {
          std::cout << "No element greater than 4 found in 'vec'" << std::endl;
      }
      ```

## 2. Sorting algorithms
  - sort
    - Description: Sort elements in a given range
    - Example:
    ```c
    std::vector<int> numbers = {5, 2, 9, 1, 5, 6};
    std::sort(numbers.begin(), numbers.end());
    ```
    ```c
      vector<int> v = {1,2,3,4,5,6,7,8,9};
      sort(v.begin(), v.end(), compare);
      ```
  - stable_sort
    - Description: Sort elements in a given range, just like std::sort.
    - Example:
    ```c
    std::vector<int> numbers = {5, 2, 9, 1, 5, 6};
    // Sort the elements in ascending order using std::stable_sort
    std::stable_sort(numbers.begin(), numbers.end());
    ```

## 3. Reversing
  - reverse
    - Description: Reverse the order of elements in a specified range
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    std::reverse(numbers.begin(), numbers.end());
    ```
  - reverse_copy
    - Description: create a reversed copy of a specified range of elements.
    - Example:
    ```c
    std::vector<int> original = {1, 2, 3, 4, 5};
    std::vector<int> reversed_copy(original.size());

    // Create a reversed copy of the 'original' and store it in 'reversed_copy'
    std::reverse_copy(original.begin(), original.end(), reversed_copy.begin());
    ```
## 4. Rotating
  - rotate
    - Description: Used to rotate the elements in a specified range
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    // Rotate the elements so that '3' becomes the new starting element
    std::rotate(numbers.begin(), numbers.begin() + 2, numbers.end());
    ```
    ```c
    std::list<int> numbers = {1, 2, 3, 4, 5};
    // Rotate the elements so that '3' becomes the new starting element
    std::rotate(numbers.begin(), std::next(numbers.begin(), 2), numbers.end());
    ```
  - rotate_copy
    - Description: copying elements from a source range to a destination range with a rotation applied by using a combination of STL algorithms like std::copy, std::rotate, and iterators.
    - Example:
    ```c
    std::vector<int> source = {1, 2, 3, 4, 5};
    std::vector<int> destination(source.size());

    // Define the position to start the rotation
    size_t rotate_position = 2; // Rotate by 2 positions

    // Perform the rotation and copy to the destination
    std::rotate_copy(source.begin(), source.begin() + rotate_position, source.end(), destination.begin());

    ```
## 5. Minimum & Maximum
  - Min
    - Description: 
    - Example:
    ```c
    ```
  - Max
    - Description: 
    - Example:
    ```c
    ```
  - Min_Element
    - Description: 
    - Example:
    ```c
    ```
  - Max_Element
    - Description: 
    - Example:
    ```c
    ```

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
