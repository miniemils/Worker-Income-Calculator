# Worker Income Calculator

This is a Java console application designed to calculate a worker's total income for a specific month, taking into account their base salary and any hourly contracts they worked during that period. It is a practical example of object-oriented programming concepts like composition and enumerations.

## Project Structure

The project is composed of multiple files separating the main execution from the business entities:

* **`Program.java`**: The main entry point of the application. It handles user input to gather department, worker, and contract data, and then prompts the user for a specific month and year to calculate the total income.
* **`Worker.java`**: The core entity class representing the employee. It encapsulates data such as name, seniority level, base salary, their associated department, and a list of contracts. It contains the business logic (`income` method) to calculate the total income for a given month and year.
* **`Department.java`**: A simple entity class representing the department to which the worker belongs.
* **`HourContract.java`**: An entity representing an individual hourly contract, containing the date, value per hour, and total hours worked.
* **`WorkerLevel.java`**: An enumeration defining the worker's seniority (JUNIOR, MID_LEVEL, or SENIOR).

## Features and Logic

* **Object Composition:** The system heavily utilizes object composition. A `Worker` has a "has-a" relationship with exactly one `Department` object and a list containing multiple `HourContract` objects.
* **Date Manipulation:** The application uses `SimpleDateFormat` to parse string inputs into `Date` objects. Inside the `Worker` class, it utilizes the `Calendar` class to extract the specific month and year from each contract's date to match against the user's target query.
* **Dynamic Income Calculation:** The total income is calculated dynamically. It starts with the worker's base salary and iterates through all associated contracts. If a contract's month and year match the requested parameters, the contract's total value (`valuePerHour * hours`) is added to the total sum.
* **Localization:** Enforces the US locale (`Locale.setDefault(Locale.US)`) to ensure consistency in parsing decimal numbers for salaries and hourly rates.