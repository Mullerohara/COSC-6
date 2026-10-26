# COSC-6
Sorry for the late notice more technical difficulties
import random

def state_capital_quiz():
    # 1. Create a dictionary containing U.S. states as keys and their capitals as values
    state_capitals = {
        'Alabama': 'Montgomery', 'Alaska': 'Juneau', 'Arizona': 'Phoenix', 
        'Arkansas': 'Little Rock', 'California': 'Sacramento', 'Colorado': 'Denver', 
        'Connecticut': 'Hartford', 'Delaware': 'Dover', 'Florida': 'Tallahassee', 
        'Georgia': 'Atlanta', 'Hawaii': 'Honolulu', 'Idaho': 'Boise', 
        'Illinois': 'Springfield', 'Indiana': 'Indianapolis', 'Iowa': 'Des Moines', 
        'Kansas': 'Topeka', 'Kentucky': 'Frankfort', 'Louisiana': 'Baton Rouge', 
        'Maine': 'Augusta', 'Maryland': 'Annapolis', 'Massachusetts': 'Boston', 
        'Michigan': 'Lansing', 'Minnesota': 'St. Paul', 'Mississippi': 'Jackson', 
        'Missouri': 'Jefferson City', 'Montana': 'Helena', 'Nebraska': 'Lincoln', 
        'Nevada': 'Carson City', 'New Hampshire': 'Concord', 'New Jersey': 'Trenton', 
        'New Mexico': 'Santa Fe', 'New York': 'Albany', 'North Carolina': 'Raleigh', 
        'North Dakota': 'Bismarck', 'Ohio': 'Columbus', 'Oklahoma': 'Oklahoma City', 
        'Oregon': 'Salem', 'Pennsylvania': 'Harrisburg', 'Rhode Island': 'Providence', 
        'South Carolina': 'Columbia', 'South Dakota': 'Pierre', 'Tennessee': 'Nashville', 
        'Texas': 'Austin', 'Utah': 'Salt Lake City', 'Vermont': 'Montpelier', 
        'Virginia': 'Richmond', 'Washington': 'Olympia', 'West Virginia': 'Charleston', 
        'Wisconsin': 'Madison', 'Wyoming': 'Cheyenne'
    }

    # Initialize score counters
    correct_count = 0
    incorrect_count = 0

    print("--- Welcome to the U.S. State Capitals Quiz! ---")
    print("Type 'exit' at any time to end the quiz and see your final score.\n")

    # Convert dictionary keys into a list to pick randomly
    states = list(state_capitals.keys())

    # 2. Main quiz loop
    while True:
        # Pick a random state
        state = random.choice(states)
        correct_capital = state_capitals[state]

        # Display the prompt and get user input
        user_answer = input(f"What is the capital of {state}? ").strip()

        # Check if the user wants to quit
        if user_answer.lower() == 'exit':
            break

        # 3. Verify response and keep score
        # Using .lower() ensures capitalization differences don't break correctness
        if user_answer.lower() == correct_capital.lower():
            print(" Correct!\n")
            correct_count += 1
        else:
            print(f" Incorrect. The correct capital is {correct_capital}.\n")
            incorrect_count += 1

    # 4. Display final results
    print("\n--- Quiz Finished! ---")
    print(f"Correct responses: {correct_count}")
    print(f"Incorrect responses: {incorrect_count}")
    
    total = correct_count + incorrect_count
    if total > 0:
        percentage = (correct_count / total) * 100
        print(f"Your score: {percentage:.1f}%")

# Run the program
if __name__ == "__main__":
    state_capital_quiz()
