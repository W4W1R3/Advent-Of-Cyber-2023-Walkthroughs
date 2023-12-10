# Day 9
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/e9e34e47-bde4-4d30-9c1d-1976b674f13c)

## Day 9 Tasks:

### 1. What HTTP User-Agent was used by the malware for its connection requests to the C2 server?

    Open dnSpy → File → Open → Navigate to the desktop, Click all files at the bottom, and choose the juicyTomatoydefang
    Now click and expand juicytomatoy and JuicyTomaToy.exe and inspect the program

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/2dd1b23a-b921-4847-9bf9-924e6f6679a0)


    Mozilla/5.0 (Macintosh; Intel Mac OS X 14_0) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.0 Safari/605.1.15

### 2. What is the HTTP method used to submit the command execution output?

    Inspect the Code 
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/4f704f51-e062-476b-a3ba-2a1279d328b4)

    POST




### 3. What key is used by the malware to encrypt or decrypt the C2 data?

    Inspect the Code 
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/3b424980-72cd-4b0d-9391-7b11f27daf0e)

    youcanthackthissupersecurec2keys




### 4. What is the first HTTP URL used by the malware?

    Inspect the Code 
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/9a01b2e9-aff3-4cb7-86cd-16fe5236c9bc)


    http://mcgreedysecretc2.thm/reg

5. How many seconds is the hardcoded value used by the sleep function?

Inspect the Code 

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/b90bb22a-e4a2-4178-8fa5-aa88dd38605b)

    15
    
6. What is the C2 command the attacker uses to execute commands via cmd.exe?

Inspect the Code 

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/798572d6-e313-4e23-923c-58a0dfe73b8b)

        shell

7. What is the domain used by the malware to download another binary?

Inspect the Code 
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/c2c617ec-d75e-446a-86b0-6eb98aea44fe)

    stash.mcgreedy.thm

