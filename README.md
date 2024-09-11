# Equal-Elements
You are given an array A of size N. In one operation, you can do the following:
Select indices i and j (𝑖 ≠ 𝑗) and set Ai​ = Aj​.
Find the minimum number of operations required to make all elements of the array equal?

from collections import Counter

def min_operations_to_equal_elements(test_cases):
    results = []
    
    for case in test_cases:
        N, arr = case
        freq = Counter(arr)
        max_frequency = max(freq.values())
        operations = N - max_frequency
        results.append(operations)
    
    return results

T = int(input())  
test_cases = []

for _ in range(T):
    N = int(input())  
    arr = list(map(int, input().split()))  
    test_cases.append((N, arr))

# Process the test cases
results = min_operations_to_equal_elements(test_cases)

# Output the results
for res in results:
    print(res)
