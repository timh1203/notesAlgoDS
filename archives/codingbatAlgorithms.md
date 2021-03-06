# Coding Bat
- https://codingbat.com/python

---

## Warmup-1 sleep_in
- https://codingbat.com/prob/p173401
```py
# The parameter weekday is True if it is a weekday, and the parameter vacation is True if we are on vacation. We sleep in if it is not a weekday or we're on vacation. Return True if we sleep in.
# sleep_in(False, False) → True
# sleep_in(True, False) → False
# sleep_in(False, True) → True
# sleep_in(True, True) → True

def sleep_in(weekday, vacation):
  if weekday == False and vacation == False: return True
  
  elif weekday == True and vacation == False: return False
  
  elif weekday == False and vacation == True: return True
  
  else: return True
```

---

## Warmup-1 monkey_trouble
- https://codingbat.com/prob/p120546
```py
# We have two monkeys, a and b, and the parameters a_smile and b_smile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return True if we are in trouble.
# monkey_trouble(True, True) → True
# monkey_trouble(False, False) → True
# monkey_trouble(True, False) → False
# monkey_trouble(False, True) → False

def monkey_trouble(a_smile, b_smile):
  if a_smile == True and b_smile == True: return True
  
  elif a_smile == False and b_smile == True: return False
  
  elif a_smile == True and b_smile == False: return False
  
  else: return True
```

---

## Warmup-1 sum_double
- https://codingbat.com/prob/p141905
```py
# Given two int values, return their sum. Unless the two values are the same, then return double their sum.
# sum_double(1, 2) → 3
# sum_double(3, 2) → 5
# sum_double(2, 2) → 8

def sum_double(a, b):
  if (a == b):
    return 2 * (a + b)
  else:
    return a + b
```

---

## Warmup-1 diff21
- https://codingbat.com/prob/p197466
```py
# Given an int n, return the absolute difference between n and 21, except return double the absolute difference if n is over 21.
# diff21(19) → 2
# diff21(10) → 11
# diff21(21) → 0

def diff21(n):
  if n <= 21:
    return 21-n
  else:
    return (n-21) * 2
```

---

## Warmup-1 parrot_trouble
- https://codingbat.com/prob/p166884
```py
# We have a loud talking parrot. The "hour" parameter is the current hour time in the range 0..23. We are in trouble if the parrot is talking and the hour is before 7 or after 20. Return True if we are in trouble.
# parrot_trouble(True, 6) → True
# parrot_trouble(True, 7) → False
# parrot_trouble(False, 6) → False

def parrot_trouble(talking, hour):
  if talking and hour < 7:
    return True
  elif talking and hour > 20:
    return True
  else:
    return False

# ALTERNATE
# Need extra parenthesis around the or clause
# since and binds more tightly than or.
# and is like arithmetic *, or is like arithmetic +
def parrot_trouble(talking, hour):
  return (talking and (hour < 7 or hour > 20))
```

---

## Warmup1 makes10
- https://codingbat.com/prob/p124984
```py
# Given 2 ints, a and b, return True if one if them is 10 or if their sum is 10.
# makes10(9, 10) → True
# makes10(9, 9) → False
# makes10(1, 9) → True

def makes10(a, b):
  if a == 10 or b == 10:
    return True
  elif a + b == 10:
    return True
  else:
    return False
```

---

## Warmup1 near_hundred
- https://codingbat.com/prob/p124676
```py
# Given an int n, return True if it is within 10 of 100 or 200. Note: abs(num) computes the absolute value of a number.
# near_hundred(93) → True
# near_hundred(90) → True
# near_hundred(89) → False
def near_hundred(n):
  if 89 < n < 111 or 189 < n < 211:
    return True
  else:
    return False

# ALTERNATE
def near_hundred(n):
  return (abs(100-n) <= 10) or (abs(200-n) <= 10)
```

---

## Warmup1 pos_neg
- https://codingbat.com/prob/p162058
```py
# Given 2 int values, return True if one is negative and one is positive. Except if the parameter "negative" is True, then return True only if both are negative.
# pos_neg(1, -1, False) → True
# pos_neg(-1, 1, False) → True
# pos_neg(-4, -5, True) → True
def pos_neg(a, b, negative):
  if negative:
    return (a<0 and b<0)
  else:
    return (a<0 and b>0) or (a>0 and b<0)
```

---

## Warmup1 not_string
- https://codingbat.com/prob/p189441
```py
# Given a string, return a new string where "not " has been added to the front. However, if the string already begins with "not", return the string unchanged.
# not_string('candy') → 'not candy'
# not_string('x') → 'not x'
# not_string('not bad') → 'not bad'
def not_string(str):
	if str.startswith("not"):
		return str
	else:
		return "not " + str

# ALTERNATE
def not_string(str):
  if len(str) >= 3 and str[:3] == "not":
    return str
  return "not " + str
  # str[:3] goes from the start of the string up to but not
  # including index 3
```

---

## Warmup1 missing_char
- https://codingbat.com/prob/p149524
```py
# Given a non-empty string and an int n, return a new string where the char at index n has been removed. The value of n will be a valid index of a char in the original string (i.e. n will be in the range 0..len(str)-1 inclusive).
# missing_char('kitten', 1) → 'ktten'
# missing_char('kitten', 0) → 'itten'
# missing_char('kitten', 4) → 'kittn'
def missing_char(str, n):w
	return str[0:n] + str[n+1:]

# ALTERNATE
def missing_char(str, n):
  front = str[:n]   # up to but not including n
  back = str[n+1:]  # n+1 through end of string
  return front + back
```

---

