# QuizGame.py
def run_quiz(questions):
    score = 0
    for question in questions:
        print(question['question'])
        for idx, option in enumerate(question['options'], 1):
            print(f"{idx}. {option}")
        
        answer = input("Enter your answer (1, 2, 3, ...): ")
        if answer.isdigit() and 1 <= int(answer) <= len(question['options']):
            if question['options'][int(answer) - 1] == question['answer']:
                print("Correct!")
                score += 1
            else:
                print("Incorrect.")
        else:
            print("Invalid input. Skipping question.")

        print()  # Add a newline for better readability

    print(f"Quiz completed! Your score is: {score}/{len(questions)}")


# Define your quiz questions here
questions = [
    {
        'question': 'What is the capital of France?',
        'options': ['London', 'Paris', 'Berlin'],
        'answer': 'Paris'
    },
    {
        'question': 'Which planet is known as the Red Planet?',
        'options': ['Mars', 'Earth', 'Venus'],
        'answer': 'Mars'
    },
    {
        'question': 'What is the largest mammal?',
        'options': ['Elephant', 'Blue Whale', 'Giraffe'],
        'answer': 'Blue Whale'
    }
]

run_quiz(questions)
