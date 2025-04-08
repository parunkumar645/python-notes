# Dates in Python - Student Notes

## 1. Definition

Python provides several modules to handle dates and times. The most commonly used modules are:

- **`datetime`**: The primary module for working with dates and times in Python. It provides classes for manipulating dates, times, and time intervals.
- **`time`**: A module providing various time-related functions, primarily focused on timestamps and time formatting.
- **`calendar`**: A module offering calendar-related functions such as displaying calendars and calculating day of the week.

The `datetime` module is the most versatile and contains several important classes:
- `datetime.date` - For date values (year, month, day)
- `datetime.time` - For time values (hour, minute, second, microsecond)
- `datetime.datetime` - Combination of date and time
- `datetime.timedelta` - Represents a duration or difference between dates/times

## 2. Basic Examples

### Example 1: Getting Current Date and Time
```python
import datetime

# Get current date
today = datetime.date.today()
print(f"Current date: {today}")  # Format: YYYY-MM-DD

# Get current date and time
now = datetime.datetime.now()
print(f"Current date and time: {now}")  # Format: YYYY-MM-DD HH:MM:SS.microseconds

# Get components of today's date
print(f"Year: {today.year}")
print(f"Month: {today.month}")
print(f"Day: {today.day}")
```

### Example 2: Creating Custom Dates
```python
import datetime

# Create a specific date
birthday = datetime.date(1990, 5, 15)  # Year, Month, Day
print(f"Birthday: {birthday}")

# Create a specific date and time
appointment = datetime.datetime(2023, 9, 10, 14, 30, 0)  # Year, Month, Day, Hour, Minute, Second
print(f"Appointment: {appointment}")

# Create date from timestamp
import time
timestamp = time.time()  # Current timestamp (seconds since Jan 1, 1970)
date_from_timestamp = datetime.date.fromtimestamp(timestamp)
print(f"Date from timestamp: {date_from_timestamp}")
```

### Example 3: Date Formatting and Parsing
```python
import datetime

# Get current date and time
now = datetime.datetime.now()

# Format date as string using strftime (string from time)
formatted_date = now.strftime("%A, %B %d, %Y")  # Example: Monday, January 01, 2023
formatted_time = now.strftime("%H:%M:%S")  # Example: 14:30:45
formatted_datetime = now.strftime("%m/%d/%Y %H:%M")  # Example: 01/01/2023 14:30

print(f"Formatted date: {formatted_date}")
print(f"Formatted time: {formatted_time}")
print(f"Formatted date and time: {formatted_datetime}")

# Parse string to date using strptime (string parse time)
date_string = "2023-12-25"
parsed_date = datetime.datetime.strptime(date_string, "%Y-%m-%d")
print(f"Parsed date: {parsed_date}")

date_time_string = "12/31/2023 23:59"
parsed_datetime = datetime.datetime.strptime(date_time_string, "%m/%d/%Y %H:%M")
print(f"Parsed datetime: {parsed_datetime}")
```

### Example 4: Date Calculations
```python
import datetime

# Create dates
today = datetime.date.today()
future_date = datetime.date(2023, 12, 31)

# Calculate difference between dates
delta = future_date - today
print(f"Days until December 31, 2023: {delta.days}")

# Add days to a date
one_week_later = today + datetime.timedelta(days=7)
print(f"One week from today: {one_week_later}")

# Subtract days from a date
one_week_ago = today - datetime.timedelta(days=7)
print(f"One week ago: {one_week_ago}")

# More complex time difference
three_hours_later = datetime.datetime.now() + datetime.timedelta(hours=3)
print(f"Three hours from now: {three_hours_later}")

# Creating a timedelta directly
time_period = datetime.timedelta(days=2, hours=3, minutes=30)
future_time = datetime.datetime.now() + time_period
print(f"Future time after adding period: {future_time}")
```

### Example 5: Working with Calendar
```python
import calendar
import datetime

# Check if year is leap year
year = 2024
is_leap = calendar.isleap(year)
print(f"Is {year} a leap year? {is_leap}")

# Get day of the week (0 is Monday, 6 is Sunday)
today = datetime.date.today()
weekday = today.weekday()
print(f"Today is day {weekday} of the week")
print(f"Today is {calendar.day_name[weekday]}")

# Print calendar for a month
cal = calendar.month(2023, 9)  # September 2023
print("Calendar for September 2023:")
print(cal)

# Get the first Friday of the month
year = 2023
month = 10
cal = calendar.monthcalendar(year, month)
for week in cal:
    if week[calendar.FRIDAY] != 0:
        first_friday = datetime.date(year, month, week[calendar.FRIDAY])
        break
print(f"First Friday of Oct 2023: {first_friday}")
```

## 3. Practice Questions

### Question 1
Write a Python program that asks the user for their birth year, month, and day, then calculates and displays their exact age in years, months, and days.

### Question 2
Create a function that takes a date as input and returns whether it's a weekday or weekend day. Test it with various dates.

### Question 3
Write a program that displays a calendar for the current month and highlights the current day.

### Question 4
Create a program that calculates the difference between two dates in terms of years, months, and days. For example, the difference between "2023-01-01" and "2025-06-15" should be displayed as "2 years, 5 months, and 14 days".

### Question 5
Write a function that takes a year as input and returns a list of all dates that fall on Friday the 13th in that year.