## Warmup1 front_back
- https://codingbat.com/prob/p153599
```py
# Given a string, return a new string where the first and last chars have been exchanged.
# front_back('code') → 'eodc'
# front_back('a') → 'a'
# front_back('ab') → 'ba'
def front_back(str):
  if len(str) <= 1:
    return str
  elif len(str) == 2:
    return (str[len(str)-1] + str[0])
  else:
	  return (str[len(str)-1] + str[1:len(str)-1] + str[0])

# ALTERNATE
def front_back(str):
  if len(str) <= 1:
    return str
  
  mid = str[1:len(str)-1]  # can be written as str[1:-1]
  
  # last + mid + first
  return str[len(str)-1] + mid + str[0]
```

---

## Warmup1 front3
- https://codingbat.com/prob/p147920
```py
# Given a string, we'll say that the front is the first 3 chars of the string. If the string length is less than 3, the front is whatever is there. Return a new string which is 3 copies of the front.
# front3('Java') → 'JavJavJav'
# front3('Chocolate') → 'ChoChoCho'
# front3('abc') → 'abcabcabc'
def front3(str):
  if len(str) < 3:
    return (str * 3) 
  else:
    return (str[:3] * 3)

# ALTERNATE
def front3(str):
  # Figure the end of the front
  front_end = 3
  if len(str) < front_end:
    front_end = len(str)
  front = str[:front_end]
  return front + front + front 
  
  # Could omit the if logic, and write simply front = str[:3]
  # since the slice is silent about out-of-bounds conditions.
```

---

## Warmup2 string_times
- https://codingbat.com/prob/p193507
```py
# Given a string and a non-negative int n, return a larger string that is n copies of the original string.
# string_times('Hi', 2) → 'HiHi'
# string_times('Hi', 3) → 'HiHiHi'
# string_times('Hi', 1) → 'Hi'
def string_times(str, n):
  return str * n;

# ALTERNATE
def string_times(str, n):
  result = ""
  for i in range(n):  # range(n) is [0, 1, 2, .... n-1]
    result = result + str  # could use += here
  return result
```

---

## Warmup2 front_times
- https://codingbat.com/prob/p165097
```py
# Given a string and a non-negative int n, we'll say that the front of the string is the first 3 chars, or whatever is there if the string is less than length 3. Return n copies of the front;
# front_times('Chocolate', 2) → 'ChoCho'
# front_times('Chocolate', 3) → 'ChoChoCho'
# front_times('Abc', 3) → 'AbcAbcAbc'
def front_times(str, n):
  return str[:3]*n

# ALTERNATE
def front_times(str, n):
  front_len = 3
  if front_len > len(str):
    front_len = len(str)
  front = str[:front_len]
  
  result = ""
  for i in range(n):
    result = result + front
  return result
```

---

## Warmup2 string_bits
- https://codingbat.com/prob/p113152
```py
# Given a string, return a new string made of every other char starting with the first, so "Hello" yields "Hlo".
# string_bits('Hello') → 'Hlo'
# string_bits('Hi') → 'H'
# string_bits('Heeololeo') → 'Hello'
def string_bits(str):
  result = ""
  if len(str) < 1:
    return ''
  elif len(str) < 3:
    result = str[0]
  else:
    for i in range(len(str)):
      if i % 2 == 0:
        result += str[i]
      else:
        continue
  return result

# ALTERNATE
def string_bits(str):
  result = ""
  # Many ways to do this. This uses the standard loop of i on every char,
  # and inside the loop skips the odd index values.
  for i in range(len(str)):
    if i % 2 == 0:
      result = result + str[i]
  return result
```

---

## Warmup2 string_splosion (4/15/19)
- https://codingbat.com/prob/p118366
```py
# Given a non-empty string like "Code" return a string like "CCoCodCode".
# string_splosion('Code') → 'CCoCodCode'
# string_splosion('abc') → 'aababc'
# string_splosion('ab') → 'aab'
def string_splosion(str):
	result = ""
	for i in range(len(str)):
		result += str[0:i+1]
	return result
```

---

## Warmup2 last2 (4/15/19)
- https://codingbat.com/prob/p145834
```py
# Given a string, return the count of the number of times that a substring length 2 appears in the string and also as the last 2 chars of the string, so "hixxxhi" yields 1 (we won't count the end substring).
# last2('hixxhi') → 1
# last2('xaxxaxaxx') → 1
# last2('axxxaaxx') → 2
def last2(str):
	count = 0
	lastTwo = str[-2:]

	if len(str) < 2:
		return 0

	for i in range(len(str)-2):
		sub = str[i:i+2]
		if sub == lastTwo:
			count += 1
	return count


print(last2('hixxhi')) # 1
print(last2('xxaxxaxxaxx')) # 3
```

---

## Warmup2 array_count9 (4/15/19)
- https://codingbat.com/prob/p166170
```py
# Given an array of ints, return the number of 9's in the array.
# array_count9([1, 2, 9]) → 1
# array_count9([1, 9, 9]) → 2
# array_count9([1, 9, 9, 3, 9]) → 3
def array_count9(nums):
	count = 0
	for i in nums:
		if i == 9:
			count += 1
	return count

print(array_count9([1,9,9,3,9]))
```

---

## Warmup2 array_front9 (4/15/19)
- https://codingbat.com/prob/p110166
```py
# Given an array of ints, return True if one of the first 4 elements in the array is a 9. The array length may be less than 4.
# array_front9([1, 2, 9, 3, 4]) → True
# array_front9([1, 2, 3, 4, 9]) → False
# array_front9([1, 2, 3, 4, 5]) → False
def array_front9(nums):
	for i in nums[:4]:
		if i == 9:
			return True
	
	return False

print(array_front9([1,2,9,3,4]))
```

---

