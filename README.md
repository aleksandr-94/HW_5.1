# HW_5.1


import keyword
import string


def is_valid_variable_name(name):
    if not name:
        return False
    if name[0].isdigit():
        return False
    if any(char in
           string.punctuation.replace('_', '')
           for char in name):
        return False
    if any(char.isupper() for char in name):
        return False
    if name in keyword.kwlist:
        return False
    if name.count('_') > 3:
        return False
    return True
#перевірка
print(is_valid_variable_name('variable 1'))
print(is_valid_variable_name('Variable 1'))
print(is_valid_variable_name('variable_1'))
print(is_valid_variable_name('variable__1'))
print(is_valid_variable_name('1_variable'))
print(is_valid_variable_name('__variable'))
print(is_valid_variable_name('assert'))
