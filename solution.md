# Solution Code - Transaction Tracker

<details>
<summary> Step 1 Solution - Define the Transaction Class</summary>
Python - transaction_tracker.py

```python
class Transaction:
    def __init__(self, amount, description):
        self.amount = amount
        self.description = description

    def show(self):
        print(f"{self.amount} - {self.description}")

```
</details>

<details>
<summary>Step 2 Solution – Create a List to Hold Transactions</summary>
Python - transaction_tracker.py

Inside `main()`, at the very top, create a test ledger list:

```python
transactions = []
transactions.append(Transaction(200, "example payment 1"))
transactions.append(Transaction(40, "example payment 2"))

for t in transactions:
    t.show()
```
</details>  

<details>
<summary>Step 3 Solution – Build the Menu Loop</summary>
Python - transaction_tracker.py

```python
while True:
    choice = input("Type 'exit' to quit: ")
    if choice == "exit":
        break
        
# This example simply demonstrates the while True loop with a break condition.
# You’ll update or expand this logic in the next step.
```
</details>  

<details>
<summary> Step 4 Solution – Handle User Choices</summary>
Python - transaction_tracker.py

```python
while True:
    print("1. Add Credit")
    print("2. Add Debit")
    print("3. View History")
    print("4. Exit")

    choice = input("Choose an option: ")

    if choice == "1":
        print("You chose Add Credit")
    elif choice == "2":
        print("You chose Add Debit")
    elif choice == "3":
        print("You chose View History")
    elif choice == "4":
        break
    else:
        print("Invalid option, please try again.")
```
</details>   



<details>
<summary> Step 5 Solution – Add Transaction Credit Logic</summary>
Python - transaction_tracker.py

```python
while True:
	# ... earlier print menu and user input 'choice' code
	
    if choice == "1":
        print("You chose Add Credit")
        amount = float(input("Enter credit amount: "))
		description = input("Enter description: ")
		t = Transaction(amount, description)
		transactions.append(t)
    elif choice == "2":
        print("You chose Add Debit")
    elif choice == "3":
        print("You chose View History")
    elif choice == "4":
        break
    else:
        print("Invalid option, please try again.")

# Use this loop to test your code
for t in transactions:
    t.show()
```
</details>   



<details>
<summary> Step 6 Solution – Add Transaction Debit Logic</summary>
Python - transaction_tracker.py

```python
# Debits (inside choice == "2" elif code block)
elif choice == "2":
    print("You chose Add Debit")
	amount = float(input("Enter debit amount: "))
	description = input("Enter description: ")
	t = Transaction(-1 * amount, description)
	transactions.append(t)
```
</details>   



<details>
<summary> Step 7 Solution – View History and Balance</summary>
Python - transaction_tracker.py

```python
# Balance History (**inside choice == "3" elif code block)** 
elif choice == "3":
	print("You chose View History")
	balance = 0
	for t in transactions:
	    t.show()
	    balance += t.amount
	
	print(f"Current Balance: {balance}")
```
</details>   



<details>
<summary>Final Solution</summary>
Python - transaction_tracker.py

```python
# transaction_tracker.py
# Starter code for Project 05 – Transaction Tracker CLI
# ------------------------------------------------------
# You will complete the TODO sections in order.
# Follow the step-by-step project instructions.
# ------------------------------------------------------

# STEP 1: Define the Transaction class
# TODO: Remove 'pass' and add __init__ and show() methods

class Transaction:
    def __init__(self, amount, description):
        # Store the amount and description for each transaction
        self.amount = amount
        self.description = description

    def show(self):
        # Print one transaction in a readable format
        print(f"{self.amount} - {self.description}")

# STEP 2–7: All program logic happens inside main()
def main():
    print("Welcome to the Transaction Tracker!")

    # STEP 2: Create a list to hold transactions
    transactions = []

    # STEP 3: Build the menu loop
    while True:
        # Display menu options
        print("1. Add Credit")
        print("2. Add Debit")
        print("3. View History")
        print("4. Exit")

        # Ask the user for their choice
        choice = input("Choose an option: ")

        # STEP 5: Add Transaction Credit Logic
        if choice == "1":
            amount = float(input("Enter credit amount: "))
            description = input("Enter description: ")
            t = Transaction(amount, description)
            transactions.append(t)
            print("Credit added successfully.")

        # STEP 6: Add Transaction Debit Logic
        elif choice == "2":
            amount = float(input("Enter debit amount: "))
            description = input("Enter description: ")
            t = Transaction(-1 * amount, description)
            transactions.append(t)
            print("Debit added successfully.")

        # STEP 7: View History and Balance
        elif choice == "3":
            if not transactions:
                print("No transactions yet.")
            else:
                balance = 0
                print("\n=== Transaction History ===")
                for t in transactions:
                    t.show()
                    balance += t.amount
                print(f"---------------------------")
                print(f"Current Balance: {balance}")

        # STEP 4: Handle Exit
        elif choice == "4":
            print("Exiting the tracker. Goodbye!")
            break

        # Invalid choice handler
        else:
            print("Invalid option, please try again.")

# Run the program
if __name__ == "__main__":
    main()

```
</details>
