---
title: "Python tips"
description: "Python tips"
date: "2020-12-25"
banner:
src: "../../images/kelly-sikkema-Hl3LUdyKRic-unsplash.jpg"
alt: "Python Tips"
caption: 'Photo by <u><a href="https://unsplash.com/photos/Nc5Q_CEcY44">Florian Olivo</a></u>'
categories:
- "Python"
- "Coding interview"
  keywords:
- "Python"
- "Coding interview"
- "Leetcode"
---

Sometimes, you'll face problems that are not like a standard Leetcode style, which is with parameters and returns.
Problem-solving websites such as Hackerrank or ACM-style provides problems with standard input/output.
This post is a small tip for the Python standard input and output.

## Standard Output
```py
print("Hello world") # print with a line change
print("Hello world", end="") # print without a line change
```

## Standard Input
```py
# assume input is "1 2 3"

# using input with single variable.
a = input()
print(a) # variable a is a string that reads the one whole line

# using input with multiple variables
a, b, c = input().split()
print(a) # 1
print(b) # 2
print(type(c)) # <class 'str'>
# this will generate error if input is not splitted by 3

# casting type of input
a, b, c = map(int, input().split())
print(a+b+c) # 6

# putting numbers into a list
a = list(map(int, input().split()))
print(a) # [1, 2, 3]

# if you're not sure about the size of input
ret = list()
while True:
temp = list(map(int, input().split()))
if not temp:
break
ret.append(temp)
print(ret)

# sys.stdin.read()
input() is slower, so use sys.stdin.read() when you deal with a large amount of data
```

## Small Tip
```py
# max/min numbers
max_int = sys.maxsize
min_int = -sys.maxsize
# incrementing count in dict()
dic = dict()
for i in dic:
count = dic.get(i, 0)
dic[i] = count + 1
# or
dic[i] = dic[i] + 1 if i in dic else 1
# queue: using queue by list() is slow due to the properties of lists, which is fast at the end but slow at the beginning operations, as every element has to be shifted one by one. So use deque() when you're implementing queue.
q = collections.deque()
q.append(1)
q.append(2)
q.popleft()
# initialize 2d array
arr = [[0] * len(c) for _ in range(len(r))] # r = rows, c = columns
# ASCII characters
A_ascii = ord("A") # 65
a_ascii = ord("a") # 97
c_char = chr(99) # c
alphabet_order = ord(c_char) - ord("a") # 2
```
