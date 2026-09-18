# Investment Growth Calculator

An academic C++ console application that compares investment growth with and without recurring monthly deposits. The program accepts an initial investment, monthly contribution, annual interest rate, and investment period, then displays year-end balances and earned interest for both scenarios.

## What this project demonstrates

- Object-oriented modeling with a `month` class
- Encapsulation through getters and setters
- Monthly compound-interest calculations
- Collection management with `std::vector`
- Input validation, formatted tabular output, and a repeatable console workflow
- Decomposition of input, calculation, and presentation responsibilities into functions

## Calculation model

The application creates one `month` object for every month in the requested period. For each month it calculates interest as:

```text
monthly interest = balance × (annual interest rate / 100 / 12)
```

The comparison case adds the monthly deposit before calculating that month's interest. At the end of every twelve-month period, the application reports the closing balance and total interest earned during that year.

This is an educational projection, not financial advice. It does not account for taxes, fees, withdrawals, variable rates, or contribution timing beyond the implementation described above.

## Project structure

| File | Purpose |
| --- | --- |
| [`main.cpp`](main.cpp) | Console workflow, validation, monthly calculations, and annual report formatting |
| [`month.h`](month.h) | Declaration of the monthly investment record |
| [`month.cpp`](month.cpp) | Constructor and accessor implementations |

## Build and run

The source uses the C++ standard library and can be compiled with a C++11-or-newer compiler. For example, with GCC or Clang:

```bash
g++ -std=c++11 main.cpp month.cpp -o investment-calculator
./investment-calculator
```

On Windows, run the generated executable from Command Prompt or Visual Studio. The current code calls the Windows-specific `system("pause")`; remove or replace that call before building for another operating system.

## Example workflow

```text
Initial Investment Amount: 1000
Monthly Deposit: 100
Annual Interest: 5
Number of Years: 2
```

The application then prints one row per year, comparing the ending balance and interest earned with no additional deposits against the result with monthly contributions.

## Current scope

This repository is a focused academic exercise. It does not include automated tests, persistence, a graphical interface, or financial-product integrations. A useful next step would be to separate calculation logic from console input/output and add unit tests for boundary cases and known compound-interest examples.

## Academic context

Created by Michael Foster for CS 210 at Southern New Hampshire University. Course requirements and starter guidance informed the project; this README describes the implementation currently present in the repository.
