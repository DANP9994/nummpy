# Import the numpy library and give it an alias 'np' for easier referencing.
import numpy as np

# Create a 2D numpy array where the first row represents the upper bounds of grades and the second row represents the lower bounds.
a = np.array([[100, 90, 80, 70, 60, 50, 45], [90, 80, 70, 60, 50, 40, 30]])
L = ["S", "A", "B", "C", "D", "E", "F"]
n = int(input("Enter Marks Scored by Students: "))

# Create a mask (Boolean array) where each element is True if the student's score falls within the corresponding grade boundary.
grade_mask = (a[1] <= n) & (n < a[0])

# Find the index (position) of the grade boundary that the student's score falls into.
index = np.where(grade_mask)[0]

# If there's a match (i.e., the student's score falls within one of the grade boundaries), assign the corresponding grade label. Otherwise, assign "Invalid Score".
if index.size > 0:
    grade = L[index[0]]
else:
    grade = "Invalid Score"

print("Grade:", grade)
