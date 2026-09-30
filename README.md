# HCL-25-09-26

## 25 September 2026

### Python Code Implementation

## 1. Student Attendance Analysis

A college maintains the daily attendance details of its students in the form of a list containing student IDs. Some students may have attended multiple sessions on the same day. The administration wants to identify the longest continuous sequence of sessions in which no student ID is repeated. Develop a solution that determines the maximum length of such a sequence.

### Implementation

```python
l1 = input().split(",")

longest = 0

for i in range(len(l1)):
    arr = []

    for j in range(i, len(l1)):
        if l1[j] in arr:
            break

        arr.append(l1[j])

    if len(arr) > longest:
        longest = len(arr)

print(longest)
```

---

## 2. Online Shopping Price Analysis

An online shopping application stores the prices of products viewed by a customer during a browsing session. The customer wants to identify a continuous range of products that provides the maximum possible total discount value. Given the discount values, determine the maximum value that can be obtained from any continuous range.

### Implementation

```python
arr = list(map(int, input().split()))

curr = arr[0]
maxSum = arr[0]

for i in range(1, len(arr)):
    curr = max(arr[i], curr + arr[i])
    maxSum = max(maxSum, curr)

print(maxSum)
```

---

## 3. Rainwater Collection System

A city installs buildings of different heights along a straight road. During rainfall, water gets collected between taller buildings. The engineering team needs to calculate the total amount of water that can remain trapped after heavy rainfall based on the heights of the buildings.

### Implementation

```python
arr = list(map(int, input().split()))

water = 0

for i in range(len(arr)):
    left = max(arr[:i+1])
    right = max(arr[i:])

    level = min(left, right)

    if level >= arr[i]:
        water += level - arr[i]

print(water)
```

---

## 4. Employee Performance Analysis

A company stores the monthly performance scores of an employee for several months. The scores may contain both positive and negative values depending on the employee's performance. Management wants to identify the continuous period during which the employee achieved the highest overall performance.

### Implementation

```python
arr = list(map(int, input().split()))

curr = arr[0]
maxSum = arr[0]

for i in range(1, len(arr)):
    curr = max(arr[i], curr + arr[i])
    maxSum = max(maxSum, curr)

print(maxSum)
```

---

## 5. Product Sales Analysis

A retail company stores the daily sales quantity of a product for several consecutive days. Due to seasonal changes, some days may have negative adjustments. The company wants to identify the period that produced the highest multiplication of sales-related values. Develop a solution to determine this maximum product.

### Implementation

```python
arr = list(map(int, input().split()))

maximum = arr[0]
minimum = arr[0]
answer = arr[0]

for i in range(1, len(arr)):
    x = arr[i]

    if x < 0:
        maximum, minimum = minimum, maximum

    maximum = max(x, maximum * x)
    minimum = min(x, minimum * x)

    answer = max(answer, maximum)

print(answer)
```

---

## 6. Customer Purchase History

An e-commerce application stores the product IDs purchased by a customer in chronological order. The same product may appear multiple times. The system needs to determine the longest sequence of consecutive purchases in which every product ID is unique.

### Implementation

```python
l1 = input().split(",")

longest = 0

for i in range(len(l1)):
    arr = []

    for j in range(i, len(l1)):
        if l1[j] in arr:
            break

        arr.append(l1[j])

    if len(arr) > longest:
        longest = len(arr)

print(longest)
```

---

## 7. Bank Transaction Analysis

A bank stores transaction amounts for a customer's account. A continuous group of transactions may add up to a specific target amount. The auditing system needs to determine how many different continuous transaction groups produce exactly the specified amount.

### Implementation

```python
arr = list(map(int, input().split()))

target = int(input())

count = 0

for i in range(len(arr)):
    total = 0

    for j in range(i, len(arr)):
        total += arr[j]

        if total == target:
            count += 1

print(count)
```

---

## 8. Employee Skill Grouping

A company receives a list of employee skill codes represented as strings. Employees having the same set of characters in their skill codes belong to the same skill category, even if the characters appear in a different order. The HR system needs to organize employees into appropriate skill groups.

### Implementation

```python
arr = input().split()

groups = {}

for word in arr:
    key = ''.join(sorted(word))

    if key not in groups:
        groups[key] = []

    groups[key].append(word)

for group in groups.values():
    print(group)
```

---

## 9. Network Packet Analysis

A network monitoring system receives packet identifiers in chronological order. The system must determine the longest sequence of consecutive packets whose identifiers form a continuous numerical sequence, regardless of their original order in the incoming data.

### Implementation

```python
arr = list(map(int, input().split()))

nums = set(arr)

longest = 0

for x in nums:

    if x - 1 not in nums:

        current = x
        length = 1

        while current + 1 in nums:
            current += 1
            length += 1

        longest = max(longest, length)

print(longest)
```

