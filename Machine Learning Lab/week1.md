# Week 1

```python
import csv
num_attributes = 6
a = []
print("\n The Given Training Data Set \n")
with open('ENJOYSPORT.csv', 'r') as csvfile:
  reader = csv.reader(csvfile)
  for row in reader:
    a.append(row)
print(row)
print("\n The initial value of hypothesis: ")
hypothesis = ['0'] * num_attributes
print(hypothesis)
for j in range(num_attributes):
  hypothesis[j] = a[0][j]
print("\n Find S : Finding a Maximally Specific Hypothesis \n")
for i in range(len(a)):
  if a[i][num_attributes] == 'yes':
    for j in range(num_attributes):
      if a[i][j] != hypothesis[j]:
        hypothesis[j] = '?'
      else:
        hypothesis[j] = a[i][j]
print("For Training instance No : {0} the hypothesis is ".format(i), hypothesis)
print("\n The Maximally Specific Hypothesis for a given Training Examples : \n")
print(hypothesis)
```

`Output`

```
 The Given Training Data Set 

['Sunny', 'Warm', 'High', 'Strong', 'Cool', 'Change', '1']

 The initial value of hypothesis: 
['0', '0', '0', '0', '0', '0']

 Find S : Finding a Maximally Specific Hypothesis 

For Training instance No : 4 the hypothesis is  ['Sky', 'AirTemp', 'Humidity', 'Wind', 'Water', 'Forecast']

 The Maximally Specific Hypothesis for a given Training Examples : 

['Sky', 'AirTemp', 'Humidity', 'Wind', 'Water', 'Forecast']
```