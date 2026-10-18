# quiz-application
The Quiz Application is a simple Python project that allows users to answer multiple-choice questions and test their knowledge. It uses loops, conditional statements (if-else), lists, and dictionaries to display questions, check answers, and calculate the final score. At the end, it displays the total score and percentage
questions = [
    {
        "question": "1. Which language are we learning?",
        "options": ["A. Java", "B. Python", "C. C++", "D. HTML"],
        "answer": "B"
    },
    {
        "question": "2. Which keyword is used for a condition?",
        "options": ["A. for", "B. print", "C. if", "D. input"],
        "answer": "C"
    },
    {
        "question": "3. Which loop repeats while a condition is true?",
        "options": ["A. while", "B. if", "C. else", "D. break"],
        "answer": "A"
    },
    {
        "question": "4. Which data type stores multiple items in order?",
        "options": ["A. int", "B. bool", "C. float", "D. list"],
        "answer": "D"
    },
    {
        "question": "5. Which function displays output?",
        "options": ["A. input()", "B. print()", "C. range()", "D. type()"],
        "answer": "B"
    }
]

score = 0

# print("================================")
print("      PYTHON QUIZ APPLICATION")
# print("================================")

# Loop through each question
for question in questions:
    print("\n" + question["question"])

    # Display the options
    for option in question["options"]:
        print(option)

    user_answer = input("Enter your answer (A/B/C/D): ").strip().upper()

    # Check whether the answer is valid
    while user_answer not in ["A", "B", "C", "D"]:
        print("Invalid choice! Please enter A, B, C, or D.")
        user_answer = input("Enter your answer: ").strip().upper()

    # Check the answer using a condition
    if user_answer == question["answer"]:
        print("Correct answer!")
        score += 1
    else:
        print("Wrong answer!")
        print("Correct answer:", question["answer"])

# Display final results
total = len(questions)
percentage = (score / total) * 100

print("\n")
print("          QUIZ RESULTS")
# print("================================")
print("Total questions:", total)
print("Correct answers:", score)
print("Wrong answers:", total - score)
print("Percentage:", percentage, "%")

if percentage >= 80:
    print("Grade: Excellent!")
elif percentage >= 60:
    print("Grade: Good!")
elif percentage >= 40:
    print("Grade: Average!")
else:
    print("Grade: Keep practicing!")

print("Thank you for playing!")
