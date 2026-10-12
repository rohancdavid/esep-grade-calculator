# ESEP Grade Calculator

## Description
This library is a simple utility to calculate your grades.
The calculation is based on 3 customizable weighted categories including assignments, exams, and essays.

## Requirements
Runtime requirements:
- Golang 1.24+
- Git and Github

## Grading Scale
### Passing requires a C or higher
- **A:** 90+
- **B:** 80-89
- **C:** 70-79
- **D:** 60-69
- **F:** 0-59

## Files
- **go.mod:** Declares the path of the project for Go to use and what versions to use.
- **grade_calculator.go:** Contains the program that calculates the grades. Includes GradeCalculator, Grade, and GradeType, with functions to add, average, calculate, and convert them.
- **grade_calculator_test.go:** Has automatic unit tests to check grade_calculator.go is returning the set expected values.

## Testing
### How to Run Unit Tests:
Run unit tests:
```
cd grade_calculator/
go test ./...
```

Run unit tests with code coverage:
```
cd grade_calculator/
go test -coverprofile=coverage.txt ./...
```
### Included Unit tests:
- **TestGetGradedA:** Tests if calculated grade matches expected grade of A given 3 grades of 100 for each category.
- **TestGetGradedB:** Tests if calculated grade matches expected grade of B given 3 grades of 80, 81, and 85 for each category respectively.
- **TestGetGradedF:** Tests if calculated grade matches expected grade of F given 3 grades of 100, 95, and 91 for each category respectively. Returns as a passing test despite the test incorrectly classifying an A as an F.

## Issues
### grade_calculator.go:
- Incorrectly calculates average
- Essay average returns exam average
- Empty grades cause a division of zero error
- Grade inputs aren't validated
- Truncated numerical grade values instead of rounding them

### grade_calculator_test.go:
- TestGetGradedF returns as passing despite the test incorrectly classifying an A as an F
- Doesn't test all possible grades
- No edge case testing