## Warmup2 array123 (4/15/19)
- https://codingbat.com/prob/p193604
```py
# Given an array of ints, return True if the sequence of numbers 1, 2, 3 appears in the array somewhere.
# array123([1, 1, 2, 3, 1]) → True
# array123([1, 1, 2, 4, 1]) → False
# array123([1, 1, 2, 1, 2, 3]) → True
def array123(nums):
	for i in range(len(nums)-2):
		if nums[i] == 1 and nums[i+1] == 2 and nums[i+2] == 3:
			return True
	return False

print(array123([1,1,2,3,1]))
```

---

## Warmup2 string_match
- https://codingbat.com/prob/p182414
```py
# Given 2 strings, a and b, return the number of the positions where they contain the same length 2 substring. So "xxcaazz" and "xxbaaz" yields 3, since the "xx", "aa", and "az" substrings appear in the same place in both strings.
# string_match('xxcaazz', 'xxbaaz') → 3
# string_match('abc', 'abc') → 2
# string_match('abc', 'axc') → 0
def string_match(a, b):
	matches = 0
	for i in range(len(a)-1):
		if a[i:i+2] == b[i:i+2]:
			matches += 1
	return matches

print(string_match('xxcaazz', 'xxbaaz'))
```

---

## String1 hello_name (4/16/19)
- https://codingbat.com/prob/p115413
```py
# Given a string name, e.g. "Bob", return a greeting of the form "Hello Bob!".
# hello_name('Bob') → 'Hello Bob!'
# hello_name('Alice') → 'Hello Alice!'
# hello_name('X') → 'Hello X!'
def hello_name(name):
  return 'Hello ' + name + '!'
```

---

## String1 make_abba (4/16/19)
- https://codingbat.com/prob/p182144
```py
# Given two strings, a and b, return the result of putting them together in the order abba, e.g. "Hi" and "Bye" returns "HiByeByeHi".
# make_abba('Hi', 'Bye') → 'HiByeByeHi'
# make_abba('Yo', 'Alice') → 'YoAliceAliceYo'
# make_abba('What', 'Up') → 'WhatUpUpWhat'
def make_abba(a, b):
  return a + b + b + a
```

---

## String1 make_tags (4/16/19)
- https://codingbat.com/prob/p132290
```py
# The web is built with HTML strings like "<i>Yay</i>" which draws Yay as italic text. In this example, the "i" tag makes <i> and </i> which surround the word "Yay". Given tag and word strings, create the HTML string with tags around the word, e.g. "<i>Yay</i>".
# make_tags('i', 'Yay') → '<i>Yay</i>'
# make_tags('i', 'Hello') → '<i>Hello</i>'
# make_tags('cite', 'Yay') → '<cite>Yay</cite>'
def make_tags(tag, word):
  return '<' + tag + '>' + word + '</' + tag + '>'
```

---

## String1 make_out_word (4/16/19)
- https://codingbat.com/prob/p129981
```py
# Given an "out" string length 4, such as "<<>>", and a word, return a new string where the word is in the middle of the out string, e.g. "<<word>>".
# make_out_word('<<>>', 'Yay') → '<<Yay>>'
# make_out_word('<<>>', 'WooHoo') → '<<WooHoo>>'
# make_out_word('[[]]', 'word') → '[[word]]'
def make_out_word(out, word):
  return out[:2] + word + out[-2:]
```

---

## String1 extra_end (4/16/19)
- https://codingbat.com/prob/p148853
```py
# Given a string, return a new string made of 3 copies of the last 2 chars of the original string. The string length will be at least 2.
# extra_end('Hello') → 'lololo'
# extra_end('ab') → 'ababab'
# extra_end('Hi') → 'HiHiHi'
def extra_end(str):
  return str[-2:] * 3

# ALTERNATE
def extra_end(str):
  end = str[-2:]
  return end + end + end
```

---

## String1 first_two (4/16/19)
- https://codingbat.com/prob/p184816
```py
# Given a string, return the string made of its first two chars, so the String "Hello" yields "He". If the string is shorter than length 2, return whatever there is, so "X" yields "X", and the empty string "" yields the empty string "".
# first_two('Hello') → 'He'
# first_two('abcdefg') → 'ab'
# first_two('ab') → 'ab'
def first_two(str):
  if len(str) <= 2:
    return str
  return str[:2]

# ALTERNATE
def first_two(str):
  if len(str) >= 2:
    return str[:2]
  else:
    return str
```

---

## String1 first_half (4/16/19)
- https://codingbat.com/prob/p107010
```py
# Given a string of even length, return the first half. So the string "WooHoo" yields "Woo".
# first_half('WooHoo') → 'Woo'
# first_half('HelloThere') → 'Hello'
# first_half('abcdef') → 'abc'
def first_half(str):
  half = len(str)/2
  return str[:half]

# ALTERNATE
```

---

## String1 without_end (4/16/19)
- https://codingbat.com/prob/p138533
```py
# Given a string, return a version without the first and last char, so "Hello" yields "ell". The string length will be at least 2.
# without_end('Hello') → 'ell'
# without_end('java') → 'av'
# without_end('coding') → 'odin'
def without_end(str):
  return str[1:-1]
```

---

## String1 combo_string (4/16/19)
- https://codingbat.com/prob/p194053
```py
# Given 2 strings, a and b, return a string of the form short+long+short, with the shorter string on the outside and the longer string on the inside. The strings will not be the same length, but they may be empty (length 0).
# combo_string('Hello', 'hi') → 'hiHellohi'
# combo_string('hi', 'Hello') → 'hiHellohi'
# combo_string('aaa', 'b') → 'baaab'
def combo_string(a, b):
  if len(a) < len(b):
    return a + b + a
  return b + a + b

```

---

