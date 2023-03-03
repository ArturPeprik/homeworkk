#14
with open('name.txt', 'w') as file:
    file.write('Hello, world!')

with open('name.txt', 'r') as file:
    data = file.read()
    print(data)

with open('name.txt', 'w') as file:
    file.write('Hello again!')

dictionary = {'apple': 1, 'banana': 2, 'orange': 3}
with open('dictionary.txt', 'w') as file:
    for key, value in dictionary.items():
        file.write(f'{key}: {value}\n')

import os
os.remove('dictionary.txt')
#15
def read_f(*f):
    for f in f:
        with open(f, 'r') as f:
            print(f.read())

def count_words(file1):
    with open(file1, 'r') as f:
        text = f.read()
        words = text.split()
        return len(words)

def print_short_words(file):

    with open(file, 'r') as f:
        text = f.read()
        words = text.split()
        short_words = [word for word in words if len(word) < 4]
        print(' '.join(short_words))

def count_capitalized_words(file):
    with open(file, 'r') as f:
        text = f.read()
        words = text.split()
        capitalized_words = [word for word in words if word[0].isupper()]
        return len(capitalized_words)

#17
def reverse_and_append_type(lst, output_list):
    for item in reversed(lst):
        output_list.append(item)
        output_list.append(type(item))

#18
def find_common_elements(l1, l2, output_list):
    for i1 in l1:
        for i2 in l2:
            if i1 == i2:
                output_list.append(i1)
                break
    reverse_and_append_type(l1, list)
    print(list)
#19
def find_elements(list16, list26, output_list6):
    for item16 in list16:
        for item26 in list26:
            if item16 == item26:
                output_list6.append(item16)
                break
    find_elements(list16, list26, list)
    print(list)
#20
def decorator(func):
    def wrapper():
        return func().upper()
    return wrapper

@decorator
def func1():
    return 'we are best students'

print(func1())
