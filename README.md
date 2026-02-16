# Huffman-Shannon_fano
# Aim:
Consider a discrete memoryless source with symbols and statistics {0.35, 0.2, 0.15, 0.12, 0.1, 0.08} for its output. 
Apply the Huffman and Shannon-Fano to this source. 
Show that by drawing the tree diagram, and 
Calculate the average code word length, entropy, variance, redundancy, and efficiency.
# Tools Required:
colab/jupyter

# Program:
```
import math

n = int(input("Enter number of samples: "))
p  = [float(input(f"P{i+1}: ")) for i in range(n)]
lk = [float(input(f"L{i+1}: ")) for i in range(n)]

L  = sum(p[i]*lk[i] for i in range(n))                     # Avg length
hs = round(sum(p[i]*math.log2(1/p[i]) for i in range(n)),3) # Entropy
eff = round(hs/L,3)                                        # Efficiency
red = round(1-eff,3)                                       # Redundancy
var = round(sum(p[i]*(lk[i]-L)**2 for i in range(n)),3)    # Variance

print("Average Length:", L)
print("Entropy:", hs)
print("Efficiency:", eff)
print("Redundancy:", red)
print("Variance:", var)
```
# Calculation:

<img width="800" height="900" alt="image" src="https://github.com/user-attachments/assets/ad3a9b66-bb7e-4ddb-8000-8123bf40b160" />

<img width="800" height="999" alt="image" src="https://github.com/user-attachments/assets/d2bf4745-bc4a-44a8-b241-79a7ffd3a97c" />

# Output
<img width="286" height="83" alt="Screenshot 2026-02-16 152204" src="https://github.com/user-attachments/assets/3e4b60eb-a7b7-4174-aa11-b7cddc203424" />




# Results:
For the given discrete memoryless source with probabilities {0.35, 0.2, 0.15, 0.12, 0.1, 0.08} , both Huffman and Shannon–Fano coding were applied. The simulation was carried out in Python (Google Colab). Since the source probabilities are exact powers of two, the codeword lengths match the ideal values, giving zero redundancy and 100% coding efficiency. Both Huffman and Shannon–Fano yield identical results.
