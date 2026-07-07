# Python-Programms_26
## 1. Reverse a String -- String
    s = "Happy Coding"
    reversed_s = "".join(reversed(s))
    reversed_s = ""
    for char in s:
      reversed_s = char + reversed_s
    print(reversed_s)
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

## 20 .Quick Sort :- O(n log n) / O(n log n) / O(n²)
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

## 21. Heap Sort -- O(n log n) / O(n log n) / O(n log n)
    def heapify(arr, n, i):
        largest = i        # Root
        left    = 2 * i + 1  # Left Child
        right   = 2 * i + 2  # Right Child
         Check if left child is larger than root
        if left < n and arr[left] > arr[largest]:
            largest = left
         Check if right child is larger than largest
        if right < n and arr[right] > arr[largest]:
            largest = right
        If largest is not root, swap and heapify
        if largest != i:
            arr[i], arr[largest] = arr[largest], arr[i]
            heapify(arr, n, largest)
    def heap_sort(arr):
        n = len(arr)
        Build Max Heap
        for i in range(n // 2 - 1, -1, -1):
            heapify(arr, n, i)

        Extract elements from heap one by one
        for i in range(n - 1, 0, -1):
            arr[0], arr[i] = arr[i], arr[0]   
            heapify(arr, i, 0)                

    arr = [3, 1, 4, 1, 5, 9, 2, 6]
    heap_sort(arr)
    print(f"Sorted Array: {arr}")

## 22.Counting Sort -- O(n + k)
    Count occurrences of values
    # Counting Sort
    def counting_sort(arr):
        max_val = max(arr)          
        count   = [0] * (max_val + 1)  
        for num in arr:
            count[num] += 1
    # Reconstruct sorted array
        sorted_arr = []
        for i, c in enumerate(count):
            sorted_arr.extend([i] * c)

        return sorted_arr

    arr = [4, 2, 2, 8, 3, 3, 1]
    print(f"Original Array: {arr}")
    print(f"Sorted  Array : {counting_sort(arr)}")

## 23. Radix Sort -- O(nk)
    Radix Sort is a non-comparison sorting algorithm that sorts numbers digit by digit, starting from the least significant digit (LSD) to the most significant digit (MSD).
    # Radix Sort
    def counting_sort_radix(arr, exp):
        n      = len(arr)
        output = [0] * n
        count  = [0] * 10  
        # Count occurrences of digits
        for i in range(n):
            index = arr[i] // exp % 10
            count[index] += 1
        # Change count to actual positions
        for i in range(1, 10):
            count[i] += count[i - 1]
        # Build output array (traverse right to left for stability)
        for i in range(n - 1, -1, -1):
            index = arr[i] // exp % 10
            output[count[index] - 1] = arr[i]
            count[index]  -= 1
        # Copy output to arr
        for i in range(n):
            arr[i] = output[i]

    def radix_sort(arr):
        max_val = max(arr)        # Find maximum value
        exp     = 1               # Start from least significant digit
        while max_val // exp > 0:
            counting_sort_radix(arr, exp)
            exp *= 10             # Move to next digit

    arr = [170, 45, 75, 90, 802, 24, 2, 66]
    print(f"Original Array: {arr}")
    radix_sort(arr)
    print(f"Sorted  Array : {arr}")

## 24. Decimal to Binary Conversion and Count the 0's and 1's
     --> First Approch
    num = 29
    binary = bin(num)[2:]         # Convert to binary (remove '0b' prefix)
    zeros  = binary.count('0')    # Count 0s
    ones   = binary.count('1')    # Count 1s
    print(f"Number         : {num}")
    print(f"Binary         : {binary}")
    print(f"Count of 0s    : {zeros}")
    print(f"Count of 1s    : {ones}")

    --> Second Approch
    num    = 29
    binary = ""
    n      = num
    while n > 0:
        binary = str(n % 2) + binary
        n //= 2
    zeros  = binary.count('0')
    ones   = binary.count('1')
    print(f"Binary      : {binary}")
    print(f"Count of 0s : {zeros}")
    print(f"Count of 1s : {ones}")

## 25.Binary to Decimal Conversion
    --> 1st Approch
    binary = "11101"
    decimal = int(binary, 2)      # Convert binary to decimal
    print(f"Binary  : {binary}")
    print(f"Decimal : {decimal}")

    --> 2nd Approch
    binary  = "11101"
    decimal = 0
    power   = 0
    for bit in reversed(binary):
        decimal += int(bit) * (2 ** power)
        power   += 1
    print(f"Binary  : {binary}")
    print(f"Decimal : {decimal}")

## 26.Decimal to octal
    --> 1st Apprcoh
    num = 29
    octal = oct(num)[2:]          # Convert to octal (remove '0o' prefix)
    print(f"Decimal : {num}")
    print(f"Octal   : {octal}")
    
    --> 2nd Approch
    num   = 29
    octal = ""
    n     = num
    while n > 0:
        octal = str(n % 8) + octal
        n    //= 8
    print(f"Decimal : {num}")
    print(f"Octal   : {octal}")

## 27.Octal to decimal
    --> 1st Approch
    octal = "35"
    decimal = int(octal, 8)       # Convert octal to decimal
    print(f"Octal   : {octal}")
    print(f"Decimal : {decimal}")

    --> 2nd Approch
    octal   = "35"
    decimal = 0
    power   = 0
    for digit in reversed(octal):
        decimal += int(digit) * (8 ** power)
        power   += 1
    print(f"Octal   : {octal}")
    print(f"Decimal : {decimal}")

## 28.Decimal to Hexadecimal --
    --> 1st Approch
    num = 255
    hexadecimal = hex(num)[2:]    # Convert to hex (remove '0x' prefix)
    print(f"Decimal     : {num}")
    print(f"Hexadecimal : {hexadecimal}")

    --> 2nd Approch
    num         = 255
    hexadecimal = ""
    hex_chars   = "0123456789ABCDEF"
    n           = num
    while n > 0:
        hexadecimal = hex_chars[n % 16] + hexadecimal
        n          //= 16
    print(f"Decimal     : {num}")
    print(f"Hexadecimal : {hexadecimal}")

## 29.Hexadecimal to Decimal
    --> 1st Approch
    hexadecimal = "FF"
    decimal = int(hexadecimal, 16)  # Convert hex to decimal
    print(f"Hexadecimal : {hexadecimal}")
    print(f"Decimal     : {decimal}")

    --> 2nd Approch
    hexadecimal = "FF"
    hex_chars   = "0123456789ABCDEF"
    decimal     = 0
    for digit in hexadecimal.upper():
        decimal = decimal * 16 + hex_chars.index(digit)
    print(f"Hexadecimal : {hexadecimal}")
    print(f"Decimal     : {decimal}")

## 30. Binary to Octal
    # Binary to Octal
    binary = "11101"
    octal = oct(int(binary, 2))[2:]   # Convert binary to octal
    print(f"Binary : {binary}")
    print(f"Octal  : {octal}")

## 31. Octal to Binary
    # Octal to Binary
    octal = "35"
    binary = bin(int(octal, 8))[2:]   # Convert octal to binary
    print(f"Octal  : {octal}")
    print(f"Binary : {binary}")

## 32.Binart to Hexadecimal
    binary = "11101"
    hexadecimal = hex(int(binary, 2))[2:].upper()  # Convert binary to hex
    print(f"Binary      : {binary}")
    print(f"Hexadecimal : {hexadecimal}")
    
## 33.Hexa to Binary
    hexadecimal = "1D"
    binary = bin(int(hexadecimal, 16))[2:]   # Convert hex to binary
    print(f"Hexadecimal : {hexadecimal}")
    print(f"Binary      : {binary}")

## 34. Octal to Hexadecimal
    octal = "35"
    hexadecimal = hex(int(octal, 8))[2:].upper()  # Convert octal to hex
    print(f"Octal       : {octal}")
    print(f"Hexadecimal : {hexadecimal}")

## 35 . Hexadecimal to Octal
    hexadecimal = "1D"
    octal = oct(int(hexadecimal, 16))[2:]  # Convert hex to octal
    print(f"Hexadecimal : {hexadecimal}")
    print(f"Octal       : {octal}")

## 36. Removing the dublicate element in an array 
    arr = [3, 1, 4, 1, 5, 9, 2, 6, 5, 3]
    result = []
    for num in arr:
        if num not in result:
            result.append(num)
    print(f"Without Duplicates: {result}")  # [3, 1, 4, 5, 9, 2, 6]

## 37. Prime number Check
    import math
    num = 29
    def is_prime(n):
        if n <= 1:
            return False
    for i in range(2, int(math.sqrt(n)) + 1):
            if n % i == 0:
                return False
    return True

    print(f"{num} is {'a Prime' if is_prime(num) else 'Not a Prime'} Number")

    <--------------- 2nd Method ------------------------>
     a = int(input())
    b = int(input())
    for n in range(a , b + 1):
        if n < 2:
            continue
    
    for i in range(2, int(n ** 0.5) + 1):
        if n % i == 0:
            break
    else:
        print(n, end = " ")

    

## 38. Fibonacci 
    <--- 1st Method ------->
    def fibonacci(n):
        if n <= 0:
            return 0
        if n == 1:
            return 1
        return fibonacci(n - 1) + fibonacci(n - 2)

    for i in range(10):
        print(fibonacci(i), end=" ")   # 0 1 1 2 3 5 8 13 21 34 ---- OR---

        <------ 2nd Method ----->

        n = int(input("Enter value : ")
        a = 0
        b = 1
        for i in range(n):
            print(a)
            c = a + b
            a = b
            b = c

        

## 39.Check the Even and Odd number -- array
    arr = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    for num in arr:
        print(f"{num} is {'Even' if num % 2 == 0 else 'Odd'}")

    <---- 2nd Method ------>

    count  = 0 
    i = 1
    while count < 25:
    if i % 2 != 0:
        print(i)
        count += 1
    i += 1

## 40. Linear Serach -- O(1) - O(n)
    def linear_search(arr, target):
        for i in range(len(arr)):
            if arr[i] == target:
                return i       # Return index if found
        return -1              # Return -1 if not found
    arr    = [3, 1, 4, 1, 5, 9, 2, 6]
    target = 5
    result = linear_search(arr, target)
    if result != -1:
        print(f"Array   : {arr}")
        print(f"Target  : {target}")
        print(f"Found at index : {result}")
    else:
        print(f"Target {target} not found in array")

## 41.Binary Search -- O(1) -- O(log n)
    def binary_search(arr, target):
        left  = 0
        right = len(arr) - 1

        while left <= right:
            mid = (left + right) // 2     # Find middle index
            if arr[mid] == target:
                return mid                 # Target found
            elif arr[mid] < target:
                left = mid + 1             # Search right half
            else:
                right = mid - 1            # Search left half

        return -1                          # Target not found

    arr    = [1, 2, 3, 4, 5, 6, 7, 8, 9]
    target = 5

    result = binary_search(arr, target)

    if result != -1:
        print(f"Array          : {arr}")
        print(f"Target         : {target}")
        print(f"Found at index : {result}")
    else:
        print(f"Target {target} not found in array")

## 42.Pattern Matching -- Right angle Triangle
    n = 5
    for i in range(1, n + 1):
        print("* " * i)

## 43. Inverted Right angle Triangle
    n = 5
    for i in range(n, 0, -1):
        print("* " * i)

## 44. Right angle Triangle (Numbers)
    n = 5
    for i in range(1, n + 1):
    for j in range(1, i + 1):
        print(j, end = " ")
    print()

## 45. Right angle Triangle(Same numbers)
    n = 5
    for i in range(1, n + 1):
        print((str(i) + " ") * i)

## 46. Pyramid 
    n = 5
    for i in range(1, n + 1):
        print( " " * ( n - i) + " * " * i)

## 47. Inverted Pyramid
    n = 5
    for i in range(n, 0, -1):
        print(" " * (n - i) + "* " * i)

## 48.Diamond
    n = 5
    for i in range(1, n + 1):
        print(" " * (n - i) + "* " * i)
    for i in range(n - 1, 0, -1):
        print(" " * (n - i) + "* " * i)

## 49.Hollow Square
    n = 5
    for i in range(n):
        for j in range(n):
            if i == 0 or i == n-1 or j == 0 or j == n-1:
                print("*", end=" ")
            else:
                print(" ", end=" ")
       print()

## 50.Hollow Square
    n = 5
    for i in range(1, n + 1):
        for j in range(1, i + 1):
            if j == 1 or j == i or i == n:
                print("*", end=" ")
            else:
                print(" ", end=" ")
        print()

## 51. Floyd's Triangle
    n = 5
    num = 1
    for i in range(1, n + 1):
        for j in range(i):
            print(num, end=" ")
            num += 1
    print()

## 52. ButterFly 
    n = 5
    for i in range(1, n + 1):
        print("* " * i + "  " * (n - i) * 2 + "* " * i)
    for i in range(n, 0, -1):
        print("* " * i + "  " * (n - i) * 2 + "* " * i)

## 53. Invreted Right aligned triangle in Numbers
    n = 5
    for i in range(n, 0, -1):
        for j in range(1, i + 1):
            print(j, end=" ")
    print()

## 54. Count and Print all voewls!
    text = input("Enter a text: ")
    vowels = "aeiouAEIOU"
    count = 0
    for i in text:
        if i in vowels:
            count = count + 1
    print(count)

## 55. Reverse the words of a given string
    text = "how are you"
    result = " "
    words = text.split()
    words.reverse()
    result = result.join(words)
    print(result)

## 56. Length of a string without using len()
    text = input("Enter a String: ")
    count = 0
    for i in text:
        count = count + 1
    print("Length of the String:", count)

## 57. Check the list ascending without using Built in Method
    numbers = [12,13,14]
    is_ascending = True
    for i in range(len(numbers) -1 ):
        if numbers[i] > numbers[i + 1]:
            is_ascending = False
            break
    if is_ascending:
        print("List is Ascending order")
    else:
        print("List is not ascending order")

## 58. Create a list containing the squares of all elements in the given list
    L1 = [2,3,4,5]
    L2 = []
    for i in L1:
        sq = i ** 2
        L2.append(sq)
    
    print(L2)

## 59. Search a Given number
    numbers = [12, 13,11,212,34]
    target = int(input("Enter a number to search: "))
    for i in numbers:
        if i  == target:
            print("Number Found")
            print("Number found index at", numbers.index(target))
        break
    
    else:
        print("Number not found")

## 60. Convert a String to title case without using title()
    text = input("Enter a String: ")
    words = text.split()
    result = ""
    for word in words:
        result = result + word[0].upper()  + word[1:].lower()
    print(result)

## 61. Calculate sum and average until user enters 0
    total = 0
    count = 0
    while True:
        num = int(input("Enter a number: "))
    
        if num == 0:
            break
    
        total = total + num
        count = count + 1
    
    average = total / count
    
    print("Sum:", total)
    print("Average:", average)

## 62. Remove the a Particular character from a String
    text = input("Enter a String: ")
    char = input("Enter the character to remove:")
    result = ""
    for i in text:
        if i != char:
            result = result + i
    print("Updated string:", result) 

## 63. Print all the unique combinations of 1,2,3 and 4 -- Nested loop
    num = [1,2,3,4]
    for i in num:
        for j in num:
            if i != j:
                print(i,j)f

## 64. Index postion of a particular character
    text = input("Enter a String: ")
    char = input("Enter a character:")
    for i in range(len(text)):
        if text[i] == char:
            print(f"character found at index : {i}")
            break
    else:
        print("Character not Found")

## 65. Extract Username from a given email
    email = input("Enter a Email id: ")
    username = ""
    for i in email:
        if i == '@':
            break
        username = username + i
    print("Username:", username)

## 66. Writa a Program to print the Triangle pattern -- In nunbers
    n = 1
    for i in range(1, 5):
        for j in range(i):
            print(n, end = " ")
            n = n + 1
        
        print()

## 67. Write a program to print the following pattern
    n = 5
    for i in range(1, n + 1):
        for j in range(1, i + 1):
            print(j, end = " ") 
        for j in range(i - 1, 0, -1):
            print(j, end = " ")
        print()

## 68. Triangle pattern
    n = 5
    for i in range(1, n + 1):
        print(" " * (n - i), end = "")
        print("* " * (2 * i - 1))

## 69. Greatest Commom Divisor of two numbers
    a = int(input())
    b = int(input())
    while b != 0:
        a, b = b, a % b
    print(a)

## 70. Print all the armstrong number within a given range
    a = int(input())
    b = int(input())
    for num in range(a, b + 1):
        num_str = str(num)
        n = len(num_str)
        result = 0
        for digit_char in num_str:
            digit = int(digit_char)
            result = result + digit ** n
        
        if result == num:
            print(num)

## 71. Reminder and Floor divison 
    1. Keep only last element in the given number
    n = 123
    b = n % 10 
    print(b) ---> Ouput ---> 3

    2. Eliminate the last element and keep remaining element
    n = 123 
    b = n // 10
    print(b) ---O/P ----> 12

    3. Add the number without using built in method
    n = 32
    a = 32 * 10 + 1
    b = a * 10 + 0
    c = b * 10 + 1
    print(a) ---> 321
    print(b) ---> 3210
    print(c) ---> 32101

## 72. WAP that can multiply 2 numbers proided by the User without using * operator
    import math
    a = int(input("Enter a Number: "))
    b = int(input("Enter a Number: "))
    multiply = math.prod([a,b])
    print(multiply)

## 73. WAP that will reverse a Four digit number & also it checks whether the reverse it true.
    num = input("Enter a valid digit: ")
    if len(num) == 4 and num.isdigit():
        reversed = (num[::-1])
        print(reversed)
    else:
        print("Please enter valid digit")
    
    if reversed ==(num[::-1]):
        print("Yes, Reverse is True")

## 74. Write a program to convert celsius value to Fahrenheit
    cel_temp = int(input("Enter a Value: "))
    fahren_temp = 1.8*(cel_temp)
    result = fahren_temp + 32
    print("fahrenheit temp is :", result)

## 75. WAP to check the Year is a leap year or not
   year = int(input("Enter the Year: "))
    def leap_year(year):
        if year % 4 == 0 and year % 100 != 0 or year % 400 == 0:
            return True
        else:
            return False       
    if leap_year(year):
        print("Leap Year")   
    else:
        print("Not a Leap Year")
        
