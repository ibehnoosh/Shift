# Nurse Rostering
## Overview:

We needed to develop a medical rostering system for a major hospital where:
- Nurses work in a rotating shift system. 
- There are three shifts per day: morning, evening, and night. 
- Each shift requires five nurses. 
- Nurses must not work more than one shift per day.

Over time, the requirements evolved and the system needed to be more adaptable to different policies related to nurse selection and shift assignment.

## Implementation:
### Initial Solution:
- Utilized models for Nurse and Shift. 
- Developed a buildRoster function to generate the roster by randomly assigning nurses to each shift.

### Refinements:

1.  Shift Extension:
 - Leveraged PHP 8's ENUM to represent different shift types (ShiftType), making it easier to introduce new types of shifts in the future.
2. Separation of Concerns:
 - Broke down the buildRoster function to modularize logic:
 - Picking nurses for the day.
 - Assigning nurses to specific shifts.

3. Policy-based Architecture:
- Introduced interfaces to encapsulate policies for nurse selection (NurseSelectionPolicyInterface) and nurse shift assignment (NurseAssignmentPolicyInterface).
- Developed policies like SingleShiftPolicy to handle nurse selection.
- Developed shift assignment policies like FiveNurseAssignmentPolicy to handle how many nurses are assigned to each type of shift.


## Key Benefits:
- Modularity: The code is now more modular, adhering to the Single Responsibility Principle. 
- Extensibility: New policies can be easily implemented and plugged in without altering core roster-building logic.
- Maintainability: With policies and logic separated, future changes or adaptations are easier to manage.

## Future Considerations:
- Using DataBase for managing policies.
- Implement additional policies for various requirements.
- Enhance validation to account for nurse preferences or specializations.
- Writing more Tests.

## Running

This app is designed to be from the command line using:

```
php artisan app:generate-roster --help
```

Doing so with no params should print out usage information.

## Tests

You can run tests with `php artisan test`. Tests for the scaffold code have been provided.


### Note
For me, software engineering is not only about Coding, Designing or Testing, it’s a lifestyle based on logic, learning, sharing,  problem-solving, empathy, and full of fun and bugs!🚀🐛
