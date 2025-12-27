# Muiz_cos_tax_calculator_assignment# Personal Income Tax Calculator (2009)

status = int(input(
    "Enter filing status:\n"
    "0 - Single\n"
    "1 - Married Filing Jointly or Qualifying Widow(er)\n"
    "2 - Married Filing Separately\n"
    "3 - Head of Household\n"
))

income = float(input("Enter taxable income: "))

tax = 0

if status == 0:  # Single
    if income <= 8350:
        tax = income * 0.10
    elif income <= 33950:
        tax = 8350 * 0.10 + (income - 8350) * 0.15
    elif income <= 82250:
        tax = 8350 * 0.10 + (33950 - 8350) * 0.15 + (income - 33950) * 0.25
    else:
        tax = 8350 * 0.10 + (33950 - 8350) * 0.15 + (82250 - 33950) * 0.25 + (income - 82250) * 0.28

elif status == 1:  # Married filing jointly
    if income <= 16700:
        tax = income * 0.10
    elif income <= 67900:
        tax = 16700 * 0.10 + (income - 16700) * 0.15
    elif income <= 137050:
        tax = 16700 * 0.10 + (67900 - 16700) * 0.15 + (income - 67900) * 0.25
    else:
        tax = 16700 * 0.10 + (67900 - 16700) * 0.15 + (137050 - 67900) * 0.25 + (income - 137050) * 0.28

elif status == 2:  # Married filing separately
    if income <= 8350:
        tax = income * 0.10
    elif income <= 33950:
        tax = 8350 * 0.10 + (income - 8350) * 0.15
    elif income <= 68525:
        tax = 8350 * 0.10 + (33950 - 8350) * 0.15 + (income - 33950) * 0.25
    else:
        tax = 8350 * 0.10 + (33950 - 8350) * 0.15 + (68525 - 33950) * 0.25 + (income - 68525) * 0.28

elif status == 3:  # Head of household
    if income <= 11950:
        tax = income * 0.10
    elif income <= 45500:
        tax = 11950 * 0.10 + (income - 11950) * 0.15
    elif income <= 117450:
        tax = 11950 * 0.10 + (45500 - 11950) * 0.15 + (income - 45500) * 0.25
    else:
        tax = 11950 * 0.10 + (45500 - 11950) * 0.15 + (117450 - 45500) * 0.25 + (income - 117450) * 0.28

else:
    print("Invalid filing status")
    exit()

print(f"Total tax is: ${tax:.2f}")
