# Ex.No: 9  Logic Programming –  Computer Maintenance Expert System
### DATE:                                                                            
### REGISTER NUMBER : 212222040061
### AIM: 
Write a Prolog program to build a computer maintenance expert system.
###  Algorithm:
1. Start the program.
2. Write the rules for each fault in computer.
3. If system have printing problem, missing dots and no uniform printing then system fault on printer head.
4. If system have not printing, missing dots and spread inks then system fault on ribbon
5. If system have not printing, paper jam and out of paper then system fault on paper stuck in printer
6. Similarly define rules for all faults.
7. Define facts for system problems.
8. Find the fault of computer by passing query to system.
     
### Program:
```
% Define the main goal to start the expert system
start :-
    write('Welcome to the Computer Maintenance Expert System!'), nl,
    write('Please answer the following questions to help diagnose the problem.'), nl,
    find_problem(Problem),
    write('The diagnosed problem is: '), write(Problem), nl,
    solution(Problem).

% Define facts and rules for different types of computer problems

% Printer head problem
find_problem(printer_head_fault) :-
    printing_problem,
    ask('Are there missing dots on the printouts?'),
    ask('Is the printing not uniform?').

% Ribbon problem
find_problem(ribbon_fault) :-
    not_printing,
    ask('Are there missing dots on the printouts?'),
    ask('Is there spread ink on the paper?').

% Paper stuck problem
find_problem(paper_stuck) :-
    not_printing,
    ask('Is there a paper jam?'),
    ask('Is the printer out of paper?').

% General system problem
find_problem(system_overheating) :-
    ask('Is your computer getting very hot?'),
    ask('Is the system shutting down unexpectedly?').

find_problem(virus_infection) :-
    ask('Is your computer running unusually slow?'),
    ask('Are there unexpected pop-ups or strange behavior?').

find_problem(power_issue) :-
    ask('Is your computer failing to turn on?'),
    ask('Have you checked the power connections and battery?').

% Default case if no problem is matched
find_problem(unknown_problem) :-
    write('Unable to diagnose the problem based on your answers. Please consult a technician.').

% System faults and symptoms
printing_problem :-
    ask('Is there a problem with printing?').

not_printing :-
    ask('Is the printer not printing at all?').

% Solutions for diagnosed problems
solution(printer_head_fault) :-
    write('Solution: Clean or replace the printer head.').

solution(ribbon_fault) :-
    write('Solution: Replace the printer ribbon.').

solution(paper_stuck) :-
    write('Solution: Remove any stuck paper and check the paper tray for obstructions.').

solution(system_overheating) :-
    write('Solution: Clean the fans and ensure proper ventilation. You may also need to use a cooling pad.').

solution(virus_infection) :-
    write('Solution: Run a full system antivirus scan and remove any detected threats.').

solution(power_issue) :-
    write('Solution: Check the power supply, battery, and cables. Replace or repair if necessary.').

solution(unknown_problem) :-
    write('Solution: Please consult a technician for further assistance.').

% Helper predicate to ask yes/no questions and get user input
ask(Question) :-
    format('~w (yes/no): ', [Question]),
    read(Response),
    Response == yes.
```

### Output:
![computer expert system](https://github.com/user-attachments/assets/e02c0a46-f407-4ccc-97e0-5d0bb46f2335)


### Result:
Thus the simple omputer maintenance expert system was built sucessfully.
