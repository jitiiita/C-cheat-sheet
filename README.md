
# Mastering C++ STL Algorithms: Unleash the Power of Your Code
  - Searching algorithms
  - Sorting algorithms
  - Copying algorithms
  - Swapping algorithms
  - Set algorithms
  - Heap algorithms
  - Transform



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
      std::vector<int> vec = {1, 2, 4, 5, 6, 7};
      std::vector<int> targets = {3, 6, 7};
      auto it = std::find_first_of(vec.begin(), vec.end(), targets.begin(), targets.end());
      if (it != vec.end()) {
          std::cout << "First element from 'targets' found at position: " << std::distance(vec.begin(), it) << std::endl;
      } else {
          std::cout << "No element from 'targets' found in 'vec'" << std::endl;
      }
      // First element from 'targets' found at position: 4
      ```
  - adjacent_find
    - Description: Search for the first pair of adjacent elements in a specified range that satisfy a specified condition. You can also provide a binary predicate function to
      std::adjacent_find if you want to search for pairs that meet a specific condition other than equality. 
    - Example:
      ```c
      std::vector<int> vec = {1, 2, 2, 3, 4, 4, 5};
      auto it = std::adjacent_find(vec.begin(), vec.end());
      if (it != vec.end()) {
          std::cout << "First pair of adjacent equal elements found at position: " << std::distance(vec.begin(), it) << std::endl;
      } else {
          std::cout << "No adjacent equal elements found in 'vec'" << std::endl;
      }
      // 1 => 2,2
      ```
  - search
      - Description: Used to search for a subsequence within a given range. It returns an iterator pointing to the first occurrence of the subsequence within the range, or the end() iterator if the subsequence is not found.
      - Example:
        ```c
        std::vector<int> mainSequence = {1, 2, 3, 4, 5, 6, 7, 8, 9};
        std::vector<int> subSequence = {3, 4, 5};
    
        auto result = std::search(
            mainSequence.begin(), mainSequence.end(),
            subSequence.begin(), subSequence.end()
        );
    
        if (result != mainSequence.end()) {
            std::cout << "Subsequence found starting at index " << std::distance(mainSequence.begin(), result) << std::endl;
        } else {
            std::cout << "Subsequence not found in the main sequence." << std::endl;
        }
        // std::search is a useful algorithm when you need to find a subsequence within a range or container. It can be applied to a variety of data types and use cases.
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
    - Description: Used to determine the minimum value among two or more values.
    - Example:
    ```c
    int x = 5;
    int y = 3;

    // Find the minimum of x and y
    int minValue = std::min(x, y); // 3
    ```
  - Max
    - Description: used to determine the maximum value among two or more values
    - Example:
    ```c
    int x = 5;
    int y = 3;

    // Find the minimum of x and y
    int minValue = std::max(x, y); // 5
    ```
  - min_Element
    - Description: used to find the smallest element in a given range
    - Example:
    ```c
    std::vector<int> numbers = {5, 2, 8, 1, 6, 4, 7, 3};

    // Find the smallest element in the 'numbers' vector
    auto minElement = std::min_element(numbers.begin(), numbers.end()); // Smallest element: 1
    ```
  - max_Element
    - Description: used to find the largest element in a given range.
    - Example:
    ```c
    std::vector<int> numbers = {5, 2, 8, 1, 6, 4, 7, 3};

    // Find the largest element in the 'numbers' vector
    auto maxElement = std::max_element(numbers.begin(), numbers.end()); // Largest element: 8
    ```

