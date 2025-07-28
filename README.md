def basic_calculator():
    """
    A simple Python program that performs basic arithmetic operations
    based on user input.
    """
    print("Welcome to the Basic Calculator!")

    try:
        # Get the first number from the user
        num1_str = input("Enter the first number: ")
        num1 = float(num1_str) # Convert input to float to handle decimals

        # Get the second number from the user
        num2_str = input("Enter the second number: ")
        num2 = float(num2_str) # Convert input to float

        # Get the mathematical operation from the user
        operation = input("Enter the operation (+, -, *, /): ")

        result = None
        expression = f"{num1_str} {operation} {num2_str}"

        if operation == '+':
            result = num1 + num2
        elif operation == '-':
            result = num1 - num2
        elif operation == '*':
            result = num1 * num2
        elif operation == '/':
            if num2 == 0:
                print("Error: Division by zero is not allowed.")
                return # Exit the function if division by zero
            else:
                result = num1 / num2
        else:
            print("Error: Invalid operation. Please use +, -, *, or /.")
            return # Exit the function if invalid operation

        # Print the result in the specified format
        if result is not None:
            # Format numbers to be integers if they are whole numbers
            # This makes the output like the example (10 + 5 = 15) rather than (10.0 + 5.0 = 15.0)
            if num1.is_integer():
                num1_display = int(num1)
            else:
                num1_display = num1

            if num2.is_integer():
                num2_display = int(num2)
            else:
                num2_display = num2

            if result.is_integer():
                result_display = int(result)
            else:
                result_display = result

            print(f"{num1_display} {operation} {num2_display} = {result_display}")

    except ValueError:
        print("Error: Invalid input. Please enter valid numbers.")
    except Exception as e:
        print(f"An unexpected error occurred: {e}")

# Call the function to run the calculator
basic_calculator()
