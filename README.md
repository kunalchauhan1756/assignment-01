# assignment-01# Name: kunal chauhan 
# Date: 2025-11-10
# Project: Daily Calorie Tracker CLI Tool

print("Welcome to the Daily Calorie Tracker!")
print("This tool will help you log your meals, calculate total and average calorie intake,")
print("and compare it with your personal daily calorie limit.\n")

meal_names = []
calorie_amounts = []

meal_count = int(input("How many meals would you like to enter? "))

for i in range(meal_count):
    meal = input(f"Enter the name of meal #{i+1}: ")
    calories = float(input(f"Enter the calorie amount for {meal}: "))
    meal_names.append(meal)
    calorie_amounts.append(calories)
total_calories = sum(calorie_amounts)
average_calories = total_calories / meal_count

daily_limit = float(input("\nEnter your daily calorie limit: "))

if total_calories > daily_limit:
    print("\n️ Warning: You have exceeded your daily calorie limit!")
else:
    print("\n Good job! You're within your daily calorie limit.")

print("\n----- Calorie Intake Summary -----")
print("Meal Name\tCalories")
print("-----------------------------")
for meal, cal in zip(meal_names, calorie_amounts):
    print(f"{meal}\t\t{cal}")
print("-----------------------------")
print(f"Total:\t\t{total_calories}")
print(f"Average:\t{average_calories:.2f}")
