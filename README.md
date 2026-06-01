# Ex 11- Huffman-Coding

## Aim
To implement Huffman coding to compress the data using Python.

## Software Required
1. Anaconda - Python 3.7

## Algorithm:
step1: Get the input string.

Step2: Create tree nodes.

Step3: Main function to implement huffman coding.

Step4: Calculate frequency of occurence.

Step5: Print the characters and its huffmancode.


## Developed By:
- **Name:** KESAVAN S
- **Register Number:**  212224230121

## Program:
```python
input_string = "KESAVAN S"
frequency = {}
for char in input_string:
    if char in frequency:
        frequency[char] += 1
    else:
        frequency[char] = 1
nodes = [[char, freq] for char, freq in frequency.items()]
while len(nodes) > 1:
    nodes = sorted(nodes, key=lambda x: x[1])
    left = nodes.pop(0)
    right = nodes.pop(0)
    new_node = [[left, right], left[1] + right[1]]
    nodes.append(new_node)
huffman_tree = nodes[0]
huffman_codes = {}

def generate_codes(tree, code=""):
    if isinstance(tree[0], str):
        huffman_codes[tree[0]] = code
    else:
        generate_codes(tree[0][0], code + "0")
        generate_codes(tree[0][1], code + "1")

generate_codes(huffman_tree)
print("Character | Huffman Code")
print("-------------------------")
for char, code in huffman_codes.items():
    print(f"    {char}    |    {code}")

```

## Output:

<img width="415" height="227" alt="image" src="https://github.com/user-attachments/assets/4d1ca258-2b01-4457-b077-92a1213a255b" />

## Result:

Thus the huffman coding was implemented to compress the data using python programming.
