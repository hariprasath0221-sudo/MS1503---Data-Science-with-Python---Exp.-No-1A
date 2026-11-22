# Experiment 1.A: Employee Data Display Using Python

## Aim

To collect employee details, validate inputs, and calculate gross and net salary using Python.

## Algorithm

1. **Start** the program.
2. **Read Employee Details** from the user:
   * Input `name` (String) for the employee's full name.
   * Input `emp_id` (String) for the employee's identification number.
   * Input `basic` (Float) for the employee's basic salary.
3. **Validate Input**:
   * Ensure `basic` is a valid numeric value and check if `basic < 0`. If invalid or negative, display an appropriate error message and terminate the program.
4. **Compute Allowances**:
   * Calculate House Rent Allowance: `HRA = 0.15 × basic`
   * Calculate Dearness Allowance: `DA = 0.10 × basic`
5. **Compute Gross Salary**:
   * `Gross Salary = basic + HRA + DA`
6. **Compute Tax Deduction**:
   * Calculate income tax at 8% of gross pay: `Tax = 0.08 × Gross Salary`
7. **Compute Net Salary**:
   * `Net Salary = Gross Salary - Tax`
8. **Display Formatted Payroll Report**:
   * Print a structured summary displaying `name`, `emp_id`, `basic`, `HRA`, `DA`, `Gross Salary`, `Tax`, and `Net Salary` formatted to two decimal places.
9. **Stop** the program.

## Program

```python
# Employee Data Display and Salary Calculation

# Step 2: Read employee details
name = input("Enter employee name: ")
emp_id = input("Enter employee ID: ")

# Step 3: Validate basic salary
try:
    basic = float(input("Enter basic salary: "))
except ValueError:
    print("Error: Basic salary must be a valid number.")
    exit()

if basic < 0:
    print("Error: Basic salary cannot be negative.")
    exit()

# Step 4: Compute allowances
hra = 0.15 * basic
da = 0.10 * basic

# Step 5: Compute gross salary
gross = basic + hra + da

# Step 6: Compute tax deduction
tax = 0.08 * gross

# Step 7: Compute net salary
net = gross - tax

# Step 8: Display payroll report
print("\n" + "=" * 35)
print("        EMPLOYEE PAYROLL REPORT")
print("=" * 35)
print(f"Name          : {name}")
print(f"Employee ID   : {emp_id}")
print("-" * 35)
print(f"Basic Salary  : {basic:10.2f}")
print(f"HRA (15%)     : {hra:10.2f}")
print(f"DA (10%)      : {da:10.2f}")
print(f"Gross Salary  : {gross:10.2f}")
print(f"Tax (8%)      : {tax:10.2f}")
print("-" * 35)
print(f"Net Salary    : {net:10.2f}")
print("=" * 35)
```

## Output

**Sample Run 1: Valid Input**

```
Enter employee name: Rahul Kumar
Enter employee ID: EMP101
Enter basic salary: 30000

===================================
        EMPLOYEE PAYROLL REPORT
===================================
Name          : Rahul Kumar
Employee ID   : EMP101
-----------------------------------
Basic Salary  :   30000.00
HRA (15%)     :    4500.00
DA (10%)      :    3000.00
Gross Salary  :   37500.00
Tax (8%)      :    3000.00
-----------------------------------
Net Salary    :   34500.00
===================================
```

**Sample Run 2: Negative Salary**

```
Enter employee name: Priya Sharma
Enter employee ID: EMP102
Enter basic salary: -5000
Error: Basic salary cannot be negative.
```

**Sample Run 3: Non-numeric Salary**

```
Enter employee name: Arun Raj
Enter employee ID: EMP103
Enter basic salary: abc
Error: Basic salary must be a valid number.
```

## ✅ Result

The program successfully accepts and validates employee details, calculates allowances and deductions, and displays a well-formatted salary report.
