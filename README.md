
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
    - Description: Partially sort a range of elements such that the element at a specified position (the "nth" element) is in its correct sorted position, and all elements before it are less than or equal to it, and all elements after it are greater than or equal to it. 
    - Example:
    ```c
    std::vector<int> numbers = {5, 2, 9, 1, 5, 6, 4, 7, 3};
    // Find the 3rd smallest element using std::nth_element
    std::nth_element(numbers.begin(), numbers.begin() + 2, numbers.end()); //3
    ```

## 8. Partition and Stable partition
  - partition and stable partition
    - Description: Partition the elements of a container or range based on a given condition
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6};
    auto isEven = [](int x) { return x % 2 == 0; };
    std::partition(numbers.begin(), numbers.end(), isEven);
    ```
  - stable partition
    - Description: Separates elements into two groups based on a condition.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6};
    auto isEven = [](int x) { return x % 2 == 0; };
    std::stable_partition(numbers.begin(), numbers.end(), isEven);
    ```

## 9. Removing algorithms
  - remove
    - Description: 
    - Example:
    ```c
    ```
  - remove_if
    - Description: 
    - Example:
    ```c
    ```
  - remove_copy
    - Description: 
    - Example:
    ```c
    ```
  - remove_copy_if
    - Description: 
    - Example:
    ```c
    ```

## 10. Replacing algorithms
  - replace
    - Description: 
    - Example:
    ```c
    ```
  - replace_if
    - Description: 
    - Example:
    ```c
    ```
  - replace_copy
    - Description: 
    - Example:
    ```c
    ```
  - replace_copy_if
    - Description: 
    - Example:
    ```c
    ```

## 11. for each
  - for_each
    - Description: Used to apply a specified function or functor to each element within a given range or container.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    // Use a lambda function to square and print each element
    std::for_each(numbers.begin(), numbers.end(), [](int x) { std::cout << x * x << " "; });
    ```

## 12. Numeric algorithms
  - Accumulate
    - Description: 
    - Example:
    ```c
    ```
  - Adjacent difference
    - Description: 
    - Example:
    ```c
    ```
  - Inner product
    - Description: 
    - Example:
    ```c
    ```
  - Partial sum
    - Description: 
    - Example:
    ```c
    ```
  - Power
    - Description: 
    - Example:
    ```c
    ```

## 13. Generate algorithms
  - generate
    - Description: 
    - Example:
    ```c
    ```
  - generate_n
    - Description: 
    - Example:
    ```c
    ```

## 14. Filling algorithms
  - fill
    - Description: 
    - Example:
    ```c
    ```
  - fill_n
    - Description: 
    - Example:
    ```c
    ```

## 15. Copying algorithms
  - copy
    - Description: 
    - Example:
    ```c
    ```
  - copy_backward
    - Description: 
    - Example:
    ```c
    ```
  - copy_n
    - Description: 
    - Example:
    ```c
    ```

## 16. Heap algorithms
  - push_heap
    - Description: 
    - Example:
    ```c
    ```
  - pop_heap
    - Description: 
    - Example:
    ```c
    ```
  - make_heap
    - Description: 
    - Example:
    ```c
    ```
  - sort_heap
    - Description: 
    - Example:
    ```c
    ```
  - is_heap
    - Description: 
    - Example:
    ```c
    ```

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
    - Description: 
    - Example:
    ```c
    ```

## 19. Comparing algorithms
  - Lexicographical compare
    - Description: 
    - Example:
    ```c
    ```
  - Equal and mismatch
    - Description: 
    - Example:
    ```c
    ```

## 20. Mismatch
  - Mismatch
    - Description: 
    - Example:
    ```c
    ```

## 21. Set algorithms
  - includes
    - Description: Used to check whether one range of elements is a subset of another range. It determines whether all elements in the first range are also present in the second range. 
    - Example:
    ```c
    std::vector<int> mainList = {1, 2, 3, 4, 5, 6};
    std::vector<int> subList = {2, 4, 6};

    // Check if 'subList' is a subset of 'mainList'
    bool isSubset = std::includes(mainList.begin(), mainList.end(), subList.begin(), subList.end());
    ```
  - set_difference
    - Description: Used to compute the set difference between two sorted ranges. It finds the elements that are present in the first range but not in the second range and stores them in a destination range. 
    - Example:
    ```c
    std::vector<int> firstRange = {1, 2, 3, 4, 5};
    std::vector<int> secondRange = {3, 4, 5, 6, 7};
    std::vector<int> difference;

    // Compute the set difference between 'firstRange' and 'secondRange'
    std::set_difference(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(difference)); //output will be: 1 2.
    ```
  - set_intersection
    - Description: Used to compute the set intersection between two sorted ranges. It finds the elements that are common to both ranges and stores them in a destination range. 
    - Example:
    ```c
    std::vector<int> firstRange = {1, 2, 3, 4, 5};
    std::vector<int> secondRange = {3, 4, 5, 6, 7};
    std::vector<int> intersection;

    // Compute the set intersection between 'firstRange' and 'secondRange'
    std::set_intersection(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(intersection));//output will be: 3 4 5.
    ```
  - set_symmetric_difference
    - Description: Used to compute the symmetric difference between two sorted ranges. The symmetric difference contains elements that are present in either of the two ranges but not in their intersection
    - Example:
    ```c
    std::vector<int> firstRange = {1, 2, 3, 4, 5};
    std::vector<int> secondRange = {3, 4, 5, 6, 7};
    std::vector<int> symmetricDifference;

    // Compute the set symmetric difference between 'firstRange' and 'secondRange'
    std::set_symmetric_difference(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(symmetricDifference));

    ```
  - set_union
    - Description: Used to compute the set union of two sorted ranges. It combines the elements from both ranges into a single sorted range without any duplicates.
    - Example:
    ```c
    std::vector<int> firstRange = {1, 2, 3, 4, 5};
    std::vector<int> secondRange = {3, 4, 5, 6, 7};
    std::vector<int> unionResult;

    // Compute the set union between 'firstRange' and 'secondRange'
    std::set_union(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(unionResult)); //output will be: 1 2 3 4 5 6 7.

    ```

## 22. Swapping algorithms
  - iter swap
    - Description: 
    - Example:
    ```c
    ```
  - swap
    - Description: 
    - Example:
    ```c
    ```
  - swap_ranges
    - Description: 
    - Example:
    ```c
    ```

## 23. transform
  - Transform
    - Description: 
    - Example:
    ```c
    ```

## 24. unique
  - unique
    - Description: 
    - Example:
    ```c
    ```
  - unique_copy
    - Description: 
    - Example:
    ```c
    ```
