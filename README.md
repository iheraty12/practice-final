# practice-final

# tidbit.py

# Constants
DOWN_PAYMENT_RATE = 0.10
ANNUAL_INTEREST_RATE = 0.12
MONTHLY_PAYMENT_RATE = 0.05

# Get purchase price from user
purchase_price = float(input("Enter the purchase price: "))

# Calculate the down payment
down_payment = purchase_price * DOWN_PAYMENT_RATE

# Calculate the initial balance after down payment
balance = purchase_price - down_payment

# Initialize the month counter
month = 1

# Print the table headers
print(f"{'Month':<10}{'Balance Owed':<20}{'Interest':<15}{'Principal':<15}{'Payment':<15}{'Remaining Balance':<20}")

# Loop to calculate and display each month's payment details
while balance > 0:
    # Calculate the monthly interest
    interest = balance * (ANNUAL_INTEREST_RATE / 12)

    # Calculate the monthly payment
    payment = purchase_price * MONTHLY_PAYMENT_RATE

    # Calculate the principal payment
    principal = payment - interest

    # If the balance is less than the payment, adjust the payment
    if balance < payment:
        payment = balance + interest
        principal = balance

    # Calculate the remaining balance after the payment
    remaining_balance = balance - principal

    # Display the current month's payment details
    print(f"{month:<10}{balance:<20.2f}{interest:<15.2f}{principal:<15.2f}{payment:<15.2f}{remaining_balance:<20.2f}")

    # Update the balance and increment the month
    balance = remaining_balance
    month += 1
