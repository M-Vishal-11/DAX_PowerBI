# Power BI DAX -- Date Table, Calculated Table, and Time Intelligence Practice

## Overview

This project demonstrates the creation and manipulation of Date and
Time-related data structures in Power BI using DAX.

The objective of this exercise was to understand:

-   Creating a custom Date Table using DAX
-   Working with Date and Time dimensions
-   Creating Calculated Tables
-   Building DAX measures and calculated columns
-   Performing string and date manipulations
-   Understanding filtering with `CALCULATETABLE()`

------------------------------------------------------------------------

## Date Table Creation

A Date Table was created using:

``` dax
Date Table =
CALENDAR(DATE(2025,01,01), DATE(2026,01,01))
```

This generated a continuous calendar containing all dates between
January 1, 2025 and January 1, 2026.

------------------------------------------------------------------------

## Calculated Columns Created

The Date Table was enriched with multiple calculated columns:

  Column               Description
  -------------------- -----------------------------------------
  Date                 Calendar Date
  Month Number         Numeric month value (1--12)
  Month Shortname      Abbreviated month name (Jan, Feb, etc.)
  Month Fullname       Full month name
  Week Number          Week number of the year
  WeekDay              Numeric weekday
  WeekDay Fullname     Full weekday name
  WeekDay Short        Short weekday name
  Concatinate Fun      Month + Weekday concatenation
  Concatenate WD Fun   Formatted Month - Weekday text
  Left Fun             LEFT() string operation
  Right Fun            RIGHT() string operation
  Mid Fun              MID() string operation
  Length Fun           LEN() function output
  Count WeekNum        Count-based aggregation column

------------------------------------------------------------------------

## DAX Functions Practiced

### Date Functions

-   CALENDAR()
-   DATE()
-   WEEKNUM()
-   MONTH()
-   FORMAT()

### Text Functions

-   LEFT()
-   RIGHT()
-   MID()
-   LEN()
-   CONCATENATE()

### Aggregation Functions

-   COUNT()
-   SUM()
-   SUMX()
-   MIN()
-   MINX()
-   MAX()
-   PRODUCT()

------------------------------------------------------------------------

## Measures Created

The model contains several DAX measures used for practice:

-   Max Fun
-   Min Fun
-   Minx Fun
-   Product Fun
-   Sum Fun
-   Sumx Fun
-   All Except

These measures were created to understand aggregation behavior and row
context vs filter context concepts.

------------------------------------------------------------------------

## Calculated Table

A filtered calculated table was created using:

``` dax
Calculated Table =
CALCULATETABLE(
    'Date Table',
    'Date Table'[Month Shortname] = "DEC",
    'Date Table'[WeekDay Short] = "FRI"
)
```

### Result

The calculated table returns only the rows where:

-   Month = December
-   Weekday = Friday

Output contains:

-   05/12/2025
-   12/12/2025
-   19/12/2025
-   26/12/2025

This demonstrates how `CALCULATETABLE()` applies filter conditions to
generate a new table.

------------------------------------------------------------------------

## Learning Outcomes

Through this exercise the following concepts were explored:

1.  Date dimension modeling
2.  Calendar table creation
3.  Time intelligence preparation
4.  Calculated columns
5.  Calculated tables
6.  DAX measures
7.  Text manipulation functions
8.  Filter context
9.  Row context
10. Aggregation functions in DAX

------------------------------------------------------------------------

## Tools Used

-   Power BI Desktop
-   DAX (Data Analysis Expressions)

------------------------------------------------------------------------

## Author

Power BI DAX Practice Project focused on Date Table creation, Time
Intelligence preparation, Calculated Tables, and DAX function
experimentation.