## 6. Merge
  - Merge
    - Description: used to merge two sorted ranges into a single sorted range. 
    - Example:
    ```c
    std::vector<int> firstRange = {1, 3, 5, 7};
    std::vector<int> secondRange = {2, 4, 6, 8};
    std::vector<int> mergedResult(8); // The destination vector with enough space

    // Merge the two sorted ranges into 'mergedResult'
    std::merge(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), mergedResult.begin());
    // 1 2 3 4 5 6 7 8.
    ```
  - In-place merge
    - Description: This algorithm reorders the elements in a single sorted range in such a way that they form a merged, sorted range within the original range.
    - Example:
    ```c
    std::vector<int> numbers = {3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5};

    // Sort the 'numbers' vector in ascending order
    std::sort(numbers.begin(), numbers.begin() + 4);
    std::sort(numbers.begin() + 5, numbers.end());

    // Perform an in-place merge to create a single sorted range
    std::inplace_merge(numbers.begin(), numbers.begin() + 5, numbers.end());
    //1 1 2 3 3 4 5 5 5 6 9 
    ```

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
    - Description: Used to remove all elements equal to a specified value from a range. It does not actually erase the elements from the container but rather moves them to the end of the range and returns an iterator pointing to the new end.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 3, 5};

    // Remove all elements equal to 3
    auto newEnd = std::remove(numbers.begin(), numbers.end(), 3);

    // Erase the removed elements
    numbers.erase(newEnd, numbers.end());
    ```
  - remove_if
    - Description: used to remove elements from a range that satisfy a certain predicate or condition.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6};

    // Remove all odd numbers
    auto newEnd = std::remove_if(numbers.begin(), numbers.end(), [](int num) { return num % 2 != 0; });

    // Erase the removed elements
    numbers.erase(newEnd, numbers.end());
    ```
  - remove_copy
    - Description:  used to create a new sequence that contains all elements from the input sequence except for those matching a specified value. It copies elements from the input range to the output range, excluding elements that compare equal to the specified value. It doesn't modify the original input range.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 2, 4, 2, 5};
    std::vector<int> result;

    // Use std::remove_copy to copy elements from 'numbers' excluding the value 2
    std::remove_copy(numbers.begin(), numbers.end(), std::back_inserter(result), 2);
    ```
  - remove_copy_if
    - Description: used to create a new sequence that contains elements from the input sequence that do not satisfy a specified predicate.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6};
    std::vector<int> result;

    // Use std::remove_copy_if to copy even numbers from 'numbers' to 'result'
    std::remove_copy_if(numbers.begin(), numbers.end(), std::back_inserter(result), [](int num) { return num % 2 == 0; });

    ```

## 10. Replacing algorithms
  - replace
    - Description: used to replace all occurrences of a specified value with another value in a given range. It modifies the elements in place within the specified range.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 2, 3, 4, 2, 5};
    // Replace all occurrences of 2 with 0 in the 'numbers' vector
    std::replace(numbers.begin(), numbers.end(), 2, 0);
    ```
  - replace_if
    - Description: 
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5, 6};

    // Replace all even numbers with 0 in the 'numbers' vector
    std::replace_if(numbers.begin(), numbers.end(), [](int num) { return num % 2 == 0; }, 0); // 1, 0, 3, 0, 5, 0
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
  - accumulate
    - Description: used to calculate the sum of all elements in a range. It starts with an initial value and accumulates each element in the range using addition (or a specified binary operation).
    - Example:
    ```c
    int sum = std::accumulate(begin, end, initial_value);
    ```
  - adjacent_difference
    - Description: Calculates the differences between adjacent elements in a range and stores the results in another range. It is useful for calculating differences or rates of change.
    - Example:
    ```c
    std::adjacent_difference(begin, end, result_begin);
    ```
  - inner_product
    - Description: calculates the inner product of two sequences. It multiplies corresponding elements from two input ranges and then accumulates the results.
    - Example:
    ```c
    int result = std::inner_product(first1, last1, first2, initial_value);
    ```
  - partial_sum
    - Description: Used to compute a sequence of partial sums of the elements in a given range. It calculates the cumulative sums of the elements and stores the results in another range, often in the same container as the original elements.
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5};
    std::vector<int> partialSums(numbers.size());

    // Calculate and store the partial sums in 'partialSums'
    std::partial_sum(numbers.begin(), numbers.end(), partialSums.begin()); //1 3 6 10 15

    ```
  - power
    - Description: to calculate the power of a number:
    - Example:
    ```c
    double base = 2.0;
    double exponent = 3.0;

    // Calculate 2^3 using std::pow
    double result = std::pow(base, exponent);
    ```
  - iota
    - Description: Sequence of incrementing values to a range. It is often used to initialize a range with consecutive numbers.
    - Example:
    ```c
    std::vector<int> numbers(5); 
    // Use std::iota to assign consecutive values starting from 1
    std::iota(numbers.begin(), numbers.end(), 1); // 1, 2, 3, 4, 5
    ```
  - gcd and lcm
    - Description: calculate the greatest common divisor (std::gcd) and the least common multiple (std::lcm) of two or more integers.
    - Example:
    ```c
    int gcd_result = std::gcd(a, b);
    int lcm_result = std::lcm(a, b);
    ```

