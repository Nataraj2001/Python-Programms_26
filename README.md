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

## Count the Characters in String excluding spaces  -- String
    s = "Hello World Python"
    count = len(s.replace(" ", ""))
    print(f"Count (excluding spaces): {count}")  # 15