## String1 non_start (4/16/19)
- https://codingbat.com/prob/p127703
```py
# Given 2 strings, return their concatenation, except omit the first char of each. The strings will be at least length 1.
# non_start('Hello', 'There') → 'ellohere'
# non_start('java', 'code') → 'avaode'
# non_start('shotl', 'java') → 'hotlava'
def non_start(a, b):
  return a[1:] + b[1:]
```

---

## String1 left2
- https://codingbat.com/prob/160545
```py
# Given a string, return a "rotated left 2" version where the first 2 chars are moved to the end. The string length will be at least 2.
# left2('Hello') → 'lloHe'
# left2('java') → 'vaja'
# left2('Hi') → 'Hi'
def left2(str):
  if len(str) == 2:
    return str
  return str[2:] + str[:2]

# ALTERNATE
def left2(str):
  return str[2:] + str[:2]
```

---

## List1 first_last6 (4/17/19)
- https://codingbat.com/prob/p181624
```py
# Given an array of ints, return True if 6 appears as either the first or last element in the array. The array will be length 1 or more.
# first_last6([1, 2, 6]) → True
# first_last6([6, 1, 2, 3]) → True
# first_last6([13, 6, 1, 2, 3]) → False
def first_last6(nums):
	if nums[0] == 6 or nums[-1] == 6:
		return True
	return False

print(first_last6([1,2,6]))

# ALTERNATE
def first_last6(nums):
  return (nums[0]==6 or nums[-1]== 6)
```

---

## List1 same_first_last (4/17/19)
- https://codingbat.com/prob/p179078
```py
# Given an array of ints, return True if the array is length 1 or more, and the first element and the last element are equal.
# same_first_last([1, 2, 3]) → False
# same_first_last([1, 2, 3, 1]) → True
# same_first_last([1, 2, 1]) → True
def same_first_last(nums):
	return len(nums) > 0 and nums[0] == nums[-1]

same_first_last([1,2,1])
```

---

## List1 make_pi (4/17/19)
- https://codingbat.com/prob/p113659
```py
# Return an int array length 3 containing the first 3 digits of pi, {3, 1, 4}.
# make_pi() → [3, 1, 4]
def make_pi():
  return [3,1,4]
```

---

## List1 common_end (4/17/19)
- https://codingbat.com/prob/p147755
```py
# Given 2 arrays of ints, a and b, return True if they have the same first element or they have the same last element. Both arrays will be length 1 or more.
# common_end([1, 2, 3], [7, 3]) → True
# common_end([1, 2, 3], [7, 3, 2]) → False
# common_end([1, 2, 3], [1, 3]) → True
def common_end(a, b):
  sameFirst = a[0] == b[0]
  sameLast = a[-1] == b[-1]
  return sameFirst or sameLast
```

---

## List1 sum3 (4/17/19)
- https://codingbat.com/prob/p191645
```py
# Given an array of ints length 3, return the sum of all the elements.
# sum3([1, 2, 3]) → 6
# sum3([5, 11, 2]) → 18
# sum3([7, 0, 0]) → 7
def sum3(nums):
  return nums[0] + nums[1] + nums[2]
```

---

## List1 rotate_left3 (4/17/19)
- https://codingbat.com/prob/p148661
```py
# Given an array of ints length 3, return an array with the elements "rotated left" so {1, 2, 3} yields {2, 3, 1}.
# rotate_left3([1, 2, 3]) → [2, 3, 1]
# rotate_left3([5, 11, 9]) → [11, 9, 5]
# rotate_left3([7, 0, 0]) → [0, 0, 7]
def rotate_left3(nums):
  return nums[1:] + [nums[0]]
```

---

## List1 reverse3 (4/17/19)
- https://codingbat.com/prob/p192962
```py
# Given an array of ints length 3, return a new array with the elements in reverse order, so {1, 2, 3} becomes {3, 2, 1}.
# reverse3([1, 2, 3]) → [3, 2, 1]
# reverse3([5, 11, 9]) → [9, 11, 5]
# reverse3([7, 0, 0]) → [0, 0, 7]
def reverse3(nums):
  return [nums[2], nums[1], nums[0]]
```

---

## List1 max_end3 (4/17/19)
- https://codingbat.com/prob/p135290
```py
# Given an array of ints length 3, figure out which is larger, the first or last element in the array, and set all the other elements to be that value. Return the changed array.
# max_end3([1, 2, 3]) → [3, 3, 3]
# max_end3([11, 5, 9]) → [11, 11, 11]
# max_end3([2, 11, 3]) → [3, 3, 3]
def max_end3(nums):
  max = nums[0]
  if max < nums[-1]:
    max = nums[-1]
  return [max, max, max]

# ALTERNATIVE
def max_end3(nums):
  big = max(nums[0], nums[2])
  nums[0] = big
  nums[1] = big
  nums[2] = big
  return nums
```

---

## List1 sums2(4/17/19)
- https://codingbat.com/prob/p192589
```py
# Given an array of ints, return the sum of the first 2 elements in the array. If the array length is less than 2, just sum up the elements that exist, returning 0 if the array is length 0.
# sum2([1, 2, 3]) → 3
# sum2([1, 1]) → 2
# sum2([1, 1, 1, 1]) → 2
def sum2(nums):
  if len(nums) < 1:
    return 0
  elif len(nums) < 2:
    return nums[0]
  else:
    return nums[0] + nums[1]
```

---

## List1 middle_way(4/17/19)
- https://codingbat.com/prob/p171011
```py
# Given 2 int arrays, a and b, each length 3, return a new array length 2 containing their middle elements.
# middle_way([1, 2, 3], [4, 5, 6]) → [2, 5]
# middle_way([7, 7, 7], [3, 8, 0]) → [7, 8]
# middle_way([5, 2, 9], [1, 4, 5]) → [2, 4]
def middle_way(a, b):
  return [a[1], b[1]]
```