## 13. Generate algorithms
  - generate
    - Description: used to populate a range of elements in a container with values generated by a provided function or functor. It allows you to initialize or update elements in a range using a specified generator function.
    - Example:
    ```c
    std::vector<int> numbers(5);
    // Use std::generate to populate the vector with random values
    std::random_device rd;
    std::mt19937 gen(rd());
    std::uniform_int_distribution<int> dist(1, 100);

    std::generate(numbers.begin(), numbers.end(), [&]() { return dist(gen); });
    // The output will contain five random integers between 1 and 100.
    ```
  - generate_n
    - Description: used to populate a specified number of elements in a container with values generated by a provided function or functor. It allows you to initialize or update a fixed number of elements in a range using a specified generator function.
    - Example:
    ```c
    std::vector<int> numbers;

    // Use std::generate_n to generate 5 random values and store them in the vector
    std::random_device rd;
    std::mt19937 gen(rd());
    std::uniform_int_distribution<int> dist(1, 100);

    std::generate_n(std::back_inserter(numbers), 5, [&]() { return dist(gen); });

    ```

## 14. Filling algorithms
  - fill
    - Description: used to assign a specified value to all elements in a given range. 
    - Example:
    ```c
    std::vector<int> numbers(5);

    // Use std::fill to set all elements in the vector to 42
    std::fill(numbers.begin(), numbers.end(), 42);
    ```

## 15. Copying algorithms
  - copy
    - Description: used to copy elements from one range (container) to another.
    - Example:
    ```c
    std::vector<int> source = {1, 2, 3, 4, 5};
    std::vector<int> destination(5); // Destination vector with the same size as the source

    // Use std::copy to copy elements from 'source' to 'destination'
    std::copy(source.begin(), source.end(), destination.begin());
    ```
  - copy_backward
    - Description: used to copy elements from one range (container) to another in reverse order.
    - Example:
    ```c
    std::vector<int> source = {1, 2, 3, 4, 5};
    std::vector<int> destination(5); // Destination vector with the same size as the source

    // Use std::copy_backward to copy elements from 'source' to 'destination' in reverse order
    std::copy_backward(source.begin(), source.end(), destination.end());
    ```
  - copy_n
    - Description: used to copy a specified number of elements from one range (container) to another
    - Example:
    ```c
    std::vector<int> source = {1, 2, 3, 4, 5};
    std::vector<int> destination(3); // Destination vector with enough space for 3 elements

    // Use std::copy_n to copy the first 3 elements from 'source' to 'destination'
    std::copy_n(source.begin(), 3, destination.begin());
    ```

## 16. Heap algorithms
  - make_heap
    - Description: Converts a range of elements into a max heap or min heap.
    - Example:
    ```c
    std::vector<int> vec = {3, 1, 4, 1, 5, 9, 2, 6, 5};
    std::make_heap(vec.begin(), vec.end()); // Converts 'vec' into a max
    ```
  - push_heap
    - Description: Inserts an element into a heap and maintains the heap property.
    - Example:
    ```c
    vec.push_back(7);
    std::push_heap(vec.begin(), vec.end());
    ```
  - pop_heap
    - Description: Removes the top element (root) of a heap (which is the largest element in a max heap or the smallest element in a min heap) and moves it to the end of the range.
    - Example:
    ```c
    std::pop_heap(vec.begin(), vec.end());
    vec.pop_back(); // Remove the largest element from the heap
    ```
  - sort_heap
    - Description: Sorts the elements of a heap in ascending order (for a max heap) or descending order (for a min heap).
    - Example:
    ```c
    std::sort_heap(vec.begin(), vec.end()); // Sort 'vec' in ascending order
    ```
  - is_heap
    - Description: Checks if a range is a valid heap.
    - Example:
    ```c
    bool is_heap = std::is_heap(vec.begin(), vec.end()); // Checks if 'vec' is a heap
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
    - Description: used to randomly shuffle the elements of a sequence, such as an array, vector, or list. It rearranges the elements into a random order. 
    - Example:
    ```c
    std::vector<int> numbers = {1, 2, 3, 4, 5};

    // Create a random number generator using std::random_device
    std::random_device rd;
    std::default_random_engine rng(rd());

    // Use std::shuffle to randomize the order of elements in 'numbers'
    std::shuffle(numbers.begin(), numbers.end(), rng);
    ```

## 19. Comparing algorithms
  - Lexicographical compare
    - Description: compare two sequences lexicographically. It determines whether one sequence is less than another based on the lexicographic order of their elements. This is often used to compare strings, character arrays, or any other sequence of comparable elements.
    - Example:
    ```c
    std::string str1 = "apple";
    std::string str2 = "banana";

    bool result = std::lexicographical_compare(
        str1.begin(), str1.end(),
        str2.begin(), str2.end()
    );
    ```
## 20. Equal
    - Description:  compares two ranges for equality. It checks whether all corresponding elements in two input ranges are equal. If all elements match, it returns true; otherwise, it returns false.
    - Example:
    ```c
    std::vector<int> vec1 = {1, 2, 3, 4, 5};
    std::vector<int> vec2 = {1, 2, 3, 4, 5};

    bool result = std::equal(vec1.begin(), vec1.end(), vec2.begin()); //true
    ```

## 21. Mismatch
  - Mismatch
    - Description: Used to find the first pair of elements in two ranges that do not match
    - Example:
    ```c
    std::vector<int> firstRange = {1, 2, 3, 4, 5};
    std::vector<int> secondRange = {1, 2, 6, 4, 5};

    // Find the first pair of elements that do not match between 'firstRange' and 'secondRange'
    auto mismatchPair = std::mismatch(firstRange.begin(), firstRange.end(), secondRange.begin());
    // First mismatch: 3 in firstRange and 6 in secondRange.
    ```

## 22. Set algorithms
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
      std::set_difference(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(difference));
      //output will be: 1 2.
      ```
  - set_intersection
    - Description: Used to compute the set intersection between two sorted ranges. It finds the elements that are common to both ranges and stores them in a destination range. 
    - Example:
      ```c
      std::vector<int> firstRange = {1, 2, 3, 4, 5};
      std::vector<int> secondRange = {3, 4, 5, 6, 7};
      std::vector<int> intersection;
  
      // Compute the set intersection between 'firstRange' and 'secondRange'
      std::set_intersection(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(intersection));
      //output will be: 3 4 5.
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
      // output will be: 1 2 6 7.
    ```
  - set_union
    - Description: Used to compute the set union of two sorted ranges. It combines the elements from both ranges into a single sorted range without any duplicates.
    - Example:
      ```c
      std::vector<int> firstRange = {1, 2, 3, 4, 5};
      std::vector<int> secondRange = {3, 4, 5, 6, 7};
      std::vector<int> unionResult;
  
      // Compute the set union between 'firstRange' and 'secondRange'
      std::set_union(firstRange.begin(), firstRange.end(), secondRange.begin(), secondRange.end(), std::back_inserter(unionResult));
      // output will be: 1 2 3 4 5 6 7.
      ```

