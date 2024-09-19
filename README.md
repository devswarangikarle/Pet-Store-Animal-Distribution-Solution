# Pet-Store-Animal-Distribution-Solution

Problem Breakdown:
The problem requires us to check if Sanjana and Vansh can end up with exactly the same multiset of animals after Sanjana purchases some of the animals from the pet store, and Vansh buys the rest. Both should have the same number of animals of each type.

Key Insights:
Multisets: The problem is about comparing two multisets, meaning not only the types of animals should match but also the number of each type.

Even Frequency Requirement: For it to be possible for Sanjana and Vansh to have the same multiset:

The total count of each animal type must be even. This is because the total number of animals of a certain type needs to be split equally between the two.
Plan:
For each test case:
Count the frequency of each animal type.
Check if the frequency of every animal type is even.
If all frequencies are even, it's possible for Sanjana and Vansh to split the animals equally, and the answer will be "Yes". Otherwise, the answer will be "No".
Approach:
Parse the input and read the number of test cases.
For each test case:
Count the frequency of each animal type using a frequency array or dictionary.
Check if all frequencies are even.
Return "Yes" if all frequencies are even, otherwise "No".

Solution Code:

def can_split_equally(N, animals):
    freq = [0] * 101
    
    for animal in animals:
        freq[animal] += 1
    
    for count in freq:
        if count % 2 != 0:
            return "No"
    
    return "Yes"

import sys
input = sys.stdin.read
data = input().split()

t = int(data[0])
index = 1
results = []

for _ in range(t):
    n = int(data[index])
    animals = list(map(int, data[index + 1: index + 1 + n]))
    index += n + 1
    
    results.append(can_split_equally(n, animals))

sys.stdout.write("\n".join(results) + "\n")