---

## List1 make_ends (4/17/19)
- https://codingbat.com/prob/p124806
```py
# Given an array of ints, return a new array length 2 containing the first and last elements from the original array. The original array will be length 1 or more.
# make_ends([1, 2, 3]) → [1, 3]
# make_ends([1, 2, 3, 4]) → [1, 4]
# make_ends([7, 4, 6, 2]) → [7, 2]
def make_ends(nums):
  if len(nums) == 1:
    return [nums[0], nums[0]]
  return [nums[0], nums[-1]]
```

---

## List1 has23 (4/17/19)
- https://codingbat.com/prob/p177892
```py
# Given an int array length 2, return True if it contains a 2 or a 3.
# has23([2, 5]) → True
# has23([4, 3]) → True
# has23([4, 5]) → False
def has23(nums):
  if 2 in nums or 3 in nums:
    return True
  return False
```

---

## Logic1 cigar_party (4/18/19)
- https://codingbat.com/prob/p195669
```py
# When squirrels get together for a party, they like to have cigars. A squirrel party is successful when the number of cigars is between 40 and 60, inclusive. Unless it is the weekend, in which case there is no upper bound on the number of cigars. Return True if the party with the given values is successful, or False otherwise.
# cigar_party(30, False) → False
# cigar_party(50, False) → True
# cigar_party(70, True) → True
def cigar_party(cigars, is_weekend):
  if is_weekend and cigars>=40:
    return True
  elif not is_weekend and 40<=cigars<=60:
    return True
  else:
    return False

# ALTERNATE
def cigar_party(cigars, is_weekend):
  if is_weekend:
    return (cigars >= 40)
  else:
    return (cigars >= 40 and cigars <= 60)
```

---

## Logic1 date_fashion (4/18/19)
- https://codingbat.com/prob/p129125
```py
# You and your date are trying to get a table at a restaurant. The parameter "you" is the stylishness of your clothes, in the range 0..10, and "date" is the stylishness of your date's clothes. The result getting the table is encoded as an int value with 0=no, 1=maybe, 2=yes. If either of you is very stylish, 8 or more, then the result is 2 (yes). With the exception that if either of you has style of 2 or less, then the result is 0 (no). Otherwise the result is 1 (maybe).
# date_fashion(5, 10) → 2
# date_fashion(5, 2) → 0
# date_fashion(5, 5) → 1
def date_fashion(you, date):
  if you <= 2 or date <= 2:
    return 0
  elif you >= 8 or date >= 8:
    return 2
  return 1
  

# ALTERNATE
def date_fashion(you, date):
  ## Check the <=2 case first, since it takes precedence
  ## over the >=8 case.
  if (you <= 2) or (date <= 2):
    return 0
  elif (you >= 8) or (date >= 8):
    return 2
  else:
    return 1
```

---

## Logic1 squirrel_play (4/18/19)
- https://codingbat.com/prob/p135815
```py
# The squirrels in Palo Alto spend most of the day playing. In particular, they play if the temperature is between 60 and 90 (inclusive). Unless it is summer, then the upper limit is 100 instead of 90. Given an int temperature and a boolean is_summer, return True if the squirrels play and False otherwise.
# squirrel_play(70, False) → True
# squirrel_play(95, False) → False
# squirrel_play(95, True) → True
def squirrel_play(temp, is_summer):
  if is_summer:
    return 60 <= temp <= 100
  elif not is_summer:
    return 60 <= temp <= 90
  else:
    return False
```

---

## Logic1 caught_speeding (4/18/19)
- https://codingbat.com/prob/p137202
```py
# You are driving a little too fast, and a police officer stops you. Write code to compute the result, encoded as an int value: 0=no ticket, 1=small ticket, 2=big ticket. If speed is 60 or less, the result is 0. If speed is between 61 and 80 inclusive, the result is 1. If speed is 81 or more, the result is 2. Unless it is your birthday -- on that day, your speed can be 5 higher in all cases.
# caught_speeding(60, False) → 0
# caught_speeding(65, False) → 1
# caught_speeding(65, True) → 0
def caught_speeding(speed, is_birthday):
  if is_birthday:
    if speed >= 86:
      return 2
    elif 66 <= speed <= 85:
      return 1
    else:
      return 0
  elif not is_birthday:
    if speed >= 81:
      return 2
    elif 61 <= speed <= 80:
      return 1
    else:
      return 0
```

---

## Logic1 sorta_num (4/18/19)
- https://codingbat.com/prob/p116620
```py
# Given 2 ints, a and b, return their sum. However, sums in the range 10..19 inclusive, are forbidden, so in that case just return 20.
# sorta_sum(3, 4) → 7
# sorta_sum(9, 4) → 20
# sorta_sum(10, 11) → 21
def sorta_sum(a, b):
  if 10 <= a+b <= 19:
    return 20
  return a+b

# ALTERNATE
def sorta_sum(a, b):
  sum = a + b
  if sum >= 10 and sum <= 19:
    return 20
  return sum
```

---

## Logic1 alarm_clock (4/18/19)
- https://codingbat.com/prob/p119867
```py
# Given a day of the week encoded as 0=Sun, 1=Mon, 2=Tue, ...6=Sat, and a boolean indicating if we are on vacation, return a string of the form "7:00" indicating when the alarm clock should ring. Weekdays, the alarm should be "7:00" and on the weekend it should be "10:00". Unless we are on vacation -- then on weekdays it should be "10:00" and weekends it should be "off".
# alarm_clock(1, False) → '7:00'
# alarm_clock(5, False) → '7:00'
# alarm_clock(0, False) → '10:00'
def alarm_clock(day, vacation):
  if vacation:
    if 1 <= day <= 5:
      return "10:00"
    elif day == 6 or day == 0:
      return "off"
  else:
    if 1 <= day <= 5:
      return "7:00"
    elif day == 6 or day == 0:
      return "10:00"
```

