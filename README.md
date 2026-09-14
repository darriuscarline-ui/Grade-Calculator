# 1. Initialize student data
student_grades = {
    "Dave": [79, 93, 78],
    "Jess": [92, 78, 85],
    "Dame": [72, 89, 72],
}

# 2. Calculate average grades
student_averages = {}

for student, grades in student_grades.items():
    average = sum(grades) / len(grades)
    student_averages[student] = average

# 3. Determine letter grades
student_letter_grades = {}

for student, average in student_averages.items():
    if average >= 90:
        letter_grade = "A"
    elif average >= 80:
        letter_grade = "B"
    elif average >= 70:
        letter_grade = "C"
    elif average >= 60:
        letter_grade = "D"
    else:
        letter_grade = "F"

    student_letter_grades[student] = letter_grade

# Display each student's average and letter grade
print("Student Grades:")
for student in student_averages:
    print(
        student,
        "- Average:",
        round(student_averages[student], 2),
        "- Letter Grade:",
        student_letter_grades[student],
    )

# 4. Find the top performer
top_student = None
highest_average = 0

for student, average in student_averages.items():
    if average > highest_average:
        highest_average = average
        top_student = student

print("\nTop Performer:")
print(top_student, "with an average grade of", round(highest_average, 2))

# 5. Calculate overall class average
overall_class_average = sum(student_averages.values()) / len(student_averages)

# Count students who received a passing grade (C or better)
passing_students = 0

for student, letter_grade in student_letter_grades.items():
    if letter_grade == "A" or letter_grade == "B" or letter_grade == "C":
        passing_students += 1

# Display class statistics
print("\nClass Statistics:")
print("Overall Class Average:", round(overall_class_average, 2))
print("Number of Students Who Passed:", passing_students)
