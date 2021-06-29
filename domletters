#! /usr/bin/python3

# Greg Hairfield
# CS461/Summer 2021
# Assignment 1
#
# Count the dominant letters in an input file and print the total to stdout.
#
# For this program a word is defined as <space>word<space>, where <word> only
# contains a-z and A-Z with no punctuation A dominant letter is defined as the
# most common letter in a word. This program is designed to be case-insensitive.
#
# Examples:
# 'The' -- {'t': 1, 'h': 1, 'e': 1} = 1
# 'Apple' -- {'a': 1, 'p': 2, 'l': 1, 'e': 1} = 2
# 'Dessert.' -- Invalid word because of the punctuation at the end.
#
# Usage:
# ./domletters <file.txt

import re
import sys

def dominant_letters(word_list):
    """Count the dominant letters in a sentence.

    Keyword arguments:
    word_list -- A python list of words

    Returns:
    The total of dominant letters in word list.
    """
    total = 0
    for word in word_list:
        if re.search('[^a-zA-Z]', word) is None:
            letters = {}
            for i in word.lower():
                letters[i] = letters.get(i, 0) + 1
            total += max(letters.values())
    return total

if __name__ == '__main__':
    """ Gather a list of words from stdin

    The program is intended to have a file redirected to stdin. Parse 
    the input and separate each word. Print the total.
    """
    words = []
    for i in sys.stdin:
        i = i.strip()
        sp = i.split()
        words.extend(sp)

    print('Total = {}'.format(dominant_letters(words)))