---

## Logic1 love6 (4/18/19)
- https://codingbat.com/prob/p100958
```py
# The number 6 is a truly great number. Given two int values, a and b, return True if either one is 6. Or if their sum or difference is 6. Note: the function abs(num) computes the absolute value of a number.
# love6(6, 4) → True
# love6(4, 5) → False
# love6(1, 5) → True
def love6(a, b):
  is6 = a == 6 or b == 6
  sum6 = a + b == 6
  diff6 = abs(a-b) == 6 or abs(b-a) == 6
  
  if is6 or sum6 or diff6:
    return True
  return False
```

---

## Logic1 in1to10 (4/18/19)
- https://codingbat.com/prob/p158497
```py
# Given a number n, return True if n is in the range 1..10, inclusive. Unless outside_mode is True, in which case return True if the number is less or equal to 1, or greater or equal to 10.
# in1to10(5, False) → True
# in1to10(11, False) → False
# in1to10(11, True) → True
def in1to10(n, outside_mode):
  if outside_mode:
    if n >= 10 or n <= 1:
      return True
    return False
  return 1 <= n <= 10
```

---

## Logic1 near_ten (4/18/19)
- https://codingbat.com/prob/p165321
```py
# Given a non-negative number "num", return True if num is within 2 of a multiple of 10. Note: (a % b) is the remainder of dividing a by b, so (7 % 5) is 2. See also: Introduction to Mod
# near_ten(12) → True
# near_ten(17) → False
# near_ten(19) → True
def near_ten(num):
  if num%10 <= 2 or (10 - num%10 <= 2):
    return True
  return False
```

---

## Logic2 make_bricks (4/19/19)
- https://codingbat.com/prob/p118406

- tough problem but simple solution once understands
- covers all cases up to the goal and beyond
```py
# We want to make a row of bricks that is goal inches long. We have a number of small bricks (1 inch each) and big bricks (5 inches each). Return True if it is possible to make the goal by choosing from the given bricks. This is a little harder than it looks and can be done without any loops. See also: Introduction to MakeBricks
# make_bricks(3, 1, 8) → True
# make_bricks(3, 1, 9) → False
# make_bricks(3, 2, 10) → True
def make_bricks(small, big, goal):
	combined = small + big*5
	leftoverGoal = goal % 5

  # if the goal is ever higher than combined,
	if goal > combined:
		return False
  
  # if we don't have enough to cover leftovers from goal
	elif small >= leftoverGoal:
		return True
	return False

print(make_bricks(1, 2, 12))
```

---

## Logic2 lone_sum (4/19/19)
- https://codingbat.com/prob/p143951
```py
# Given 3 int values, a b c, return their sum. However, if one of the values is the same as another of the values, it does not count towards the sum.
# lone_sum(1, 2, 3) → 6
# lone_sum(3, 2, 3) → 2
# lone_sum(3, 3, 3) → 0
def lone_sum(a, b, c):
  ab = a == b
  bc = b == c
  ac = a == c
  
  if ab and bc:
    return 0
  elif ab:
    return c
  elif bc:
    return a
  elif ac:
    return b
  else:
    return a + b + c

# ALTERNATE
def lone_sum(a, b, c):
  sum = 0
  if a != b and a != c: sum += a
  if b != a and b != c: sum += b
  if c != a and c != b: sum += c
  
  return sum
```

---

## Logic2 lucky_sum (4/19/19)
- https://codingbat.com/prob/p107863
```py
# Given 3 int values, a b c, return their sum. However, if one of the values is 13 then it does not count towards the sum and values to its right do not count. So for example, if b is 13, then both b and c do not count.
# lucky_sum(1, 2, 3) → 6
# lucky_sum(1, 2, 13) → 3
# lucky_sum(1, 13, 3) → 1
def lucky_sum(a, b, c):
  if a == 13:
    return 0
  elif b == 13:
    return a
  elif c == 13:
    return a + b
  else:
    return a + b + c
```

---

## Logic2 no_teen_sum (4/19/19)
- https://codingbat.com/prob/p100347
```py
# Given 3 int values, a b c, return their sum. However, if any of the values is a teen -- in the range 13..19 inclusive -- then that value counts as 0, except 15 and 16 do not count as a teens. Write a separate helper "def fix_teen(n):"that takes in an int value and returns that value fixed for the teen rule. In this way, you avoid repeating the teen code 3 times (i.e. "decomposition"). Define the helper below and at the same indent level as the main no_teen_sum().
# no_teen_sum(1, 2, 3) → 6
# no_teen_sum(2, 13, 1) → 3
# no_teen_sum(2, 1, 14) → 3
def fix_teen(n):
  if 13 <= n <= 14 or 17 <= n <= 19:
    return 0
  return n
  
def no_teen_sum(a, b, c):
  return fix_teen(a) + fix_teen(b) + fix_teen(c)
```

---

## Logic2 round_sum (4/19/19)
- https://codingbat.com/prob/p179960
```py
# For this problem, we'll round an int value up to the next multiple of 10 if its rightmost digit is 5 or more, so 15 rounds up to 20. Alternately, round down to the previous multiple of 10 if its rightmost digit is less than 5, so 12 rounds down to 10. Given 3 ints, a b c, return the sum of their rounded values. To avoid code repetition, write a separate helper "def round10(num):" and call it 3 times. Write the helper entirely below and at the same indent level as round_sum().
# round_sum(16, 17, 18) → 60
# round_sum(12, 13, 14) → 30
# round_sum(6, 4, 4) → 10
def round_sum(a, b, c):
  return round10(a) + round10(b) + round10(c)
  
def round10(num):
  if num <= 4:
    return 0
  elif num <= 10:
    return 10
  else:
    return round(num/10) * 10
```

