# Day 9
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/e9e34e47-bde4-4d30-9c1d-1976b674f13c)

## Day 9 Tasks:

### 1. What HTTP User-Agent was used by the malware for its connection requests to the C2 server?

    Open dnSpy → File → Open → Navigate to the desktop, Click all files at the bottom, and choose the juicyTomatoydefang
    Now click and expand juicytomatoy and JuicyTomaToy.exe and inspect the program

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/2dd1b23a-b921-4847-9bf9-924e6f6679a0)


    Mozilla/5.0 (Macintosh; Intel Mac OS X 14_0) AppleWebKit/605.1.15 (KHTML, like Gecko) Version/17.0 Safari/605.1.15

### 2. What is the HTTP method used to submit the command execution output?

    Inspect the Code or use the below video reference
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/4f704f51-e062-476b-a3ba-2a1279d328b4)

    POST




### 3. What key is used by the malware to encrypt or decrypt the C2 data?

Inspect the Code or use the below video reference

Ans: youcanthackthissupersecurec2keys




### 4. What is the first HTTP URL used by the malware?

Inspect the Code or use the below video reference

Ans: http://mcgreedysecretc2.thm/reg

5. How many seconds is the hardcoded value used by the sleep function?

Inspect the Code or use the below video reference

    Use your skills to find the Answer for this Question

    If you are unble to find, use the below video to find the answer

6. What is the C2 command the attacker uses to execute commands via cmd.exe?

Inspect the Code or use the below video reference

Ans: shell

7. What is the domain used by the malware to download another binary?

Inspect the Code or use the below video reference

Ans: stash.mcgreedy.thm

