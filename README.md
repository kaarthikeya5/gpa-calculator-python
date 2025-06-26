# Define subject data as (subject name, credits)
subjects = [
    ("Mathematics – I", 4),
    ("Engineering Physics", 4),
    ("Programming in C / Python", 3),
    ("Basic Civil & Mechanical Engineering", 3),
    ("Communicative English", 2),
    ("Physics Lab", 1.5),
    ("Programming Lab", 1.5),
    ("Workshop Practice", 1),
    ("English Lab", 1)
]

# Grade point function based on marks
def get_grade_point(marks):
    if marks >= 90:
        return 10
    elif marks >= 80:
        return 9
    elif marks >= 70:
        return 8
    elif marks >= 60:
        return 7
    elif marks >= 50:
        return 6
    elif marks >= 45:
        return 5
    elif marks >= 40:
        return 4
    else:
        return 0  # Fail

def calculate_gpa():
    total_points = 0
    total_credits = 0

    print("\n📘 GPA Calculator – Semester 1")
    print("----------------------------------")

    for subject, credits in subjects:
        while True:
            try:
                marks = float(input(f"Enter your marks for {subject}: "))
                if 0 <= marks <= 100:
                    break
                else:
                    print("⚠️ Enter marks between 0 and 100.")
            except ValueError:
                print("❌ Invalid input. Please enter a number.")
        
        grade_point = get_grade_point(marks)
        total_points += grade_point * credits
        total_credits += credits

    gpa = total_points / total_credits
    print(f"\n🎯 Your Semester GPA is: {gpa:.2f}")

if __name__ == "__main__":
    calculate_gpa()

