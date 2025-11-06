# Grading Report

**Final Grade: 6.00/10.00**

## Rubric

| Criterion | Points |
|-----------|--------|
| `extract_data` correctly slices, title-cases names, int conversion, extracts grades, and leaves input untouched | **2** |
| `curve_grades` applies the curve (while loop) and caps values at 100 | **1.5** |
| `print_top_performers` prints only qualifying `Name: Score` lines (>= 95) | **1.5** |
| Code quality (required loop choices, clear logic) | **1** |

## General Comments

extract_data
Loop shape is fine, but you are mis-using variables:
   - you only extract names, you never extract or convert grades
   - you never append grades to s_grades


curve_grades
while loop start is correct, but:
   - you index the wrong thing
   - you add 5 to the wrong variable 
   - clamp check is against the function name, not the numeric grade
   - return is inside the loop. function exits on first iteration

print_top_performers
   - don't reassign names = [] - destroys inputs
   - compare grade values, not the name variable
   - don't return - this should only print lines

## Functionality

- tests/test_grader.py::RosterHelperTests::test_curve_grades_values_and_clamping: Failed (0.0 points)
   Error:     TypeError: '<' not supported between instances of 'int' and 'range'

- tests/test_grader.py::RosterHelperTests::test_extract_data_parses_names_and_grades_title_case: Failed (0.0 points)
   Error:         ValueError: invalid literal for int() with base 10: '2025-fall:ana lopez:78'

- tests/test_grader.py::RosterHelperTests::test_extract_data_returns_new_lists: Failed (0.0 points)
   Error:         ValueError: invalid literal for int() with base 10: '2025-fall:max jones:85'

- tests/test_grader.py::RosterHelperTests::test_print_top_performers_prints_name_and_score_for_ge_95: Failed (0.0 points)
   Error:                 AttributeError: 'int' object has no attribute 'append'