---

## 10. Hospital Appointment Scheduling

A hospital receives appointment requests represented by starting and ending times. Some appointments overlap with each other. The scheduling system needs to combine overlapping appointment periods so that the final schedule contains only non-overlapping time ranges.

### Implementation

```python
n = int(input())

arr = []

for i in range(n):
    start, end = map(int, input().split())
    arr.append([start, end])

arr.sort()

result = [arr[0]]

for i in range(1, n):
    start = arr[i][0]
    end = arr[i][1]

    if start <= result[-1][1]:
        result[-1][1] = max(result[-1][1], end)

    else:
        result.append([start, end])

for x in result:
    print(x[0], x[1])
```
---

## 29 September 2026

### Python Code Implementation

#### 1. NumPy-based Assignment

```python
import numpy as np

scores = np.array([78, 65, 89, 56, 92])

print("Q1 - Student Marks Array")
print("Array:", scores)
print("Dimensions:", scores.ndim)
print("Shape:", scores.shape)
print("Number of elements:", scores.size)
print("Data type:", scores.dtype)
```

#### 2. Calculate Area of a Circle

```python
import math

radius = float(input())

area = math.pi * radius * radius

print("Area of circle:", round(area, 2))
```

#### 3. Count Character Frequency in a String

```python
text = input()

frequency = {}

for char in text:
    if char != " ":
        frequency[char] = frequency.get(char, 0) + 1

print("Character frequency:")

for char, count in frequency.items():
    print(char, ":", count)
```

#### 4. Calculate Factorial

```python
number = int(input())

factorial = 1

for value in range(2, number + 1):
    factorial *= value

print("Factorial:", factorial)
```

#### 5. Generate Fibonacci Series

```python
num = int(input())

first, second = 0, 1
series = []

for _ in range(num):
    series.append(first)
    first, second = second, first + second

print("Fibonacci series:", series)
```

#### 6. Merge Two Dictionaries

```python
dict_one = {
    "name": "Priyanka",
    "age": 20
}

dict_two = {
    "course": "AI & DS",
    "year": 3
}

merged = {**dict_one, **dict_two}

print("Merged dictionary:", merged)
```

#### 7. Check Prime Numbers

```python
n = int(input())

if n < 2:
    is_prime = False
else:
    is_prime = True

    for divisor in range(2, int(n ** 0.5) + 1):
        if n % divisor == 0:
            is_prime = False
            break

if is_prime:
    print(n, "is a prime number")
else:
    print(n, "is not a prime number")
```

#### 8. Reverse a String

```python
text = input()

reversed_text = text[::-1]

print("Reversed string:", reversed_text)
```

#### 9. Remove Duplicate Elements from a List

```python
numbers = [10, 20, 10, 30, 20, 40, 30]

unique_values = list(dict.fromkeys(numbers))

print("Original list:", numbers)
print("After removing duplicates:", unique_values)
```

#### 10. Find the Second-Largest Element

```python
numbers = [45, 12, 78, 34, 90, 56]

distinct_numbers = sorted(set(numbers), reverse=True)

if len(distinct_numbers) >= 2:
    print("Second-largest element:", distinct_numbers[1])
else:
    print("Second-largest element does not exist")
```

#### 11. Calculate Square Using Lambda

```python
number = float(input())

square = lambda x: x * x

print("Square:", square(number))
```

#### 12. Display Employee Information Using Functions

```python
def show_employee(name, employee_id, department):
    print("Employee Name:", name)
    print("Employee ID:", employee_id)
    print("Department:", department)


show_employee(
    "Priyanka",
    "EMP101",
    "Automation Testing"
)
```

#### 13. Perform Mathematical Operations Using Functions

```python
def addition(a, b):
    return a + b


def subtraction(a, b):
    return a - b


def multiplication(a, b):
    return a * b


def division(a, b):
    if b == 0:
        return "Division by zero is not possible"
    return a / b


x = float(input())
y = float(input())

print("Addition:", addition(x, y))
print("Subtraction:", subtraction(x, y))
print("Multiplication:", multiplication(x, y))
print("Division:", division(x, y))
```

#### 14. Remove Duplicates Using a Function

```python
def remove_duplicates(items):
    result = []

    for item in items:
        if item not in result:
            result.append(item)

    return result


data = [5, 8, 5, 2, 8, 9, 2, 10]

print("Original data:", data)
print("Unique data:", remove_duplicates(data))
```

#### 15. Sort Tuple Elements Using a Function

```python
def sort_tuple(values):
    return tuple(sorted(values))


data = (45, 12, 78, 23, 9, 56)

print("Original tuple:", data)
print("Sorted tuple:", sort_tuple(data))
```





