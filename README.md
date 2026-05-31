# Python-Programms_26
## 1. Reverse a String -- String
    s = "Happy Coding"
    reversed_s = "".join(reversed(s))
    reversed_s = ""
    for char in s:
      reversed_s = char + reversed_s
## 2. Count the Characters in an Array -- Array
    arr = ["hello", "world", "python"]
    for word in arr:
        print(f"{word}: {len(word)} characters")
    total = sum(len(word) for word in arr)
    print(f"Total: {total} characters")

## 3. Count the Character in an array without spaces -- Array
    arr = ["hello world", "python is fun", "open ai"]
    for word in arr:
        count = len(word.replace(" ", ""))
        print(f"'{word}': {count} characters (excluding spaces)")
    total = sum(len(word.replace(" ", "")) for word in arr)
    print(f"Total: {total} characters")

## 4.Count the Characters in String excluding spaces  -- String
    s = "Hello World Python"
    count = len(s.replace(" ", ""))
    print(f"Count (excluding spaces): {count}")  # 15
    
## 6. Length of the String
    s = "Hello World Python"
    length = len(s.replace(" ", ""))
    print(f"Length (excluding spaces): {length}")  # 15

## 7. Reverse the given number
    num = 12345
    def reverse_num(n, rev=0):
        if n == 0:
            return rev
        return reverse_num(n // 10, rev * 10 + n % 10)
    print(reverse_num(num))

## 8. Factorial of gievn number
    def factorial(n):
        if n == 0 or n == 1:
            return 1
        return n * factorial(n - 1)
    print(factorial(5))  # 120

## 9. Swap two numbers
    a, b = 10, 20
    temp = a
    a = b
    b = temp
    print(f"After swap: a = {a}, b = {b}")  # a = 20, b = 10)

## 10. Check Palindrome
    s = "Bab"
    reversed_s = "".join(reversed(s))
    reversed_s = ""
    for char in s:
        reversed_s = char + reversed_s
    if s == reversed_s:
        print("Is a Palindrome")
    else:
        print("Not a Palindrome")

## 11. Find the largest Element in an array
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    largest = arr[0]
    for i in arr:
        if i > largest:
            largest = i
    print(f"Largest element: {largest}")  # 9

## 12. Find the second largest Element in an array
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    largest = second_largest = float('-inf')
    for i in arr:
        if i > largest:
            second_largest = largest
            largest = i
        elif i > second_largest and i != largest:
            second_largest = i
    print(f"Second Largest element: {second_largest}")  # 6

## 13. Find the Third largest Element in an array
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    largest = float('-inf')
    second_largest = float('-inf')
    third_largest = float('-inf')
    for num in arr:
        if num > largest:
            third_largest = second_largest   
            second_largest = largest         
            largest = num                    

        elif num > second_largest and num != largest:
            third_largest = second_largest   
            second_largest = num             
        elif num > third_largest and num != second_largest:
            third_largest = num              
    print(f"Array         : {arr}")
    print(f"Largest       : {largest}")
    print(f"Second Largest: {second_largest}")
    print(f"Third Largest : {third_largest}")

## 14. Sorting an Array
    // arr = list(map(int, input("Enter numbers separated by spaces: ").split())) -- Dynamic Data
    // print(f"Ascending  : {sorted(arr)}") -- Dynamic Data
    // print(f"Descending : {sorted(arr, reverse=True)}") --Dynamic Data
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    asc  = sorted(arr)
    desc = sorted(arr, reverse=True)
    print(f"Ascending  : {asc}")   # [1, 1, 2, 3, 4, 5, 6, 9]
    print(f"Descending : {desc}")  # [9, 6, 5, 4, 3, 2, 1, 1]

## 15. Bubble Sort -- O(n) / O(n²) / O(n²)
    Repeatedly compares adjacent elements and swaps them if out of order.
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
    print(f"Ascending  : {arr}")   # [1, 1, 2, 3, 4, 5, 6, 9]

## 16. Selection Sort -- O(n²) / O(n²) / O(n²)
    Finds the minimum element and places it at the beginning.
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    n = len(arr)
    for i in range(n):
        min_idx = i
        for j in range(i + 1, n):
            if arr[j] < arr[min_idx]:
                min_idx = j
         arr[i], arr[min_idx] = arr[min_idx], arr[i]
    print(f"Ascending  : {arr}")   # [1, 1, 2, 3, 4, 5, 6, 9]

## 17. Insertion Sort -- O(n) / O(n²) / O(n²)
    Builds the sorted array one item at a time.
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j + 1] = arr[j]
            j -= 1
        arr[j + 1] = key
    print(f"Ascending  : {arr}")   # [1, 1, 2, 3, 4, 5, 6, 9]

## 18. Merge Sort --O(n log n) / O(n log n) / O(n log n)
    Divide array into halves , Sort each half recursively and Merge sorted halves
    def merge_sort(arr):
        if len(arr) <= 1:
            return arr
        mid = len(arr) // 2
        left  = merge_sort(arr[:mid])
        right = merge_sort(arr[mid:])
        return merge(left, right)

    def merge(left, right):
        result = []
        i = j = 0
        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                result.append(left[i])
                i += 1
            else:
                result.append(right[j])
                j += 1
        result.extend(left[i:])
        result.extend(right[j:])
        return result

    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    print(f"Merge Sort: {merge_sort(arr)}")  # [1, 1, 2, 3, 4, 5, 6, 9]

## Quick Sort :- O(n log n) / O(n log n) / O(n²)
    Chooses a pivot and partitions the array.
    def quick_sort(arr):
        if len(arr) <= 1:
            return arr
        pivot = arr[len(arr) // 2]
        left  = [x for x in arr if x < pivot]
        mid   = [x for x in arr if x == pivot]
        right = [x for x in arr if x > pivot]
        return quick_sort(left) + mid + quick_sort(right)
    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    print(f"Quick Sort: {quick_sort(arr)}")  # [1, 1, 2, 3, 4, 5, 6, 9]