---

## Logic2 close_far (4/19/19)
- https://codingbat.com/prob/p160533
```py
# Given three ints, a b c, return True if one of b or c is "close" (differing from a by at most 1), while the other is "far", differing from both other values by 2 or more. Note: abs(num) computes the absolute value of a number.
# close_far(1, 2, 10) → True
# close_far(1, 2, 3) → False
# close_far(4, 1, 3) → True
def close_far(a, b, c):
  if abs(a-b) <= 1 and abs(a-c) > 1 and abs(b-c) > 1:
    return True
  elif abs(a-c) <= 1 and abs(a-b) > 1 and abs(b-c) > 1:
    return True
  return False

```

---

## Logic2 make_chocolate (4/19/19)
- https://codingbat.com/prob/p190859

- lots of edge cases
- STRATEGY: proceed from most coverage of cases to least
```py
# We want make a package of goal kilos of chocolate. We have small bars (1 kilo each) and big bars (5 kilos each). Return the number of small bars to use, assuming we always use big bars before small bars. Return -1 if it can't be done.
# make_chocolate(4, 1, 9) → 4
# make_chocolate(4, 1, 10) → -1
# make_chocolate(4, 1, 7) → 2
def make_chocolate(small, big, goal):
	leftover = goal % 5
	combined = small + (big*5)
	bg = big*5
	
	if goal > combined:
		return -1
	elif bg == goal:
	  return 0
	elif small >= leftover and bg > goal:
	  return leftover
	elif small >= leftover and bg < goal:
	  return goal - bg
	return -1
```

---

## String2 double_char (4/20/19)
- https://codingbat.com/prob/p170842
```py
# Given a string, return a string where for every char in the original, there are two chars.
# double_char('The') → 'TThhee'
# double_char('AAbb') → 'AAAAbbbb'
# double_char('Hi-There') → 'HHii--TThheerree'
def double_char(str):
	newStr = ''
	for i in str:
		newStr += (i + i)
	return newStr

print(double_char('The')) # 'TThhee`
print(double_char('AAbb')) # 'AAAAbbbb'
print(double_char('Hi-There')) # 'HHii--TThheerree'

# ALTERNATE
def double_char(str):
  result = ""
  for i in range(len(str)):
    result += str[i] + str[i]
  return result
```

---

## String2 count_hi (4/20/19)
- https://codingbat.com/prob/p167246
```py
# Return the number of times that the string "hi" appears anywhere in the given string.
# count_hi('abc hi ho') → 1
# count_hi('ABChi hi') → 2
# count_hi('hihi') → 2
def count_hi(str):
	count = 0
	for i in range(len(str)-1):
		if (str[i] + str[i+1]) == 'hi':
			count += 1
	return count

print(count_hi('abc hi ho'))
print(count_hi('ABChi hi'))
print(count_hi('hihi'))

# ALTERNATE
def count_hi(str):
  sum = 0
  ## Loop to length-1 and access index i and i+1
  ## in the loop.
  for i in range(len(str)-1):
    if str[i:i+2] == 'hi':
      sum = sum + 1
  return sum
```

---

## String2 cat_dog (4/20/19)
- https://codingbat.com/prob/p164876
```py
# Return True if the string "cat" and "dog" appear the same number of times in the given string.
# cat_dog('catdog') → True
# cat_dog('catcat') → False
# cat_dog('1cat1cadodog') → True
def cat_dog(str):
	catCount = 0
	dogCount = 0

	for i in range(len(str)-1):
		if str[i:i+3] == 'cat':
			catCount += 1
		if str[i:i+3] == 'dog':
			dogCount += 1

	return catCount == dogCount

print(cat_dog('catdog')) # True
print(cat_dog('catcat')) # False
print(cat_dog('1cat1cadodog')) # True
```

---

## String2 count_code (4/20/19)
- https://codingbat.com/prob/p186048
```py
# Return the number of times that the string "code" appears anywhere in the given string, except we'll accept any letter for the 'd', so "cope" and "cooe" count.
# count_code('aaacodebbb') → 1
# count_code('codexxcode') → 2
# count_code('cozexxcope') → 2
def count_code(str):
	count = 0
	for i in range(len(str)-1):
		co = str[i:i+2] == 'co'
		d = str[i+2:i+3].isalpha()
		e = str[i+3:i+4] == 'e'
		if co and d and e:
			count += 1
	return count

print(count_code('aaacodebbb')) # 1
print(count_code('codexxcode')) # 2
print(count_code('cozexxcope')) # 2

# ALTERNATE
import re

def count_code(str):
	result = re.compile('co.e')
	return len(result.findall(str))

print(count_code('aaacodebbb')) # 1
print(count_code('codexxcode')) # 2
print(count_code('cozexxcope')) # 2
```

---

## String2 end_other (4/20/19)
- https://codingbat.com/prob/p174314
```py
# Given two strings, return True if either of the strings appears at the very end of the other string, ignoring upper/lower case differences (in other words, the computation should not be "case sensitive"). Note: s.lower() returns the lowercase version of a string.
# end_other('Hiabc', 'abc') → True
# end_other('AbC', 'HiaBc') → True
# end_other('abc', 'abXabc') → True
def end_other(a, b):
	sliceA = a[-(len(b)):].lower()
	sliceB = b[-(len(a)):].lower()
	if sliceA == b.lower() or sliceB == a.lower():
		return True
	return False

print(end_other('Hiabc', 'abc')) # True
print(end_other('AbC', 'HiaBc')) # True
print(end_other('abc', 'abXabc')) # True
print(end_other('Hiabc', 'bc')) # True

