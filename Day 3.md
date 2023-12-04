# Day 3

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/40a1d025-4fe8-4490-acdd-5bcdf22193f2)

# Scenario

The server room is securely locked, and the team must regain access to recover backup tapes. Brute-forcing the PIN panel stands out as the potential option.

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/be86e8da-1c7a-4a1f-9d83-d0cc82af0cbe)


## Learning Objectives

Upon completing this task, you will gain an understanding of:

- Password complexity and the count of possible combinations.
- The impact of the number of possible combinations on the feasibility of brute force attacks.
- Generating password combinations using `crunch`.
- Automated password trials using `hydra`.

## Feasibility of Brute Force

### Inquiries

1. How many distinct PIN codes exist?
2. How many passwords can be generated?
3. What is the time estimate for finding the password via brute force?

## Counting the PIN Codes

Many systems depend on PIN codes or passwords for user authentication. Without proper security measures, such systems are susceptible to various attacks. Here, we explore brute force attacks, where an adversary systematically tries all possible combinations of a given password.

Consider a scenario where a four-digit PIN code must be selected. The total count would be 10,000 different PIN codes: 0000, 0001, 0002,..., 9998, and 9999. Mathematically, this is 10×10×10×10 or simply 10^4 different PIN codes.

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/6e1c8b72-7e67-4fcb-8f1d-7ad686b1246e)


## Counting the Passwords

Let's imagine a scenario with a four-character password, where each character can be:

- A digit: We have 10 digits (0 to 9).
- An uppercase English letter: We have 26 letters (A to Z).
- A lowercase English letter: We have 26 letters (a to z).

Therefore, each character can be one of 62 different choices. Consequently, for a four-character password, we can create 62×62×62×62 = 62^4 = 14,776,336 different passwords.

To enhance complexity, symbols can be added, expanding the set of choices by more than 30 characters.

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/cebdf03b-911a-4b72-b045-43939842a530)


