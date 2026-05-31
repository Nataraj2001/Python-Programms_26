# Python-Programms_26
## 1. Reverse a String
  # Using reversed() + join
  reversed_s = "".join(reversed(s))
  reversed_s = ""
  for char in s:
    reversed_s = char + reversed_s
