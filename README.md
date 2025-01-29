# ATM
ATM machine
# ---------------------------ATM MACHINE--------------------------------
import time

print("Please insert your card details:")
time.sleep(4)  # Simulating time taken by the machine
password = 2468  # The user's PIN
balance = 25000  # Initial balance

# Prompt for PIN
pin = int(input("Please enter your PIN: "))

if pin == password:
    while True:
        print("""
        2 == Check Balance
        4 == Withdraw Balance
        6 == Deposit Balance
        8 == Exit
        """)
        try:
            option = int(input("Please enter your choice: "))
        except ValueError:
            print("Please enter a valid number.")
            continue  # Restart the loop if invalid input is entered

        if option == 2:
            print(f"Your current balance is {balance}")
            print("----------------------------------------------------------")
            print("----------------------------------------------------------")
            print("----------------------------------------------------------")
        elif option == 4:
            try:
                withdraw_amount = int(input("Please enter the amount to withdraw: "))
                if withdraw_amount > balance:
                    print("Insufficient funds.")
                else:
                    balance -= withdraw_amount
                    print(f"{withdraw_amount} has been debited from your account.")
                    print(f"Your updated balance is {balance}")
                    print("----------------------------------------------------------")
                    print("----------------------------------------------------------")
                    print("----------------------------------------------------------")
            except ValueError:
                print("Please enter a valid number.")
        elif option == 6:
            try:
                deposit_amount = int(input("Please enter the amount to deposit: "))
                balance += deposit_amount
                print(f"{deposit_amount} has been credited to your account.")
                print(f"Your updated balance is {balance}")
            except ValueError:
                print("Please enter a valid number.")
                print("----------------------------------------------------------")
                print("----------------------------------------------------------")
                print("----------------------------------------------------------")
        elif option == 8:
            print("Thank you for using our service. Goodbye!")
            break  # Exit the loop
        else:
            print("Invalid choice. Please try again.")
else:
    print("Wrong password: TRY AGAIN")
