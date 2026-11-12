# Ex.-5-Lab-Exercise-Develop-a-Population-Growth-Model

## Name: PREM PRASANTH J

## Roll No: 2305001028

## Department: CSE

## AIM

To develop a simple mathematical model for population growth using Python and use the model to predict future population.

## PROGRAM

### Python Code

```python
import matplotlib.pyplot as plt
import numpy as np

# Historical population data
year = np.array([2020, 2021, 2022, 2023, 2024])
revenue = np.array([100, 110, 125, 135, 150])

# Convert years into time values
t = np.arange(len(year))

# Fit a linear growth model
b, a = np.polyfit(t, revenue, 1)

# Calculate predicted values
predicted_revenue = a + b * t

print(f"Base Revenue (a): {a:.2f}M")
print(f"Annual Growth Rate (b): {b:.2f}M/year")

print("\nYear  Actual ($M)  Predicted ($M)")
for y, act, pred in zip(year, revenue, predicted_revenue):
    print(f"{y}  {act:10.2f}  {pred:14.2f}")

# Forecast future values
future_year = np.array([2025, 2026, 2027])
future_t = np.array([5, 6, 7])

future_revenue = a + b * future_t

print("\nForecasted Revenue:")
for fy, f_rev in zip(future_year, future_revenue):
    print(f"{fy}: ${f_rev:.2f}M")

# Plot actual, fitted, and forecasted values
plt.figure(figsize=(10, 5))

plt.plot(year, revenue, 'o-', label='Actual Revenue')
plt.plot(year, predicted_revenue, 'x--', label='Fitted Model')
plt.plot(future_year, future_revenue, 's:', label='Forecast')

plt.title("Company Revenue Growth Model")
plt.xlabel("Year")
plt.ylabel("Revenue ($M)")
plt.legend()
plt.grid(True)
plt.show()
```

## OUTPUT

<img width="521" height="552" alt="image" src="https://github.com/user-attachments/assets/b1f78953-ffe0-4ed5-ae19-55ced8e7cf79" />


## RESULT

Thus, a simple mathematical growth model was developed successfully using Python, and the model was used to predict future values.
