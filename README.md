# Deckycoop

import math
from sympy import symbols, Eq, solve

def physics_calculator():
    print("\n-- Physics Menu --")
    print("1. Calculate Force (F = m × a)")
    print("2. Calculate Work (W = F × d)")
    print("3. Calculate Power (P = W / t)")
    print("4. Ohm's Law (V = I × R)")
    choice = input("Choose (1-4): ")

    if choice == "1":
        m = float(input("Enter mass (kg): "))
        a = float(input("Enter acceleration (m/s²): "))
        print("Force = ", m * a, "N")
    elif choice == "2":
        F = float(input("Enter force (N): "))
        d = float(input("Enter distance (m): "))
        print("Work = ", F * d, "J")
    elif choice == "3":
        W = float(input("Enter work (J): "))
        t = float(input("Enter time (s): "))
        print("Power = ", W / t, "W")
    elif choice == "4":
        I = float(input("Enter current (A): "))
        R = float(input("Enter resistance (Ω): "))
        print("Voltage = ", I * R, "V")
    else:
        print("Invalid choice.")

def unit_converter():
    print("\n-- Unit Converter --")
    print("1. Length (m ↔ cm ↔ km)")
    print("2. Mass (g ↔ kg)")
    print("3. Temperature (C ↔ F ↔ K)")
    print("4. Time (s ↔ min ↔ hr)")
    choice = input("Choose (1-4): ")

    if choice == "1":
        meters = float(input("Enter value in meters: "))
        print(f"Centimeters: {meters * 100} cm")
        print(f"Kilometers: {meters / 1000} km")
    elif choice == "2":
        grams = float(input("Enter value in grams: "))
        print(f"Kilograms: {grams / 1000} kg")
    elif choice == "3":
        c = float(input("Enter temperature in Celsius: "))
        print(f"Fahrenheit: {c * 9/5 + 32} °F")
        print(f"Kelvin: {c + 273.15} K")
    elif choice == "4":
        seconds = float(input("Enter time in seconds: "))
        print(f"Minutes: {seconds / 60} min")
        print(f"Hours: {seconds / 3600} hr")
    else:
        print("Invalid choice.")

def chemistry_calculator():
    print("\n-- Chemistry Menu --")
    print("1. Mole Calculation (n = m / M)")
    print("2. Simple Molar Mass of Compound")
    choice = input("Choose (1-2): ")

    if choice == "1":
        m = float(input("Enter mass (g): "))
        M = float(input("Enter molar mass (g/mol): "))
        print("Moles = ", m / M, "mol")
    elif choice == "2":
        element_count = int(input("How many elements? "))
        total_mass = 0
        for _ in range(element_count):
            atomic_mass = float(input("Enter atomic mass of element: "))
            count = int(input("How many atoms of this element? "))
            total_mass += atomic_mass * count
        print("Molar Mass = ", total_mass, "g/mol")
    else:
        print("Invalid choice.")

def math_calculator():
    print("\n-- Mathematics Menu --")
    print("1. Solve Quadratic Equation")
    print("2. Factorial")
    print("3. Trigonometric Function")
    choice = input("Choose (1-3): ")

    if choice == "1":
        a = float(input("Enter a: "))
        b = float(input("Enter b: "))
        c = float(input("Enter c: "))
        x = symbols('x')
        eq = Eq(a*x**2 + b*x + c, 0)
        sol = solve(eq, x)
        print("Solutions:", sol)
    elif choice == "2":
        n = int(input("Enter number: "))
        print(f"{n}! =", math.factorial(n))
    elif choice == "3":
        angle = float(input("Enter angle in degrees: "))
        rad = math.radians(angle)
        print("sin =", round(math.sin(rad), 4))
        print("cos =", round(math.cos(rad), 4))
        print("tan =", round(math.tan(rad), 4))
    else:
        print("Invalid choice.")

# Main menu
def main():
    while True:
        print("\n==== Science Calculator ====")
        print("1. Physics")
        print("2. Unit Converter")
        print("3. Chemistry")
        print("4. Mathematics")
        print("5. Exit")
        option = input("Choose a category (1-5): ")

        if option == "1":
            physics_calculator()
        elif option == "2":
            unit_converter()
        elif option == "3":
            chemistry_calculator()
        elif option == "4":
            math_calculator()
        elif option == "5":
            print("Goodbye!")
            break
        else:
            print("Invalid input. Try again.")

# Run the calculator
main() 