# Python-week-8
1.Binary String

Coders here is a simple task for you, Given string str. Your task is to check whether it is a binary string or not by using python set.

CODE:

def is_binary_string(s):

return set(s) <= {'0', '1'}
str1 = input()

print("Yes" if is_binary_string(str1) else "No")

#2.Check Pair

Given a tuple and a positive integer k, the task is to find the count of distinct pairs in the tuple whose sum is equal to K.

CODE:

def count_distinct_pairs(t, K):

pair_set = set()

seen = set()

count = 0



for num in t:

    complement = K - num

    if complement in seen and (complement, num) not in pair_set and (num, complement) not in pair_set:

        pair_set.add((complement, num))

        count += 1

    seen.add(num)



return count
t = tuple(int(x) for x in input().split(','))

K = int(input())

print(count_distinct_pairs(t, K)) #3.DNA Sequence

The DNA sequence is composed of a series of nucleotides abbreviated as 'A', 'C', 'G', and 'T'.

For example, "ACGAATTCCG" is a DNA sequence.

When studying DNA, it is useful to identify repeated sequences within the DNA.

Given a string s that represents a DNA sequence, return all the 10-letter-long sequences (substrings) that occur more than once in a DNA molecule. You may return the answer in any order.

CODE:

s = input()

sequence_length=10

if len(s) < sequence_length:

print("No repeated sequences.")
else:

seen = {}

repeated = []



for i in range(len(s) - sequence_length + 1):

    sequence = s[i:i + sequence_length]

    if sequence in seen:

        seen[sequence] += 1

        if seen[sequence] == 2:

            repeated.append(sequence)

    else:

        seen[sequence] = 1



if not repeated:

    print("No repeated sequences.")

else:

    for sequence in repeated:

        print(sequence)
 #4.Print repeated no
Given an array of integers nums containing n + 1 integers where each integer is in the range [1, n] inclusive.There is only one repeated number in nums, return this repeated number. Solve the problem using set.

CODE:

def find_duplicate(nums):

seen = set()

for num in nums:

    if num in seen:

        return num

    seen.add(num)

return -1  # This line should never be reached given the problem constraints
Read input from the user
nums = list(map(int, input().split()))

Find and print the duplicate number
duplicate = find_duplicate(nums)

print(duplicate) #5.

Remove repeated

Write a program to eliminate the common elements in the given 2 arrays and print only the non-repeating elements and the total number of such non-repeating elements.

Input Format:

The first line contains space-separated values, denoting the size of the two arrays in integer format respectively.

The next two lines contain the space-separated integer arrays to be compared.

CODE:

n, m = input().split()

n = int(n)

m = int(m)

arr1 = [int(x) for x in input().split()]

arr2 = [int(x) for x in input().split()]

non_repeating_elements = set(arr1).symmetric_difference(set(arr2))

if non_repeating_elements:

print(*non_repeating_elements)

print(len(non_repeating_elements))
else:

print("NO SUCH ELEMENTS")
#6.Malfunctioning Keyboard

There is a malfunctioning keyboard where some letter keys do not work. All other keys on the keyboard work properly.

Given a string text of words separated by a single space (no leading or trailing spaces) and a string brokenLetters of all distinct letter keys that are broken, return the number of words in text you can fully type using this keyboard.

CODE:

a=input()

a=a.split(" ")

b=input()

count=0

for i in range(len(a)):

if a[i].find(b):

count+=1

if count>len(b):

print(len(b))

else:

print(count-1) #7.American keyboard

Given an array of strings words, return the words that can be typed using letters of the alphabet on only one row of American keyboard like the image below.

In the American keyboard:

 the first row consists of the characters "qwertyuiop",

 the second row consists of the characters "asdfghjkl", and

 the third row consists of the characters "zxcvbnm".

CODE:

n=int(input())

L=[]

while(n):

L.append(input())

n-=1
K=["qwertyuiop","asdfghjkl","zxcvbnm"]

Y={}

for i in K:

Y[i]=[]
for k in K:

for l in L:

    if(set(k).union(set(l.lower()))==set(k)): #if the word can be typed using 1 row of keyboard then the union of the word and the row of keyboard is the row of keyboard

        Y[k].append(l)

    else:

        continue
flag=True

for m in Y:

if(Y[m]==[]):

    continue

else:

    flag=False

    break
if(not(flag)):

for x in Y:

    for s in Y[x]:

        print(s)
else:

print("No words")
