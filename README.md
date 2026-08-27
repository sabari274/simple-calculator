# simple-calculator
"""
Simple Python Calculator
Supports: +, -, *, /, ** (power), % (modulus)
"""

def calculate(num1, operator, num2):
    if operator == '+':
        return num1 + num2
    elif operator == '-':
        return num1 - num2
    elif operator == '*':
        return num1 * num2
    elif operator == '/':
        if num2 == 0:
            return "Error: Division by zero"
        return num1 / num2
    elif operator == '**':
        return num1 ** num2
    elif operator == '%':
        if num2 == 0:
            return "Error: Division by zero"
        return num1 % num2
    else:
        return "Error: Invalid operator"


def main():
    print("=== Python Calculator ===")
    print("Operators: + - * / ** %")
    print("Type 'quit' to exit\n")

    while True:
        expr = input("Enter calculation (e.g. 5 + 3): ").strip()

        if expr.lower() == 'quit':
            print("Goodbye!")
            break

        parts = expr.split()

        if len(parts) != 3:
            print("Invalid format. Use: number operator number (e.g. 5 + 3)\n")
            continue

        num1_str, operator, num2_str = parts

        try:
            num1 = float(num1_str)
            num2 = float(num2_str)
        except ValueError:
            print("Invalid numbers entered.\n")
            continue

        result = calculate(num1, operator, num2)
        print(f"Result: {result}\n")


if __name__ == "__main__":
    main()
