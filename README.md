# Student Data Management System

A Python application for storing, filtering, and processing student records using
core data structures: lists, tuples, sets, list comprehensions, set comprehensions,
and generator expressions.

## Setup

1. Clone the repository:
```sh
   git clone <repo-url>
   cd course-7-module-1-python-data-structures-lab
```
2. Install dependencies:
```sh
   pipenv install
```
3. Enter the virtual environment:
```sh
   pipenv shell
```
4. Run the test suite:
```sh
   pytest -x
```

## Project Structure

- `lib/student_data.py` — stores student records as a list of tuples `(ID, Name, Major)`
- `lib/filters.py` — `filter_students_by_major()` filters students by major using a list comprehension
- `lib/data_processing.py` — `format_student_data()` formats a single student record; `display_students()` prints all records
- `lib/set_operations.py` — `unique_majors()` returns the set of distinct majors using a set comprehension
- `lib/data_generator.py` — `student_generator()` lazily yields students by major using a generator expression

## Usage

```python
from lib.student_data import students
from lib.filters import filter_students_by_major
from lib.data_processing import display_students
from lib.set_operations import unique_majors
from lib.data_generator import student_generator

# Filter students by major
cs_students = filter_students_by_major(students, "Computer Science")
display_students(cs_students)

# Get unique majors
print(unique_majors(students))

# generate students by major
math_gen = student_generator(students, "Mathematics")
print(next(math_gen))
```

## Testing

All functionality is covered by pytest tests in the `testing/` directory:

```sh
pytest -x
```