# ALTERNATE
def end_other(a, b):
  a = a.lower()
  b = b.lower()
  return (b.endswith(a) or a.endswith(b))
```

---

## String2 xyz_there (4/20/19)
- https://codingbat.com/prob/p149391
```py
# Return True if the given string contains an appearance of "xyz" where the xyz is not directly preceeded by a period (.). So "xxyz" counts but "x.xyz" does not.
# xyz_there('abcxyz') → True
# xyz_there('abc.xyz') → False
# xyz_there('xyz.abc') → True
def xyz_there(str):
	if str[:3] == 'xyz':
		return True
	for i in range(len(str)-1):
		checkAlphaDigit = (str[i]).isalpha() or (str[i]).isdigit()
		checkStr = str[i+1:i+4] == 'xyz'
		if checkAlphaDigit and checkStr:
			return True
	return False

print(xyz_there('abcxyz')) #True
print(xyz_there('abc.xyz')) #False
print(xyz_there('xyz.abc')) #True
print(xyz_there('12xyz')) #True
```

---

## List2 count_evens (4/21/19)
- https://codingbat.com/prob/p189616
```py
# Return the number of even ints in the given array. Note: the % "mod" operator computes the remainder, e.g. 5 % 2 is 1.
# count_evens([2, 1, 2, 3, 4]) → 3
# count_evens([2, 2, 0]) → 3
# count_evens([1, 3, 5]) → 0
def count_evens(arr):
	counter = 0
	for i in arr:
		if i % 2 == 0:
			counter += 1
	return counter

print(count_evens([2,1,2,3,4]))
```

---

## List2 big_diff (4/21/19)
- https://codingbat.com/prob/p184853
```py
# Given an array length 1 or more of ints, return the difference between the largest and smallest values in the array. Note: the built-in min(v1, v2) and max(v1, v2) functions return the smaller or larger of two values.
# big_diff([10, 3, 5, 6]) → 7
# big_diff([7, 2, 10, 9]) → 8
# big_diff([2, 10, 7, 2]) → 8
def big_diff(nums):
	if len(nums) < 2:
		return 0

	smallest = 1000000000
	biggest = 0
	
	for i in range(len(nums)-1):
		if min(nums[i], nums[i+1]) < smallest:
			smallest = min(nums[i], nums[i+1])
		if max(nums[i], nums[i+1]) > biggest:
			biggest = max(nums[i], nums[i+1])
	
	return biggest - smallest

print(big_diff([10,3,5,6])) # 7
print(big_diff([7,2,10,9])) # 8
print(big_diff([2,10,7,2])) # 8
print(big_diff([2])) # 0
```

---

## List2 centered_average (4/21/19)
- https://codingbat.com/prob/p126968
```py
# Return the "centered" average of an array of ints, which we'll say is the mean average of the values, except ignoring the largest and smallest values in the array. If there are multiple copies of the smallest value, ignore just one copy, and likewise for the largest value. Use int division to produce the final average. You may assume that the array is length 3 or more.
# centered_average([1, 2, 3, 4, 100]) → 3
# centered_average([1, 1, 5, 5, 10, 8, 7]) → 5
# centered_average([-10, -4, -2, -4, -2, 0]) → -3
def centered_average(arr):
	newArr = sorted(arr)[1:-1]
	avg = round((sum(newArr) / len(newArr)), 0)
	return int(avg)

print(centered_average([1,2,3,4,100])) # 3
print(centered_average([1,1,5,5,10,8,7])) # 5
print(centered_average([-10,-4,-2,-4,-2,0]))
```

---

## List2 sum13 (4/21/19)
- https://codingbat.com/prob/p167025
```py
# Return the sum of the numbers in the array, returning 0 for an empty array. Except the number 13 is very unlucky, so it does not count and numbers that come immediately after a 13 also do not count.
# sum13([1, 2, 2, 1]) → 6
# sum13([1, 1]) → 2
# sum13([1, 2, 2, 1, 13]) → 6
def sum13(nums):
	sum = 0
	i = 0

	while i < len(nums):
		if nums[i] == 13:
			i += 2
		else:
			sum += nums[i]
			i += 1

	return sum

print(sum13([1,2,2,1])) # 6
print(sum13([1, 2, 13, 2, 1, 13])) # 4
```

---

## List2 sum67 (4/21/19)
- https://codingbat.com/prob/p108886
```py
# Return the sum of the numbers in the array, except ignore sections of numbers starting with a 6 and extending to the next 7 (every 6 will be followed by at least one 7). Return 0 for no numbers.
# sum67([1, 2, 2]) → 5
# sum67([1, 2, 2, 6, 99, 99, 7]) → 5
# sum67([1, 1, 6, 7, 2]) → 4
def sum67(nums):
	if len(nums) == 0:
		return 0

	total = 0
	locked = False

	for i in nums:
		if i == 6:
			locked = True
			continue
		elif i == 7 and locked:
			locked = False
			continue
		elif i == 7 and not locked:
			total += i
			continue
		elif locked:
			continue
		else:
			total += i

	return total

print(sum67([1,2,2])) #5
print(sum67([1,2,2,6,99,99,7])) # 5
print(sum67([1, 1, 6, 7, 2])) # 4
```

---

## List2 has22 (4/21/19)
- https://codingbat.com/prob/p119308
```py
# Given an array of ints, return True if the array contains a 2 next to a 2 somewhere.
# has22([1, 2, 2]) → True
# has22([1, 2, 1, 2]) → False
# has22([2, 1, 2]) → False
def has22(nums):
	for i in range(len(nums)-1):
		if nums[i] == 2 and nums[i+1] == 2:
			return True
	return False
```