## 23. Swapping algorithms
  - iter swap
    - Description: Used to swap the values of two elements pointed to by iterators.
    - Example: 
      ```c
      std::vector<int> numbers = {1, 2, 3, 4};
      // Swap the second and third elements using std::iter_swap
      std::iter_swap(numbers.begin() + 1, numbers.begin() + 2); // output will be: 1 3 2 4.
      ```
  - swap
    - Description: Used to swap the values of two objects or variables of the same type. 
    - Example:
      ```c
      int x = 5;
      int y = 10;
  
      // Swap the values of x and y using std::swap
      std::swap(x, y); // x = 10, y = 5
      ```
  - swap_ranges
    - Description: Used to swap the elements of two ranges of equal length. It swaps each element in the first range with the corresponding element in the second range.
    - Example:
      ```c
      std::vector<int> firstRange = {1, 2, 3};
      std::vector<int> secondRange = {4, 5, 6};

      // Swap the elements of 'firstRange' with the elements of 'secondRange'
      std::swap_ranges(firstRange.begin(), firstRange.end(), secondRange.begin());
      // firstRange: 4 5 6
      // secondRange: 1 2 3
      ```

## 24. transform
  - Transform
    - Description: used to apply a specified operation or function to each element within a given range or container and store the results in another range or container
    - Example:
      ```c
      std::vector<int> numbers = {1, 2, 3, 4, 5};
      std::vector<int> squaredNumbers;
  
      // Use std::transform to square each element and store the result in 'squaredNumbers'
      std::transform(numbers.begin(), numbers.end(), std::back_inserter(squaredNumbers), [](int x) { return x * x; });
      // output will be: 1 4 9 16 25.
      ```

## 25. unique
  - unique
    - Description: Used to remove consecutive duplicate elements from a sorted range or container.
    - Example:
      ```c
      std::vector<int> numbers = {1, 2, 2, 3, 3, 3, 4, 4, 5, 5};
      // Remove consecutive duplicates from the 'numbers' vector
      auto newEnd = std::unique(numbers.begin(), numbers.end());
      // Resize the vector to contain only unique elements
      numbers.resize(std::distance(numbers.begin(), newEnd)); //1 2 3 4 5.
      ```
  - unique_copy
    - Description: Used to create a copy of a range while eliminating consecutive duplicate elements
    - Example:
      ```c
      std::vector<int> numbers = {1, 2, 2, 3, 3, 3, 4, 4, 5, 5};
      std::vector<int> uniqueNumbers;
  
      // Create a copy of 'numbers' with consecutive duplicates removed
      std::unique_copy(numbers.begin(), numbers.end(), std::back_inserter(uniqueNumbers)); //1 2 3 4 5.
      ```
