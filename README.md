# Family-Travel-Japan
The project was created to simulate a real software product and demonstrate a complete QA workflow, from requirements analysis and test planning to bug reporting, API testing, SQL, mobile testing, and test automation.
🏨 Family Travel Japan — QA Portfolio Project







📌 About the Project

Family Travel Japan is a QA portfolio project focused on validating an MVP for family-friendly hotel search in Japan.

The project was created to simulate a real software product and demonstrate a complete QA workflow, from requirements analysis and test planning to bug reporting, API testing, SQL, mobile testing, and test automation.

The main idea is to make hotel search easier for families by allowing users to search using information such as:

destination;
check-in and check-out dates;
number of adults;
number of children;
children's ages;
price range.

The project is designed as a small MVP, keeping the scope realistic for a Junior QA portfolio.

🎯 Project Objective

The main objective is to demonstrate practical QA skills through a complete testing process.

This project focuses on:

requirements analysis;
test planning;
test case design;
functional testing;
negative testing;
boundary value testing;
UI validation;
API testing;
database validation;
mobile testing;
test automation;
regression testing;
bug reporting;
test documentation.
💡 Problem

Families traveling in Japan may need to consider several factors when looking for accommodation:

destination;
travel dates;
number of adults;
number of children;
children's ages;
hotel price;
hotel information.

A search experience that does not validate these criteria correctly can generate incorrect results or prevent users from finding suitable accommodation.

The project therefore focuses on validating whether the search flow correctly handles family-specific travel scenarios.

👨‍👩‍👧‍👦 Target Users

The main target audience is:

Families traveling in Japan with children.

Example:

2 adults + 2 children (ages 4 and 8)
Destination: Shizuoka
Trip: future dates
Price: up to ¥50,000

🚀 MVP Scope

The MVP contains the following main flow:

Destination
     ↓
Travel Dates
     ↓
Adults
     ↓
Children
     ↓
Children's Ages
     ↓
Price Range
     ↓
Search
     ↓
Hotel Results
     ↓
Hotel Details
Included

✅ Destination search
✅ Check-in and check-out
✅ Adult quantity
✅ Child quantity
✅ Children's ages
✅ Price filter
✅ Search validation
✅ Hotel results
✅ Hotel details

Out of Scope

❌ Real payment
❌ Real booking
❌ Cancellation system
❌ Loyalty points
❌ Administrative area
❌ Complete user account system

📋 Functional Requirements
RF-001 — Inform Destination

The destination is mandatory.

The system should:

accept Japanese characters;
accept Latin characters;
accept Portuguese destination names;
validate whether the destination exists;
display an appropriate error for a nonexistent destination.

Examples:

静岡       → Valid
Shizuoka   → Valid
São Paulo  → Valid
XXXXXX     → Invalid
RF-002 — Inform Travel Period

The system should:

require check-in;
require check-out;
require check-out to be after check-in;
prevent selection of past dates;
require at least 2 nights.

Examples:

Today → Tomorrow
Invalid

Future Date → Date + 2 days
Valid
RF-003 — Number of Adults

Rules:

Minimum: 1
Maximum: 5

Examples:

0 → Invalid
1 → Valid
5 → Valid
6 → Invalid
-1 → Invalid
RF-004 — Number of Children

Children are optional.

Rules:

Minimum: 0
Maximum: 5

When children are included, their individual ages must be informed.

Child age range:

0 to 12 years

Examples:

0 children → Valid
1 child    → Valid
5 children → Valid
6 children → Invalid

Age 0  → Valid
Age 12 → Valid
Age 13 → Invalid
RF-005 — Price Range

The price filter is optional.

Rules:

Maximum price: ¥50,000

When no price filter is provided, the system should display the cheapest offers first.

Examples:

¥25,000 → Valid
¥50,000 → Valid
¥50,001 → Invalid
RF-006 — Search Validation

Before proceeding to the results page, the system must validate mandatory information.

When a required field is empty:

the field should be highlighted in red;
the user should not proceed to the next page;
the Search button should not complete the navigation.

Optional fields should not block the search.

RF-007 — Hotel Results

After a valid search, the system should display compatible hotel results.

Each result should contain, at minimum:

hotel name;
image;
location;
price;
rating/review information.

When no price filter is provided, results should be ordered from the cheapest to the most expensive.

RF-008 — Hotel Details

The user should be able to select a hotel and view:

hotel name;
images;
location/address;
price;
rating/reviews;
description;
main amenities.

The user should also be able to return to the search results.

🧪 Test Strategy

The project uses different testing techniques to validate the MVP.

Functional Testing

Validation of the expected behavior for each requirement.

Negative Testing

Testing invalid inputs and unexpected user actions.

Examples:

empty required fields;
invalid dates;
nonexistent destinations;
invalid adult quantities;
invalid child ages;
prices outside the allowed range.
Boundary Value Analysis

Examples:

Adults:
0 | 1 | 5 | 6

Children:
0 | 1 | 5 | 6

Child age:
-1 | 0 | 12 | 13

Price:
¥24,999 | ¥25,000 | ¥50,000 | ¥50,001
UI Testing

Validation of:

field behavior;
error states;
button behavior;
navigation;
displayed information.
API Testing

API requests, responses, status codes and validation using Postman.

Database Testing

Validation of stored and returned data using SQL, when a database is available.

Mobile Testing

Testing the application flow on an Android environment using Android Studio.

Automation Testing

Automation of selected regression and functional scenarios using Selenium WebDriver.

Regression Testing

Re-execution of critical scenarios after bug fixes or relevant changes.
