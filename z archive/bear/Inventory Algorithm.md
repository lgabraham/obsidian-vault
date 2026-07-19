# Inventory Algorithm
Inventory Score = x + y + z + r

x = Saves Score (0-99):
Percentile of likes; 
If 0, score 0 or 1-in-K chance of J

y = Click-through Rate Score (0-99):
Percentile of click-through rate
If 0, score 0 or 1-in-K chance of J

z = Discount Score (0-99):
Percentile of discount
If 0, score 0 or 1-in-K chance of J

r = Randomness (0-R): 
Add random integer, uniformly distributed

Parameters to start:
K = 20
J = 50
R = 53

Max score: 350

Rescore each hour.